---
permalink: /app-setup/
title: "App Setup"
toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
toc_sticky: true
---

This page outlines the tooling and setup process WNI uses for creating a new Teams App.

### Setup ngrok tunneling for local development

- You need an ngrok account for your local development. Don't forget to check your email and confirm your account, and then add your personal token locally so that the forwarding doesn't time out.
- Once running in the terminal, type ngrok http --host-header=rewrite 3978
- We'll use the forwarding URL, e.g. https://dc97-2001-569-7a7f-1900-59cf-6265-d6b8-bd5d.ngrok.io shortly.

### Scaffold app using Teams Toolkit for VS Code

- Create a new JavaScript bot app
- Configure local environment .fx/configs/config.local.json with the siteEndpoint using the forwarding Url above for ngrok as follows:

```
{
    "$schema": "https://aka.ms/teamsfx-env-config-schema",
    "description": "You can customize the TeamsFx config for different environments. Visit https://aka.ms/teamsfx-env-config to learn more about this.",
    "bot": {
        "siteEndpoint": "https://0de7-50-92-169-16.ngrok.io"
    },
    "manifest": {
        "appName": {
            "short": "Relaydesk-local",
            "full": "Full name for Relaydesk-local"
        },
        "description": {
            "short": "Short description of Relaydesk-local",
            "full": "Full description of Relaydesk-local"
        },
        "icons": {
            "color": "resources/color.png",
            "outline": "resources/outline.png"
        }
    }
}

```

- Configuring the siteEndpoint enables debugging startup to be faster and more reliable than relying on Teams Toolkit to launch ngrok. The downside is that if you close the ngrok session you need to remember to refresh the siteEndpoint value with the new one you create as the forwarding Url is new each time (on the free plan).

- Configure the .fx/configs/azure.parameters.dev.json with a friendly, but unique to all of Azure, resourceBaseName as follows:

```
{
  "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentParameters.json#",
  "contentVersion": "1.0.0.0",
  "parameters": {
    "provisionParameters": {
      "value": {
        "resourceBaseName": "relaydesk-dev",
        "botAadAppClientId": "{{state.fx-resource-bot.botId}}",
        "botAadAppClientSecret": "{{state.fx-resource-bot.botPassword}}"
      }
    }
  }
}
```

- Create a prod environment in Teams Toolkit, and configure the resourceBaseName (e.g. relaydesk-prod).

### Provision Azure resources using Teams Toolkit for VS Code.

- We are using an existing shared linux app service plan to host the new app, and the deployment model will be to [run the app from a zip package](https://learn.microsoft.com/en-us/azure/app-service/deploy-run-package). Using this approach Github actions can deploy a new commit in 1-2 min. The webapp provisioning template (/templates/azure/provision/webapp.bicep) needs to be as follows (subscription ID omitted):

```
@secure()
param provisionParameters object
param userAssignedIdentityId string

var resourceBaseName = provisionParameters.resourceBaseName
// var serverfarmsName = contains(provisionParameters, 'botServerfarmsName') ? provisionParameters['botServerfarmsName'] : '${resourceBaseName}bot' // Try to read name for App Service Plan from parameters
// var webAppSKU = contains(provisionParameters, 'botWebAppSKU') ? provisionParameters['botWebAppSKU'] : 'B1' // Try to read SKU for Azure Web App from parameters
var webAppName = contains(provisionParameters, 'botSitesName') ? provisionParameters['botSitesName'] : '${resourceBaseName}bot' // Try to read name for Azure Web App from parameters

// Web App that hosts your bot
resource webApp 'Microsoft.Web/sites@2021-02-01' = {
  kind: 'app'
  location: 'East US'
  name: webAppName
  properties: {
    serverFarmId: '/subscriptions/826d4700-d96d-458e-ba88...replace with subscriptionID/resourceGroups/DefaultResourceGroup-EUS/providers/Microsoft.Web/serverFarms/wni-shared-linux-dev'
    keyVaultReferenceIdentity: userAssignedIdentityId // Use given user assigned identity to access Key Vault
    httpsOnly: true
    siteConfig: {
      linuxFxVersion: 'node|14-lts'
      appSettings: [
        {
          name: 'WEBSITE_RUN_FROM_PACKAGE'
          value: '1'
        }
      ]
      ftpsState: 'FtpsOnly'
    }
  }
  identity: {
    type: 'UserAssigned'
    userAssignedIdentities: {
      '${userAssignedIdentityId}': {} // The identity is used to access other Azure resources
    }
  }
}

output webAppName string = webAppName
output webAppDomain string = webApp.properties.defaultHostName
output webAppResourceId string = webApp.id
output webAppEndpoint string = 'https://${webApp.properties.defaultHostName}'

```

### Setup Github with deployment to Azure

Once the Azure resources are provisioned, open a terminal in VS Code (with [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli) installed first), and run the following command. You need to do this twice, once each for the dev and prod resource groups (update command accordingly). Also give each service principal a name that is easy to recognize in your list of app registrations.

```
az ad sp create-for-rbac --name "relay-dev-sp" --role contributor --scopes /subscriptions/826d4700-d96d-458e-ba88...replace with subscriptionID/resourceGroups/relay-dev --sdk-auth

```

The output will be as follows:

```
This command or command group has been migrated to Microsoft Graph API. Please carefully review all breaking changes introduced during this migration: https://docs.microsoft.com/cli/azure/microsoft-graph-migration
Option '--sdk-auth' has been deprecated and will be removed in a future release.
Creating 'contributor' role assignment under scope '/subscriptions/826d4700-d96d-458e-ba88-4f56.../resourceGroups/relaydesk-prod'
The output includes credentials that you must protect. Be sure that you do not include these credentials in your code or check the credentials into your source control. For more information, see https://aka.ms/azadsp-cli
{
  "clientId": "3e77949a-59af-40ba-b9a3-c286ed3d6b0f",
  "clientSecret": "CRW8Q~LvrikfI2CMGrwArUnvp1LoRlO0zcndNcHU",
  "subscriptionId": "826d4700-d96d-458e-ba88-4f56...",
  "tenantId": "58f3cd82-820b-4eaf-a33c-c4dabf6....",
  "activeDirectoryEndpointUrl": "https://login.microsoftonline.com",
  "resourceManagerEndpointUrl": "https://management.azure.com/",
  "activeDirectoryGraphResourceId": "https://graph.windows.net/",
  "sqlManagementEndpointUrl": "https://management.core.windows.net:8443/",
  "galleryEndpointUrl": "https://gallery.azure.com/",
  "managementEndpointUrl": "https://management.core.windows.net/"
}
```

- Create a Github repo to use with the project.
- Add the information from each of the above outputs to settings>secrets>actions in the Github repo, the end-result being as follows:

![](/assets/images/actions-secrets.png)

- Initialize a git repository for the project locally in VS Code.
- Add the Githup repo as a remote from a terminal as follows:

```
git remote add origin https://github.com/wni-app/relaydesk.git
git branch -M main
git push -u origin main

```

- Add a Github actions deployment workflow file (e.g.relaydesk-dev.yml) for each branch (e.g. dev will push to dev and main will push to prod) to /.github/workflows/

The workflow references the secrets for each resource group created earlier and is as follows:

```
{% raw %}
# Docs for the Azure Web Apps Deploy action: https://github.com/Azure/webapps-deploy
# More GitHub Actions for Azure: https://github.com/Azure/actions
# test

name: Relaydesk-dev

on:
  push:
    branches:
      - dev
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v2

      - name: Set up Node.js version
        uses: actions/setup-node@v1
        with:
          node-version: "14.x"

      - name: npm install
        working-directory: bot
        run: |
          npm install

      - name: Zip artifact for deployment
        run: zip release.zip ./* -r
        working-directory: bot

      - name: Upload artifact for deployment job
        uses: actions/upload-artifact@v2
        with:
          name: node-app
          path: bot/release.zip

  deploy:
    runs-on: ubuntu-latest
    needs: build
    environment:
      name: "Production"
      url: ${{ steps.deploy-to-webapp.outputs.webapp-url }}

    steps:
      - name: Download artifact from build job
        uses: actions/download-artifact@v2
        with:
          name: node-app

      - name: Azure Login
        uses: Azure/login@v1.4.5
        with:
          creds: '{"clientId":"${{ secrets.CLIENT_ID_DEV }}","clientSecret":"${{ secrets.CLIENT_SECRET_DEV }}","subscriptionId":"${{ secrets.SUBSCRIPTION_ID }}","tenantId":"${{ secrets.TENANT_ID }}"}'

      - name: Deploy to App Service
        run: |
          az webapp deployment source config-zip --resource-group relaydesk-dev --name relaydesk-devbot --src release.zip

{% endraw %}
```

- Commit the changes of adding the workflow files to main, which will trigger the action to do an initial deployment to prod. You can then create a dev branch and when that is committed you should have an initial deployment to dev also.
- You can launch the dev and prod Teams app from within the Teams Toolkit to test that everything is working as expected. Make sure to give it a couple min after deployment for the web app to come online, and if it is not responding look at the Logs for the web app using the Azure extension for VS Code.

### Creating new local debug setup

- Clone repo into VS Code
- Start ngrok
- Configure config.local.json with bot.siteEndpoint url
- Run debug in chrome or edge, this will create local bot registration and .env.teamsfx.local file.

### Faster and simpler local debugging

Instead of using the default Teams Toolkit VS Code launch configuration, which takes 10-15 seconds and launches an new browser window each time, it is more convenient to use the following VS Code launch configuration (in /.vscode/launch.json):

```
{
			"command": "npm run watch",
			"name": "Run npm watch",
			"request": "launch",
			"type": "node-terminal",
			"cwd": "${workspaceFolder}/bot",
			"envFile": "${workspaceFolder}/bot/.env.teamsfx.local"
}
```

- This will launch in a few seconds and does not create a new browser session and try to install the Teams app again.
- Just remember that if you update the Teams app you need to build a new one and upload it manually to Teams.
