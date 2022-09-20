---
permalink: /relaydesk/
title: "Relaydeskdesk"
author_profile: true
author:
  name: "Enables a channel to have a conversation with non-members"
  avatar: "/_pages/Relaydesk/color.png"
  bio: "[Relaydesk POC](mailto:info@wni.app?subject=Relaydesk%20POC)"
  home: /relaydesk/

toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
toc_sticky: true
---

## Overview

Relaydesk enables a private Teams channel to have a conversation with a non-member. A typical use-case is a help desk channel (e.g. HR, IT) being able to have a conversation with an user without that person joining the help desk channel. This help desk scenario is typically being solved with a shared mailbox (e.g. hr@contoso.com). Relaydesk keeps these conversations in Teams.

## How it works

- Once Relaydesk is installed in a team, it generates a link for each channel. A channel link can be shared with anyone outside the team that needs to have a conversation with the channel.
- When a user clicks on the channel link, it opens their Teams app and prepopulates a message to the Relaydesk bot that initiates a conversation with the channel. No Teams app install is required for the user.
- The Relaydesk app posts the user's message into the channel as a new conversation, and anyone in the team can respond. The conversation can continue back and forth between the channel and the user via the Relaydesk bot.

## Benefits

- Eliminates need for internal shared mailboxes.
- Simply add app to the team and post channel link.
- No app install for users contacting channel.
- App does not store messages, it just relays them.

## Demo Videos

### Desktop/Web

This is a demo using the Teams web client.
{% include video id="m8d564XxObw" provider="youtube" %}

### Mobile

This is a demo using the Teams iOS client.  
{% include video id="q3zo5NFD6sk" provider="youtube" %}

## Instructions

### Add app, get channel link

- Add the app to your team. The app will respond with a welcome card that includes the unique link for each channel.
- Note that when users contact your channel, they will see the channel's name so they know who they are messaging. If you need to, you can [change the channel name in Teams](https://support.microsoft.com/en-us/office/change-a-channel-name-in-teams-bb1761e1-bc68-4654-985d-7095cd0b2032) to something more descriptive.
- You can post the channel link for users to reach on your intranet, company directory, etc.

### User clicks channel link

- When a user clicks on the channel link, it will open the Teams client and pre-populate a message to the Relaydesk app such as the following: "To start a conversation with Contoso IT Helpdesk, please click send. RelaydeskID #d9ekcdke0#".
- When the user sends the message to the app, it responds with an adaptive card confirming the channel name, and asks the user to enter their message. When the user hits submit, the card refreshes to include their message, and then sends the message to the channel.
- Since the user is just having a conversation with the app, and no additional permissions are needed, and it is not necessary for the user to install the Relaydesk app.

### Channel receives message

- The message from the user is added to the channel by the app as a new conversation with the message in an adaptive card.
- Any team member can click on the Reply button on the card, and an edit form will toggle open where they can enter their message and click Submit to send the reply. The card will refresh to include the reply from the channel to that particular message.
- Any other messages posted in the conversation will remain private to the channel, so the team can have internal discussions about the case/issue all in the same thread.

### User receives reply

- The user will receive the reply from the channel as a new message card, and they can respond in the same way that the channel did, and their card will refresh to show their response.
- If necessary, they can respond more than once to each message by clicking Reply again. Regardless of which message they reply to, each response will be posted as a new reply in the same channel conversation, so all messages from the are kept together in the channel.

## Pricing

This app is free for up to 1000 messages per helpdesk channel member, which is intended to allow free casual use, or enough to run a trial in a busy helpdesk. After that, each helpdesk channel member is $5 per month. No app is required for the user to contact the channel, so the cost is only for the channel members.

## Limitations and roadmap

This is a very basic POC version of the app, and we are working on adding more features. Here are some of the roadmap items:

- Mark conversations as closed, forcing users to open a new thread for another issue.
- Include fields for users to set urgency, type of issue, etc.
- Inclued fields for helpdesk members to assign conversations.
- Lookup user in a related system (e.g. HRMS) to help speed access to relevant data.

## Version History

- 1.0.0 - POC release
