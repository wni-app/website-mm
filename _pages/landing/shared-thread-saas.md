---
permalink: /subscription/
title: "Activate Shared Thread Subscription"
---

Thanks for subscribing!

To activate your Shared Thread subscription, please click the link below. This will open Microsoft Teams with a pre-populated message containing your subscription ID - just click send.

<a id="deepLink" href="https://www.google.com">Activate Subscription in Microsoft Teams</a>

<script>

    // get query param
    let subId = (new URL(document.location)).searchParams.get('subId');
    console.log(subId);
    // create deep link 
    document.getElementById("deepLink").href = "https://teams.microsoft.com/l/chat/0/0?users=28:d8fcd2b6-8a0d-4b26-9cd1-8717a59b464a&message=" + encodeURIComponent("Please send us this message to activate your subscription. Sub_ID|" + subId + "|");
     
</script>
