---
permalink: /shared-thread/
title: "Shared Thread"
author_profile: true
author:
  name   : "Enables a channel to message another channel, in any organization."
  avatar : "/assets/images/fluent_share_xlarge.png"
  bio    : "Install app into Microsoft Teams or Slack using the following:"
  home   : /shared-thread/
  links:
    - label: "Microsoft Teams App Package"
      icon: "fas fa-cloud-download-alt"
      url: "SharedThread.zip"
    - label: "Add to Slack Workspace"
      icon: "fab fa-slack"
      url: "https://slack.com/oauth/v2/authorize?scope=chat%3awrite%2cchat%3awrite.customize%2capp_mentions%3aread%2cgroups%3aread%2cusers%3aread%2cusers.profile%3aread%2cchannels%3aread%2cteam%3aread&client_id=2537782468113.2859934187347&redirect_uri=https%3a%2f%2fslack.botframework.com%2fHome%2fauth%2fv2&state=SharedThread"

sidebar:
 - image: /assets/images/Microsoft Teams_500.png
   image_alt: "teams"
 - image: /assets/images/Slack-500.png
   image_alt: "slack"

toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
toc_sticky: true
---
Shares a thread between channels for inter-team collaboration, as an alternative to email or a shared channel.  It works like a conference bridge, but for messages: one channel starts the shared thread, and provides the thread ID for other channels to join.  Only replies to a shared thread that @mention the app are shared, all others remain private, so the same thread can be used for both internal and external conversation about a topic. The channels participating can be in any organization, and even on different messaging platforms.  As an example, HR could share a thread with an outside recruiting firm to discuss a hiring project instead of using email.

## Problems it solves

**Keeps internal and external project messages together.**  Currently, the internal conversation about a project is happening one channel, but the external conversation with another team about the same project is happening in either email or a separate shared channel.  To get a complete picture of what has been discussed about the project requires team members to piece together the messages from their internal channel with the external messages in email or a shared channel.  Using Shared Thread, a channel can share a thread that is used for both internal and external messages about a project, keeping everything together.  This improves productivity as everything is now in one place, and the external messages are interleaved chronologically with the internal messages.  Also, since both channels in the conversation benefit equally from this, it is easy to get others to adopt.

**Benefits of shared channels with the scalability of email.**  Shared channels help move external collaboration out of email and provide the benefits of a chat platform.  However, if your team is collaborating on dozens of external projects at once, as often happens in client-facing functions like sales, support, services, IT, HR, etc., using a separate shared channel for each project doesn't scale as well as email threads.  Shared Thread allows you to have the collaboration benefits of chat, with the scalability of email, since it also works at the thread level.  There is no limit to the number of external projects your team can handle, all from within the same internal channel. 

**Works between different messaging platforms.** Native shared channel features only work if everyone is on the same messaging platform, which means your team will often default to using email for interoperability.  Shared Thread works with multiple messaging platforms so you can keep more of your external collaboration in chat.

## Installation
This app is currently in preview, please [let us know](../about/#contact-us) if you find any bugs or things that could be better.

### Microsoft Teams
Depending on your Teams [org settings](https://docs.microsoft.com/en-us/microsoftteams/teams-custom-app-policies-and-settings), custom apps can be added by a team member, a team owner, or an org administrator.  If you don't see an *Upload a custom app* link in the lower left of your apps page as shown below, contact your administrator and provide them the link to the app package below.

![](/assets/images/upload a custom app.png)

**This is the Microsoft Teams [custom app package](./SharedThread.zip) you want to upload.**

Here is a video demo of installation in Teams:
{% include video id="BEvbhF2_AVM" provider="youtube" %}

### Slack
Any workspace member can add the app using [this link](https://slack.com/oauth/v2/authorize?scope=chat%3awrite%2cchat%3awrite.customize%2capp_mentions%3aread%2cgroups%3aread%2cusers%3aread%2cusers.profile%3aread%2cchannels%3aread%2cteam%3aread&client_id=2537782468113.2859934187347&redirect_uri=https%3a%2f%2fslack.botframework.com%2fHome%2fauth%2fv2&state=SharedThread).  The app then needs to be invited into each channel you wish to use it in.  

Here is a video demo of installation in Slack:
{% include video id="cvWUtogQUWM" provider="youtube" %}

## Usage
### Create a new thread
@mention the app followed by the command NewThread and the topic of the thread, e.g. @Shared Thread NewThread Recruiting for Senior Pharmacist at Ballard site [Contoso HR - Rx Recruiters].  Putting the participants in brackets at end of the topic helps indicate who is part of the thread. This creates a new conversation/thread in the channel with the topic in the first message so it is easy to see what the thread is about.  A message with the instructions on how others can join will also be sent which includes the thread ID.  You can forward this to the other channel(s) you want to share the thread with by email, DM, or if you've already got another shared thread going with them, use that. 

Creating a new thread from Teams:
![](/assets/images/NewThread.png)

### Join a thread
@mention the app followed by JoinThread and the thread ID you were given by the host, e.g. @Shared Thread JoinThread 965cfd81-77bd-43d5-a4fc-c940ba800920.  This creates a new conversation/thread in the participant's channel, with the same topic message as the one created in the host's channel.

Joining a thread from Teams:
![](/assets/images/Joining from Teams.png)

Joining a thread from Slack:
![](/assets/images/Joining from Slack.png)

Notice that a message from Denis, `I added a channel to this shared thread.`, was sent to the shared thread automatically to notify everyone that a channel had been added.  This shows up in the host's channel as follows:

![](/assets/images/added-to-channel.png)

### Reply to a thread
Reply to the shared thread and @mention the app followed by the message you want to share, e.g. @Shared Thread when are we meeting next?).  The app will forward this message to all participants in the shared thread, including the channel it was sent from to confirm receipt.  

Here is what it looks like in the sender's channel:

![](/assets/images/sender-reply.png)

Here is what it looks like in the other channel:

![](/assets/images/recipient-reply.png)

When you reply to a conversation/thread normally, i.e. without @mentioning the app first, the reply is not shared and is private to your channel.  This allows you to discuss the topic internally in the same thread, which enables you to keep your internal and external messages about a topic together in one thread.

Here is an example of internal messages before replying to the shared thread:

![](/assets/images/internal-external-messages.png)

Only plain text messages can be sent, any formatting (e.g. **bold**, *italics*, [links](/), etc.) will be removed.  An @mention will be converted to the person's name in plain text. In the case of a [link](/), just the word "link" will be sent, so make sure to paste the link in plain text like https://www.some.link.

If you are pasting links to files in SharePoint, Microsoft Teams will automatically format them. If you send this as-is only the name of the file will be sent, which may be fine if you are using a shared folder for collaborating on files, e.g.

![](/assets/images/teams-formatted-links.png)

However, if you want to send the actual link, you need to edit the `Text to display` field to be the same as the address, as follows:

![](/assets/images/edit-text-to-display-link.png)

This will then provide a link that can be sent as follows:

![](/assets/images/link-in-plain-text-teams.png)

Here is a demo of using the app:

{% include video id="X5wgT4VzlCM" provider="youtube" %}

## Example uses
**Recruiting.**
Human Resources creates a shared thread for each new hire in its Recruiting channel, and invites the external recruiter's team assigned to the project, and the hiring department's selection team to join.  

**Sales.**
A sales team creates a shared thread for each prospect that requires pre-sales technical support.  This thread is then shared with the sales engineering channel, and the prospect's IT  channel in charge of requirements.

**Support.**
The support team creates a shared thread for each new customer case and shares it with the customer's team.  This way the customer's entire team can easily participate in resolution of the case.

**Legal.**
Legal sets up a shared thread for each new client file it is working on and sends the ID to the client to join.  This allows a internal legal team discussions (e.g. among a partner and associate) to occur in the same thread as the messages with the client, making it easier to see the status of a file.  Clients also find this more useful than an email thread because they can discuss the case internally without having all the messages go to the legal team, which can be distracting and expensive.

## Pricing
Free while in preview.  

## Limitations
These are some of the current limitations of this app:

*Only works in channels.*  The reason for this is that group and personal chat in Microsoft Teams does not support conversations, so we need to implement a different threading model there.

*Plain text messages only.* Any formatting (e.g. **bold**, *italics*, [links](/), etc.) will be stripped off and the plain text version will be sent.  An @mention will be converted to the person's name in plain text. In the case of a [link](/), just the word "link" will be sent, so make sure to paste the link in plain text like https://www.wni.app/home.

*No file or picture attachments.*  If you need to send an attachment, send a link to the file (e.g. in SharePoint, etc.) as a plain text link as per the point above.

*No profile pictures.*  These would be cool, and it is technically possible, but it is a bit of a privacy issue so we've left it out for now.

*No presence.*  Not really technically practical, and again, it is a privacy issue.

*No reactions.*  We're planning to implement this at some point, as it would help easily acknowledge a message.  That is part of the reason the app repeats the message back to the sender, as there is no way to put a reaction on the sender's original message.

*No ability to leave or close a thread.*  Right now it is like an email thread in the sense that it lives on forever.  Yes, but wouldn't it be nice to close or leave an email thread?  So we might do something like this.

## Roadmap
These are some of the features we're considering on the roadmap.  If any of these evoke an "OMG, that is exactly what we need!" response, please [let us know](../about/#contact-us) and ideally why.

*Participant list.*  In the first message in a shared thread, the one that has the thread topic, we're thinking it would be useful if it had a list of the participants in the thread.  This would be updated each time a new participant joins.  A hack in the meantime is to put the intended participants in the topic.  As part of this we're thinking it would be good to have each channel provide an external name (e.g. Contoso HR Recruiting) to use in the participant list, since the internal channel name may be sensitive or not useful.

*Message only specific participants.*  Let's say you have a shared thread with two internal channels (e.g. Sales and Support), and a third channel which is the customer.  It would be convenient for Sales to be able to send a message to Support about the topic, and not the customer, without having to spin up a separate shared thread between just Sales and Support for that purpose.  We're not sure how many people would want to do this, but if that's you, please let us know.

*Not needing to @mention app.*  We realize @mentioning the app before each message to the shared thread becomes a bit tedious if there is a lot of back and forth.  The alternative is that we assume all replies to the shared thread are to be shared, and possibly only those marked as private (e.g. with a private emoji) are not sent.  This obviously increases the risk of something being shared that shouldn't, and to make this work our app would need permission to see ALL the messages in the channel.   But if these downsides are not concerns for your use case, please let us know.

*Join by email.*  Your team wants to use a shared thread to keep internal and external messages about a project together in your channel, but your client isn't using Teams or Slack, or is just stuck on email.  What if they could join the thread from email?  Obviously this is no better than email for them, but it enables your team to get the benefits of a shared thread.  A simple implementation:  Send an email to the app's email address with a JoinThread <threadId>.  The app replies back with an email with a subject set to the thread topic.  You then add the client to this email thread and ReplyAll.  Any subsequent replies to this email thread are now sent to the shared thread, and vice-versa.

## Architecture and Security
![](/assets/images/SharedThreadArch.png)

The basic flow of a message is as shown in the above diagram.  The [Azure Bot Service](https://azure.microsoft.com/en-us/services/bot-services/) is responsible for receiving messages from Microsoft Teams and Slack over a secure connection, and then passing them securely to the app's bot code which is running in the Azure App Service.

The app only sees messages that @mention it first, it does not have access to the other messages in a channel.  Also, any files attached to messages sent to the app are ignored.

To help those with additional security requirements, we plan to offer the ability for organizations to self-host the app in their own Azure tenant.  If this is something you're interested in, please [let us know](../about/#contact-us).

## Alternatives
We buy software also, and know how much of a pain it is to figure out what the alternatives are for products we are interested in, so maybe this will help.  

We're not aware of any alternatives for sharing threads between channels, and will update this if we find anything.

However, if you're looking to share an entire channel between Microsoft Teams and Slack, the [Mio](https://m.io/) app, and an open source project, [matterbridge](https://github.com/42wim/matterbridge/blob/master/README.md), look like good options to explore.