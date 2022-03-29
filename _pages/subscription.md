---
permalink: /subscription/
title: 'Subscription'
---
<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-RD0D33XTR1"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-RD0D33XTR1');
</script>


Please click the link below to go to Microsoft Teams and activate your subscription.

<a id="deepLink" href="">Go to Teams</a>

<script>
    // get query param
    let subId = (new URL(document.location)).searchParams.get('subId');
    // create deep link 
    document.getElementById("deepLink").href = "https://teams.microsoft.com/l/chat/0/0?users=28:c7714737-5076-4766-abdd-de8a054960d8&message=" + "Please send this message to activate your subscription. |SubscriptionID|" + subId + "|";
    });
     
</script>

<!--

<script>
    gtag('get', 'G-RD0D33XTR1', 'client_id', (clientID) => {
    // get query param
    let subId = (new URL(document.location)).searchParams.get('subId');
    // create deep link 
    document.getElementById("deepLink").href = "https://teams.microsoft.com/l/chat/0/0?users=28:c7714737-5076-4766-abdd-de8a054960d8&message=" + "ClientID |" + clientID + "|" + subId + "|";
    });
     
</script>

-->