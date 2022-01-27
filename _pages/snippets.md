
**Works between Microsoft Teams and Slack.** Native shared channel features only work if everyone is on the same messaging platform, which means your team will often default to using email for interoperability.  Shared Thread can interoperate between Microsoft Teams and Slack, so you can keep more of your external collaboration in chat.

*Join by email.*  Your team wants to use a shared thread to keep internal and external messages about a project together in your channel, but your client isn't using Teams or Slack, or is just stuck on email.  What if they could join the thread from email?  Obviously this is no better than email for them, but it enables your team to get the benefits of a shared thread.  A simple implementation:  Send an email to the app's email address with a JoinThread <threadId>.  The app replies back with an email with a subject set to the thread topic.  You then add the client to this email thread and ReplyAll.  Any subsequent replies to this email thread are now sent to the shared thread, and vice-versa.

## Alternatives
We buy software also, and know how much of a pain it is to figure out what the alternatives are for products we are interested in, so maybe this will help.  

We're not aware of any alternatives for sharing threads between channels, and will update this if we find anything.

However, if you're looking to share an entire channel between Microsoft Teams and Slack, the [Mio](https://m.io/) app, and an open source project, [matterbridge](https://github.com/42wim/matterbridge/blob/master/README.md), look like good options to explore.

## Roadmap
These are some of the features we're considering on the roadmap.  If any of these are things you'd like to see, please [let us know](../about/#contact-us) and ideally why.

*Leave or close a thread.*  Right now it is like an email thread in the sense that it lives on forever and people can continue to reply to it.  However, it might be nice to close or leave a thread.

*Participant list.*  In the first message in a shared thread, the one that has the thread topic, we're thinking it would be useful if it had a list of the participants in the thread.  This would be updated each time a new participant joins.  A hack in the meantime is to put the intended participants in the topic.  As part of this we're thinking it would be good to have each channel provide an external name (e.g. Contoso HR Recruiting) to use in the participant list, since the internal channel name may be sensitive or not very descriptive.

*Message only specific participants.*  Let's say you have a shared thread with two internal channels (e.g. Sales and Support), and a third channel which is the customer.  It would be convenient for Sales to be able to send a message to Support about the topic, and not the customer, without having to spin up a separate shared thread between just Sales and Support for that purpose.  We're not sure how many people would want to do this, but if that's you, please [let us know](../about/#contact-us).

*Not needing to @mention app.*  We realize @mentioning the app before each message to the shared thread becomes a bit tedious if there is a lot of back and forth.  The alternative is that we assume all replies to the shared thread are to be shared, and possibly only those marked as private (e.g. with a private emoji) are not sent.  This obviously increases the risk of something being shared that shouldn't, and to make this work our app would need permission to see ALL the messages in the channel.   But if these downsides are not concerns for your use case, please [let us know](../about/#contact-us).

### Slack
Any workspace member can add the app using [this link](https://slack.com/oauth/v2/authorize?scope=chat%3awrite%2cchat%3awrite.customize%2capp_mentions%3aread%2cgroups%3aread%2cusers%3aread%2cusers.profile%3aread%2cchannels%3aread%2cteam%3aread&client_id=2537782468113.2859934187347&redirect_uri=https%3a%2f%2fslack.botframework.com%2fHome%2fauth%2fv2&state=SharedThread).  The app then needs to be invited into the channel.  

Joining a thread from Slack:

![](/assets/images/Join-from-Teams.png)