---
permalink: /relaydesk/
title: "Relaydesk"
author_profile: true
author:
  name: "Enables a help desk channel to have a conversation with an employee"
  avatar: "/_pages/Relaydesk/color.png"
  bio: "[POC App](/_pages/relaydesk/appPackage.local.zip)"
  home: /relaydesk/

toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
toc_sticky: true
---

## Overview

Relaydesk enables a standard Teams channel to have a conversation with a non-member. A common use-case is a help desk channel having a conversation with an employee that is not a member of the help desk channel. This help desk scenario is usually solved with a shared mailbox (e.g. hr@contoso.com). Relaydesk keeps these conversations in Teams.

## How it works

- Once Relaydesk is installed in a team, it generates a link for each channel. This channel link can be shared with anyone outside the team that needs to have a conversation with the channel.
- When a user clicks on the channel link, it opens their Teams app and prepopulates a message to the Relaydesk bot that initiates a conversation with the channel. No Teams app install is required for the user.
- The Relaydesk app posts the user's message into the channel as a new conversation, and anyone in the team can respond. The conversation can continue back and forth between the channel and the user via the Relaydesk bot.

## Benefits

- Eliminates the need for shared mailboxes (e.g. hr@contoso), keeps the conversation in Teams.
- Users can contact the helpdesk by just clicking a link, no app install is required.
- Relaydesk just relays regular Teams messages, so they are fully searchable.

## Proof-of-Concept Demo Video

This is a simple demo using the Teams web client.
{% include video id="NJwLkCAAU0w" provider="youtube" %}

## Instructions

### Add app, get channel link

- To upload the POC app to one of your teams, follow these [instructions for uploading a custom app](https://learn.microsoft.com/en-us/microsoftteams/platform/concepts/deploy-and-publish/apps-upload#upload-your-app).
- This is the [POC app package](/_pages/relaydesk/appPackage.local.zip) you want to upload.
- Add the app to your team. The app will respond with a welcome card that includes a unique link for each channel.
- Note that when users contact your channel, they will see the channel's name so they know who they are messaging. If you need to, you can [change the channel name in Teams](https://support.microsoft.com/en-us/office/change-a-channel-name-in-teams-bb1761e1-bc68-4654-985d-7095cd0b2032) to something more descriptive.
- You can post the channel link for users to reach on your intranet, company directory, etc.

### User clicks channel link

- When a user clicks on the channel link, it will open the Teams client and pre-populate a message to the Relaydesk app such as the following: "To start a conversation with Contoso IT Helpdesk, please click send...".
- When the user sends the message to the app, it responds to confirm the channel name, and asks the user to enter the topic and message. When the user hits send, the card refreshes to include their response, and then sends the message to the channel.
- Since the user is just having a conversation with the app's bot, and no additional permissions are needed, and it is not necessary for the user to install the Relaydesk app.

### Channel receives message

- The message from the user is added to the channel by the app as a new conversation with the topic and name of the user.
- Any team member can click on the Reply button on the card, and a message compose form will toggle open where they can enter their message and click Send. The card will refresh to include the reply from the channel to that particular message, and who sent it.
- Any other messages posted in the same conversation will remain private to the channel, so the team can have internal discussions about the case/issue all in the same thread. This is similar to the capability of shared mailbox software solutions like Front.

### User receives reply

- The user will receive the reply from the channel as a new message card, and they can respond in the same way that the channel did, and their card will refresh to show their response.
- If necessary, they can respond more than once to each message by clicking Reply again. Regardless of which message they reply to, each response will be posted as a new reply in the same channel conversation, so all messages from the are kept together in the channel.

## Pricing

This app is free for up to 1000 messages per helpdesk channel member, which is intended to allow free casual use, or enough to run a trial in a busy helpdesk. After that, each helpdesk channel member that needs to respond to messages is $5 per month. Other members of the helpdesk channel that do not respond to messages do not need a license. No app is required for the user to contact the channel so their usage is free.

## Limitations and roadmap

This is a very basic POC version of the app, and there is a lot of work ahead to clean up the UX and add more features.

Here are some of the roadmap items:

- Mark a topic / conversation as closed, allow users to open a new topic / conversation for another issue.
- Include fields to set urgency, type of issue, etc.
- Allow helpdesk members to assign a conversation to themselves or another member.
- Lookup user in a related system (e.g. HRMS) and provide a link to help speed access to relevant data about the user.

## Version History

- 0.0.1 - POC release
