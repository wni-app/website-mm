---
permalink: /receiptscan-saas/
title: "Activate ReceiptScan Subscription"
---

Please click the link below to activate your subscription.

This will open Microsoft Teams and pre-populate a message with your subscription code. Just click send and we'll respond to confirm your subscription details and activate the subscription.

<a id="deepLink" href="https://www.google.com">Activate subscription in Microsoft Teams</a>

<script>
  
    // get query param
    let token = (new URL(document.location)).searchParams.get('token');
    console.log(token);
    // create deep link 
    document.getElementById("deepLink").href = "https://teams.microsoft.com/l/chat/0/0?users=28:0f65bd5f-d2d5-4b06-81fe-0986232f0c8a&message=" + encodeURIComponent("Please send us this message to activate your subscription. Subscription Token: |" + token + "|");

</script>
