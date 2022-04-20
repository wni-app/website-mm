---
permalink: /add-relay/
title: 'Add Relay app to Microsoft Teams'
---
<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-RD0D33XTR1"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-RD0D33XTR1');
</script>


Please click the link below to add Relay to Microsoft Teams.

This will open Microsoft Teams and pre-populate a message with a registration code - just click send.

<a id="deepLink" href="">Add Relay to Microsoft Teams</a>

<script>

    gtag('get', 'G-RD0D33XTR1', 'client_id', (clientID) => {
    document.getElementById("deepLink").href = "https://teams.microsoft.com/l/chat/0/0?users=28:84ffaaf8-79ee-4e23-9b03-176c29bcf55b&message=" + "To register for the Relay app, please send this message.  UP_ID|" + clientID + "|";
    });
     
</script>

<!--
   document.getElementById("deepLink").innerHTML = test
    // document.getElementById("cid").innerHTML = test
    // document.getElementById("cid").innerHTML = clientID;
    let params = encodeURIComponent((new URL(document.location)).searchParams.toString()+
    "&referrer="+document.referrer);

    var msg = "Here is the cid:|" + client_id + "|";

-->