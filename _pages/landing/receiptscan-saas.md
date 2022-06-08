---
permalink: /receiptscan-saas/
title: "Activate ReceiptScan Subscription"
---

<script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>

Please click the link below to activate your subscription.

This will open Microsoft Teams and pre-populate a message with your subscription code - just click send and we'll respond with your subscription details to confirm, and then you can activate the subscription. You will have 72 hours to cancel your subscription with no charges to your credit card.

<a id="deepLink" href="https://www.google.com">Activate subscription in Microsoft Teams</a>

<script>
  
    // get query param
    let subId = (new URL(document.location)).searchParams.get('subId');
    console.log(subId);
    // create deep link 
    document.getElementById("deepLink").href = "https://teams.microsoft.com/l/chat/0/0?users=28:6a8ef52d-c089-450c-a1d6-f959eb0948c6&message=" + encodeURIComponent("Please send us this message to activate your subscription. Sub_Id|" + subId + "|");

</script>

<!--

// let _sub = (new URL(document.location)).searchParams.get('_sub');
    // console.log(_sub);
    // let subUrl = `https://monastoragejixuxogwmzgyg.blob.core.windows.net${_sub}`
    // async function getBlob (subUrl){
    //   const response = await axios.get(subUrl);
    //   console.log(response);
    // }
    // getBlob (subUrl);

-->
