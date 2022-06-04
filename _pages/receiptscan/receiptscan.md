---
permalink: /receiptscan/
title: "ReceiptScan"
author_profile: true
author:
  name   : "Extracts data from a picture of a receipt."
  avatar : "/assets/images/ReceiptScan-main-fs.png"
  bio    : "[Join Beta](mailto:info@wni.app?subject=ReceiptScan%20Beta)"
  home   : /receiptscan/

toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
toc_sticky: true
---
## Overview
Streamline expense reporting by extracting the merchant, date, and purchase amounts from a picture of a receipt sent to the app.  The app will respond with a form containing the extracted values which you can edit and add any comments.  The final values are then sent to your email where you can either use an inbox rule to forward them to your bookkeeper, or trigger a workflow (e.g. Power Automate, Zapier, etc.) to send the data into a spreadsheet, accounting software, etc.  The first 100 receipts are free, after which you can purchase a subscription.

## Benefits

* Quickly record receipts while you are travelling.
* No need for an extra app on your phone
* Use your existing M365 account and storage.
* Receipt images are not stored by app vendor.
* Receipts become searchable in Teams and email.
* Integrate into workflow using Power Automate.
* Simple to use, no training required.

## Demo Videos

**Desktop/Web**

This is a demo using the Teams web client and also includes a demo of a companion Power Automate flow.
{% include video id="m8d564XxObw" provider="youtube" %}

**Mobile (iOS)**

This is a demo using the Teams iOS client.  
{% include video id="q3zo5NFD6sk" provider="youtube" %}

## Example Receipts
You can use these receipts for testing:

[Example Receipt 1](/_pages/receiptscan/contoso.png)

[Example Receipt 2](/_pages/receiptscan/main-st.JPG)

[Example Receipt 2](/_pages/receiptscan/main-st.JPG)

## Instructions

### Send a receipt picture
**Mobile**: Tap the photo icon next to the message compose box to take/select a picture of your receipt, or use the attachment icon to attach media (also access your photos).  

**Desktop/Web**:  Copy and paste a receipt picture into the compose box, drag and drop an picture file into the compose box, or use the attachment icon to select an image from OneDrive or upload.

**Note**: Send only one receipt image per message.  It takes about a minute to process a receipt image, but you don't need to wait until it is complete before you send the next one.

### Edit results
Once the image is process the app will reply with a form that contains the extracted values which you can correct as needed.  Note that the app will not calculate a new total if you change the tip amount for example.  You may optionally a comment, e.g. Lunch with Jane from Contoso, Project#: 3456, etc.  

### Process receipt email
After you click Submit, the receipt values will be sent to the configured email address.  Once the email arrives in your inbox, you can process it further with one or more of the following approaches:

* Inbox rule: Set up a rule to move messages from receiptscan@wni.app to a specific receipts inbox folder, and optionally forward a copy to your bookkeeper.
* Power Automate: Set up a trigger for new emails from receiptscan@wni.app, parse the email body (receipt values are in JSON format), and then push values into a spreadsheet, accounting software, etc.

An example of both of these approaches is shown in the following video:

## Pricing

The free version can process up to 100 receipts total.

A Pro subscription is available for US$5/mo which can process unlimited receipts.

If you need to purchase a volume license, please [contact us](mailto:info@wni.app).

## Limitations

* Personal chat only, no channels or groups.

## Customization
If you would like us to customize this app and/or provide you with a source code license, please [contact us](info@wni.app).

Some example customizations to consider:
* Add additional fields (e.g. project number) to the receipt edit form.  A field could pull values from some other system (e.g. CRM) and provide a drop-down selection option.
* Send receipt values directly to a specified API (e.g. accounting software) instead of users individually needing to configure a workflow.
* Save receipt data with image attachment in a SharePoint list.

## Version History

* 1.0.5 - beta release
