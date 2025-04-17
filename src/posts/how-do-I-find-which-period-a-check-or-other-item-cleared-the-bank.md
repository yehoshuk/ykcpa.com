---
title: "How Do I Find Which Period a Check or Other Item Cleared the Bank"
date: 2021-07-01T06:13:56-04:00
draft: false
tags: ["QuickBooks","bank-rec","check","reporting","workaround"]
categories: ["QB"]
hidedate: true
---
### Q:

I know the check number, payee, check date, etc. and I can easily find that information in QB. But I’m having trouble finding when that check cleared.

The example I have is that it’s now April 2021, and I check recipient just called up and said that she never cashed the check. It happens that I can still pull up this check at the bank (they let me do this for 18 months back), but they let me search only a 90 day range of dates at a time.

I need to know which month that check cleared so that I can go into the bank and pull up that date. QB will not tell me during which period I reconciled the check, and even the audit report doesn’t register a change when a check is clicked off, in a bank rec, as cleared.

How do I find the period that a check cleared the bank?
___
### A:

The trick is to change this reconciled transaction so that it will show up on the ‘Reconciliation Discrepancy’ report long enough for you to see in which period it cleared. After you have that info, remember to change it back so that you don’t actually have a reconciliation discrepancy left!

1.  Find the transaction that you need to figure out when it cleared
2.  Change the cleared transaction amount by $0.01 (really any amount works…)
3.  Go to Reports>Banking>Previous Reconciliation Discrepancy Report
4.  Select the reconciled account
        The modified transaction will appear on the discrepancy report, below the statement date that it was reconciled with

## IMPORTANT —>> Remember to change the transaction back to the cleared amount or the reconciliation will be out of balance!!! <<— IMPORTANT
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0NzczNTE0MzddfQ==
-->