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

// https://teams.microsoft.com/l/chat/0/0?users=28:0f65bd5f-d2d5-4b06-81fe-0986232f0c8a&message=Please%20send%20us%20this%20message%20to%20activate%20your%20subscription.%20Subscription%20Token%3A%20%7CwAOQ7RR6O44r4Wu5AssarblAuN1sZbnRXswN0mmz3NzvUvKKijHeD8eho6xdJVI9agegSjTI3%2BjEcn0RSogd8XAwpWePOKsaX87%2FUyvjSQVe9YSS3njPEj9VN0JznEd7EbAbd1ZdZ77SOFv%2F3FqXBOuULKDV98LtLhpVbldXKIDYQp038LB9oEAZ%2FwFe7boU68wkjMlaoPEn6pxiSChe6sX2clrXYEYapSsePpAf1Ib3XZehWTBGH2WAAeiNVU0V%7C

</script>
