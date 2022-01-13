---
permalink: /shared-thread/
title: "Shared Thread"
author_profile: true
author:
  name   : "Share a thread between messaging channels"
  avatar : "/assets/images/fluent_share_xlarge.png"
  bio    : "Message people outside your channel on Microsoft Teams or Slack, as easy as setting up a conference bridge.  \n\nInstall using:"
  home   : /shared-thread/
  links:
    - label: "Microsoft Teams App Package"
      icon: "fas fa-cloud-download-alt"
      url: "https://drive.google.com/uc?export=download&id=1dzondjw5hJJ_zXf5IYbL8zI_xoywpMUt"
    - label: "Add to Slack Workspace"
      icon: "fab fa-slack"
      url: "https://slack.com/oauth/v2/authorize?scope=chat%3awrite%2cchat%3awrite.customize%2capp_mentions%3aread%2cgroups%3aread%2cusers%3aread%2cusers.profile%3aread%2cchannels%3aread%2cteam%3aread&client_id=2537782468113.2859934187347&redirect_uri=https%3a%2f%2fslack.botframework.com%2fHome%2fauth%2fv2&state=SharedThread"

toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
---
## Problems it solves
Shared Thread is an app that enables a thread to be shared between channels in Microsoft Teams or Slack.  For example, a sales channel at a vendor could share a thread with a purchasing channel at a prospect about a deal being negotiated.  It is an alternative to using email or a shared channel for external collaboration, with the following benefits:  

**Keeps internal and external messages about a topic together.**  Currently, getting a complete picture of a project requires team members to piece together the messages in an internal channel with the external client messages in either an email thread or shared channel.  Using Shared Thread, a team can use a single thread for both internal and external messages about a topic.  This is possible because on only replies to the thread that @mention the app first are shared, all other normal replies remain private to the channel.

**It scales effortlessly to a large number of projects.**  When a team needs to handle 50-100+ external projects at a given time (e.g. sales, support, services, IT, HR, etc.), doing this with a shared channel for each becomes unwieldy,  and may cause a team to reach the Microsoft Teams channel limit.  There is no limit to the number of shared threads that can be created in a channel, and there is no drop in usability.

**Works between Microsoft Teams and Slack.**  Shared channels based on Microsoft Teams Connect or Slack Connect only work with participants on the same platform (e.g. Teams-to-Teams or Slack-to-Slack).  Shared Thread will work with any combination of channels on Microsoft Teams or Slack.  Although this cross platform interoperability is a clear benefit, many users find the first two benefits above are even more important.

## Use Cases
Here are some examples:

Recruiting - Human Resources creates a shared thread for each new hire in its Recruiting channel, and invites the external recruiter's team assigned to the project, and the hiring department's selection team to join.  This enables all three teams to discuss the new hire internally to their team, and message the shared thread as needed.

Sales - A vendor's sales team creates a shared thread for each prospect that reaches a certain deal stage (e.g. prospect requires technical pre-sales support).  This thread is then shared with the Sales Engineering channel, the prospect's Purchasing channel,  and the prospect's requesting department (e.g. IT).  This enables all the groups to collaborate on the deal both internally and externally.

Support - The support team creates a shared thread for each new customer case and provides the ID back to the customer if they wish to join from Microsoft Teams or Slack.  This enables the customer to loop their entire team into the conversation as needed.

Legal - Legal sets up a shared thread for each new client file it is working on and sends the ID to the client to join.  This allows a internal legal team discussions (e.g. among a partner and associate) to occur in the same thread as the messages with the client, making it easier to see the status of a file.  Clients also find this more useful than an email thread because they can discuss the case internally without having all the messages go to the legal team, which can be distracting and expensive.
