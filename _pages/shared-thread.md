---
permalink: /shared-thread/
title: "Shared Thread by WNI"
author_profile: true
author:
  name   : "Enables a channel to share a thread externally."
  avatar : "/assets/images/fluent_share_xlarge.png"
  bio    : "[Click to install](/shared-thread/#instructions)"
  home   : /shared-thread/#instructions

toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
toc_sticky: true
---
Shares a thread between channels for external collaboration, as an alternative to email or a shared channel.  It works like a conference bridge, but for messages.  One channel starts the shared thread and provides the thread ID for other channels to join.  Only replies to a shared thread that @mention the app are shared, so the same thread can be used for both internal and external conversation about a topic. The channels participating in a shared thread can be in any organization.  As an example, HR could share a thread with an outside recruiting firm to discuss a hiring project.

## Problems it solves

**Keeps internal and external messages together.**  
Currently, to get a complete picture of what has been discussed in a project, team members must piece together the messages from their internal channel with the external messages to the client in email or a shared channel.  Using Shared Thread by WNI, a channel can share a thread that is used for both internal and external messages about a topic, keeping everything together.  This improves productivity as everything is now in one place, and the external messages are interleaved chronologically with the internal messages.  Also, since all participants in the shared thread benefit from this, it is easy to get others to adopt.

**Scales to large numbers of external projects.**  
If your team is collaborating on dozens of external projects at once, as often happens in client-facing functions like sales, support, services, IT, HR, etc., using a separate shared channel for each project doesn't scale well.  Shared Thread allows you to have the collaboration benefits of chat, with the scalability of email, since it also works at the thread level.  There is no limit to the number of external projects your team can handle, all from within the same internal channel.

## Instructions
### Add the app to your team
Got to the [Teams app store](https://teams.microsoft.com/l/app/33830d7f-553a-46ce-99b3-4dc436b28e45), and select the team you would like to add the app to.  The app only works in public channels, and it cannot be added to a group or personal chat.

Any member of the team can use the app.  Here is a [video demo](https://www.youtube.com/watch?v=-us4x9ADrhA) of using the app in Microsoft Teams.
{% include video id="-us4x9ADrhA" provider="youtube" %}

### Create a new thread
@mention the app followed by the command NewThread and the topic of the thread, e.g. `@Shared Thread by WNI NewThread Recruiting for Senior Pharmacist at Ballard site [Contoso HR - Rx Recruiters]`.  Putting the participants in brackets at end of the topic helps indicate who is part of the thread. This creates a new conversation/thread in the channel with the topic in the first message so it is easy to see what the thread is about.  A message with the instructions on how others can join will also be sent which includes the thread ID.  You can forward this to the other channel(s) you want to share the thread with by email, DM, or if you've already got another shared thread going with them, use that. 

Creating a new thread in Microsoft Teams:
![](/assets/images/NewThread.png)

### Join a thread
Another channel can join a shared thread by @mentioning the app followed by JoinThread and the thread ID, e.g. `@Shared Thread by WNI JoinThread 965cfd81-77bd-43d5-a4fc-c940ba800920`.  This creates a new conversation/thread in the participant's channel, with the same thread topic message as the one created in the host's channel.  Channels joining the shared thread can be in any team, in any organization.

Joining a thread from Microsoft Teams:

![](/assets/images/Join-from-Teams.png)

A message is sent to the shared thread to notify everyone that a channel has been added.  This shows up in the other participant's channel as follows:

![](/assets/images/added-to-channel.png)

### Reply to a thread
Reply to the shared thread and @mention the app followed by the message you want to share, for example: 

![](/assets/images/sender-reply.png)

The app will relay this message to the other participants in the shared thread, and it will be received as follows:

![](/assets/images/recipient-reply.png)

When you reply to a conversation/thread normally, i.e. without @mentioning the app first, the reply is not shared and is private to your channel.  This allows you to discuss the topic internally in the same thread, which enables you to keep your internal and external messages about a topic together in one thread.

Here is an example of some internal messages before replying to the shared thread:

![](/assets/images/internal-external-messages.png)

Only plain text messages can be sent, any formatting (e.g. **bold**, *italics*, [links](/), etc.) will be removed.  An @mention will be converted to the person's name in plain text. In the case of a [link](/), just the word "link" will be sent, so make sure to paste the link in plain text like https://www.some.link.

If you are pasting links to files in SharePoint, Microsoft Teams will automatically format them. If you send this as-is only the name of the file will be sent, which may be fine if you are using a shared folder for collaborating on files, e.g.

![](/assets/images/teams-formatted-links.png)

However, if you want to send the actual link, you need to edit the `Text to display` field to be the same as the address, as follows:

![](/assets/images/edit-text-to-display-link.png)

This will then provide a link that can be sent as follows:

![](/assets/images/link-in-plain-text-teams.png)

## Example uses
**Recruiting.**
Human Resources creates a shared thread for each new hire in its Recruiting channel, and invites the external recruiter's team assigned to the project, and the hiring department's selection team to join as participants.

**Sales.**
A sales team creates a shared thread for each prospect that requires pre-sales technical support.  This thread is then shared with the sales engineering channel, and the prospect's IT channel in charge of requirements.

**Support.**
The support team creates a shared thread for each new customer case and shares it with the customer's team.  This way the customer's entire team can easily participate in resolution of the case.

**Legal.**
Legal sets up a shared thread for each new client file it is working on and sends the ID to the client to join.  This allows a internal legal team discussions (e.g. among a partner and associate) to occur in the same thread as the messages with the client, making it easier to see the status of a file.  

## Pricing
### Free edition 
Shared threads only remain active for 30 days from the date they are created.  After that, the thread will not relay any new shared messages.  The thread remains usable for internal messages, and no messages are ever deleted.  

This 30 day time limit is waived until the Pro edition launches (see below).
### Pro edition
Coming soon.

Shared threads remain active with no time limit as long as the user who created them has an active subcription.

## Limitations
Some current limitations are as follows:

- *Only works in channels.*  Group and personal chats are not supported.

- *Plain text messages only.* Any formatting (e.g. **bold**, *italics*, [links](/), etc.) will be removed and the plain text version will be sent.  An @mention will be converted to the person's name in plain text. In the case of a [link](/), just the word "link" will be sent, so make sure to paste the link in plain text like https://www.wni.app/home.

- *No file or picture attachments.*  If you need to send an attachment, send a plain text link to the file instead.

- *No profile pictures or presence.*  These would be cool, but it is a bit of a privacy issue so we've left it out for now.

- *No reactions.*  You'll just have to reply with an old-school text emoji :)

## Architecture and Security

The [Azure Bot Service](https://azure.microsoft.com/en-us/services/bot-services/) is responsible for receiving messages from Microsoft Teams and passing them securely to the app's code running on the Azure App Service.

The app only sees messages that @mention it first, it does not have access to the other messages or files in a channel.

To help those with additional security requirements, we plan to offer the ability for organizations to self-host the app in their own Azure tenant.  If this is something you're interested in, please [let us know](../about/#contact-us).
