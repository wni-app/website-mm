---
permalink: /relay/
title: "Relay"
author_profile: true
author:
  name: "Enables a channel to have a conversation with non-members"
  avatar: "/_pages/relay/color.png"
  bio: "[Relay Beta](mailto:info@wni.app?subject=Relay%20Beta)"
  home: /relay/

toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
toc_sticky: true
---

## Overview

Relay enables employees to have a conversation with a channel using Teams without needing to be a member of the channel, or making the channel Org-wide. This is ideal for service desk channels that handle employee-specific questions (e.g. HR, IT), where it doesn't make sense to use an Org-wide channel, or add them as members of the channel. Often these situations are handled using a shared mailbox e.g. hr@contoso.com. Relay enables these conversations to stay in Teams, and comes with the added benefit that the service desk channel can privately discuss the messages from the employee in the same channel conversation, similar to shared inbox tools like Front, etc.

## How it works

- Once added to a team, the app generates a unique link (like a mailto: link, but for Teams) for each channel, which can then be posted where employees can access it (e.g. on an HR intranet site).
- When an employee clicks on the channel link, it opens their Teams app with a message to the Relay app pre-populated that initiates a conversation with the channel.
- The Relay app posts their message into the channel, and people in the channel can respond to the employee via the Relay app. The employees do not need to install the Relay app.

## Benefits

- Eliminates need for internal shared mailboxes.
- Simply add app to the team and post channel link.
- No app install for employees contacting channel.
- App does not store messages, it simply relays them.

## Demo Videos

### Desktop/Web

This is a demo using the Teams web client.
{% include video id="m8d564XxObw" provider="youtube" %}

### Mobile

This is a demo using the Teams iOS client.  
{% include video id="q3zo5NFD6sk" provider="youtube" %}

## Instructions

### Add app, get channel link

- Add the app to your team/channel. The app will respond with a welcome card that includes the unique link for the channel.
- If you need to use the app to another channel in the same team, simply @mention the app and send the WelcomeCard command. The app will then respond with welcome card with a link unique for that channel.
- Note that when users contact your channel, they will see the channel's name so they know who they are messaging. If you need to, you can [change the channel name in Teams](https://support.microsoft.com/en-us/office/change-a-channel-name-in-teams-bb1761e1-bc68-4654-985d-7095cd0b2032) so it is easier for users to understand (e.g. "IT Helpdesk" instead of "Triage").
- You can post the channel link for employees to use on your intranet, company directory, etc.

### Employee clicks channel link

- When an employee clicks on the channel link, it is like a mailto: email link, except for Teams. It will open the Teams client and pre-populate a message to the Relay app such as the following: "To start a conversation with Contoso IT Helpdesk, please click send. RelayeID |d9ekcdke0|".
- When the employee sends the message to the bot, it responds with an adaptive card confirming the channel name, and asks the employee to enter their message. When the employee hits submit, the card refreshes to include their message, and then sends the message to the channel.
- Since the employee is just having a conversation with the bot, and no additional permissions are needed, it is not necessary for the employee to install the Relay app in the personal context.

### Channel receives message

- The message from the employee is added to the channel by the app as a new conversation with the message in an adaptive card.
- Any member of the channel can click on the Reply button on the card, and an edit form will toggle open where they can enter their message and click Submit to send the reply. The card will refresh to include the reply from the channel to that particular message.
- Since the employee is not part of the channel, any other messages posted in the conversation will remain private to the channel, so the team can have internal discussions about the case/issue all in the same thread.

### Employee receives reply

- The employee will receive the reply from the channel as a new message card, and they can respond in the same way that the channel did, and their card will refresh to show their response.
- If necessary, they can respond more than once to each message by clicking Reply again. Regardless of which message they reply to, each response will be posted as a new reply in the same channel conversation, so all messages from the are kept together in the channel.

## Pricing

This app is free for testing and casual usage (e.g. 1000 msgs/mo/channel).

If this app is helpful to your organization, we ask that you support its development by purchasing a subscription for US$5/mo for the number of users in your helpdesk channels using it.

If you need to purchase a volume license, please [contact us](mailto:info@wni.app).

## Customization

If you would like us to customize this app and/or provide you with a source code license, please [contact us](info@wni.app).

Some example customizations to consider:

- Mark conversations as closed, forcing users to open a new thread for another issue.
- Include fields for employees to set urgency, type of issue, etc.
- Inclued fields for helpdesk members to assign conversations.
- Lookup employee in HRMS, etc. to help speed access to relevant data.

## Version History

- 1.0.0 - beta release
