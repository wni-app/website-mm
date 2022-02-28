---
permalink: /landing/
title: 'Landing'
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
    gtag('get', 'G-RD0D33XTR1', 'client_id', (clientID) => {
    document.getElementById("deepLink").href = "https://teams.microsoft.com/l/chat/0/0?users=28:c7714737-5076-4766-abdd-de8a054960d8&message=" + "ClientID |" + clientID + "|";
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