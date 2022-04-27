---
permalink: /subscription/
title: 'Activate Subscription'
---
<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-RD0D33XTR1"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-RD0D33XTR1');
</script>


Thanks for subscribing!

To activate your subscription, please click the link below.

This will open Microsoft Teams with a pre-populated message containing your subscription ID - just click send.

<a id="deepLink" href="https://www.google.com">Activate Subscription in Microsoft Teams</a>

<script>

    // get query param
    let subId = (new URL(document.location)).searchParams.get('subId');
    // create deep link 
    document.getElementById("deepLink").href = "https://teams.microsoft.com/l/chat/0/0?users=28:d8fcd2b6-8a0d-4b26-9cd1-8717a59b464a&message=" + encodeURIComponent("Please send us this message to activate your subscription. Sub_ID|" + subId + "|");
     
</script>

<!--
 + "Please send this message to activate your subscription. |SubscriptionID|" + subId + "|"

<script>
    gtag('get', 'G-RD0D33XTR1', 'client_id', (clientID) => {
    // get query param
    let subId = (new URL(document.location)).searchParams.get('subId');
    // create deep link 
    document.getElementById("deepLink").href = "https://teams.microsoft.com/l/chat/0/0?users=28:c7714737-5076-4766-abdd-de8a054960d8&message=" + "ClientID |" + clientID + "|" + subId + "|";
    });
     
</script>

-->