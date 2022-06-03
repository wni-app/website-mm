---
permalink: /receiptscan/
title: "ReceiptScan"
author_profile: true
author:
  name   : "Extracts data from a picture of a receipt."
  avatar : "/assets/images/ReceiptScan-main-fs.png"
  bio    : "[Join Beta](/support/)"
  home   : /receiptscan/

toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
toc_sticky: true
---
## Overview
Streamline expense reporting by extracting the merchant, location, date, and purchase amounts from a picture of a receipt sent to the app.  The app will respond with a form containing the extracted values which you can edit and add any comments.  The final values are then sent to your email where you can either use an inbox rule to forward them to your bookkeeper, or trigger a workflow (e.g. Power Automate, Zapier, etc.) to send the data into a spreadsheet, accounting software, etc.  The first 100 receipts are free, after which you can purchase a subscription.

## Benefits

* Quickly record receipts by simply taking a picture of them while you are travelling.
* Makes receipts searchable in Teams and email (e.g. search by merchant name).  

## Demonstration

[Demo Video for iOS](https://youtu.be/07L57PdiADM)

[Demo Video for web/desktop](https://youtu.be/rbPN0T01TsQ)

Example receipts to use for testing/demo purposes:

[Example Receipt 1](/_pages/receiptscan/contoso.png)

[Example Receipt 2](/_pages/receiptscan/main-st.JPG)

[Example Receipt 2](/_pages/receiptscan/main-st.JPG)

## Instructions

### Send a receipt picture

* Mobile: Tap the photo icon next to the message compose box to take/select a picture of your receipt.
* Desktop/Web:  Copy and paste a receipt picture into the compose box, do not attach as a file.
* Note: Send only one receipt image per message.

### Process receipt email
* Inbox rule: Move messages to a receipts inbox folder and optionally forward a copy to your bookkeeper.
* Power Automate: Email body only contains JSON of receipt values, simply parse and push values into a spreadsheet, accounting software, etc.
* In both cases you can trigger your workflow on new messages from receiptscanner@wni.app.

## Pricing

Free version can process up to 100 receipts total.

The Pro version can process unlimited receipts.


## Limitations

* Personal chat only, no channels or groups.

## Version History

* 1.0.0 - initial release
