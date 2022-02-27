---
permalink: /saas-page/
title: 'Shared Thread Pro'
---
<script src="https://unpkg.com/@microsoft/mgt/dist/bundle/mgt-loader.js"></script>
<mgt-msal2-provider client-id="9ad1833b-af9f-4e29-9530-3d0612e8d98f"></mgt-msal2-provider>
<mgt-login></mgt-login>

Thank you for subscribing!

Please click the link below to go to Microsoft Teams and activate your subscription.

<a id="deepLink" href="https://wni.app/shared-thread/">Activate Subscription</a>
<p id="cid">replace with cid</p>

<script>
    // get query param
    let params = (new URL(document.location)).searchParams;
    let token = params.get('token');
    // set intro text
    var plainMsg = "Welcome to Shared Thread by WNI. To activate your subscription, please send this message unaltered. SubscriptionToken|" + token + "|";
    var encodedMsg = encodeURIComponent(plainMsg);
    // set message to append to deeplink with token
    // var message = dli + token + "|";
    var dl = document.getElementById("deepLink");    
    // Set the href property on link
    // dl.innerHTML = token;
    dl.href = "https://teams.microsoft.com/l/chat/0/0?users=28:9ad1833b-af9f-4e29-9530-3d0612e8d98f&message=" + encodedMsg; 

    ga(function(tracker) {
        var clientId = tracker.get('clientId');
    });

    document.getElementById("cid").innerHTML = clientId
    
</script>



<!--  use this if script is at top of page
window.onload = function() {
       //when the document is finished loading, replace everything
       //between the <a ...> </a> tags with the value of splitText
   document.getElementById("myLink").innerHTML=splitText;
} 

    var dli = document.getElementById("deepLinkIntro").innerHTML;
    var test = "some test text";

https://developer.mozilla.org/en-US/docs/Web/API/URL/searchParams#Example

<script src="https://unpkg.com/@microsoft/mgt/dist/bundle/mgt-loader.js"></script>
<mgt-msal2-provider client-id="9ad1833b-af9f-4e29-9530-3d0612e8d98f"></mgt-msal2-provider>
<mgt-login></mgt-login>
<mgt-person person-query="me" view="twoLines"></mgt-person>

https://saasacceleratorwni-portal.azurewebsites.net/?token=ebk87h9T9OPBY%2fYyV2APj20iFUYVZTYwTWdtd%2fcTNmQ6PLrsTIjKN6WqGDQbkLPxQ8nr7zcYlYufPxHFMVpzqlCsk7NtC2IO6Dyu7AdYGzSGiIuGRO29RdUB5Eq5s8%2b8jDqWU560ARtgQzCaZYWUmSzgx69mJe9funGb7z1qw0H9%2blvP3UDS3kazYMbLaX56Irz3fj2wYWm4H0qyd%2fm0htHfnA1wLORAacI%2bwupKuUo6WlZiYexshQw3Ry7bGGgE
-->
