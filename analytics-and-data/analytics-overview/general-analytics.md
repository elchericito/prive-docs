---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# General Analytics

The General tab of Recurly CommerceAnalytics shows a summary of key information which allows you to drill deeper into the data. For all data, you are able to select custom windows of time and compare the data to previous periods of time.&#x20;

**Total Gross Sales During Selected Period**

<figure><img src="../../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

View a chart of how your subscription gross sales have changed over time. The dotted line shows what your gross sales looked like during the previous period of comparison so you can see how your current sales track against previous history.

**Average Order Value**

![](<../../.gitbook/assets/image (31).png>)

Average dollar amount of subscription orders (includes the initial subscription purchase). See how your subscription cart size changes over time.

**Subscription Orders Processed**

![](<../../.gitbook/assets/image (41).png>)

## Monthly Executive Report

The Monthly Executive Report is a tabular view that allows you to understand the key KPIs of your subscription business. The following are definitions for each row of data:

<details>

<summary><strong>Gross Subscription Sales</strong></summary>

Total gross sales (in merchant local currency, including tax and shipping) from subscription orders

</details>

<details>

<summary>Subscription Sales (from first orders)</summary>

Total gross sales (including tax and shipping) from the initial subscription purchase order

</details>

<details>

<summary>Subscription Sales (from recurring orders)</summary>

Total gross sales (including tax and shipping) from recurring subscription orders. This does not include sales from the initial subscription purchase.

</details>

<details>

<summary>Subscription Orders</summary>

The number of orders that have been processed in the month (includes initial subscription order as well as renewals).

</details>

<details>

<summary><strong>Gross Subscription Sales (from one-time add-ons)</strong> </summary>

Sum of gross sales from one-time add-on items in the subscriptions.

</details>

<details>

<summary><strong>Subscription Orders (with one-time add-ons)</strong> </summary>

Sum of number of subscription orders that include one-time add-on items.

</details>

<details>

<summary><strong>New Subscriptions</strong></summary>

The number of new subscription orders that have been processed in the month (does not include any subscription renewals).

</details>

<details>

<summary>New Migrated Subscriptions </summary>

Sum of new subscriptions that were migrated to Recurly Commercefrom other providers.

</details>

<details>

<summary><strong>New Subscribers</strong></summary>

The number of shoppers who have purchased a new subscription in the month.

</details>

<details>

<summary>New Migrated Subscribers </summary>

Sum of new subscribers who were migrated to Recurly Commercefrom other providers

</details>

<details>

<summary>Active Subscriptions (including paused &#x26; dunning) (ending)</summary>

The number of active subscriptions at the end of the month, including subscriptions that have been paused or are in dunning (period of time where payment has failed, but system retries payment).

</details>

<details>

<summary>Cancelled Subscriptions (ending)</summary>

The number of subscriptions at the end of the month that are in a canceled state. This does not include paused subscriptions or subscriptions that are in dunning. Cancelled Subscriptions consist of subscriptions that have been actively cancelled, have been cancelled due to failed payments, or have been migrated into Recurly Commerceas a cancelled subscription.

</details>

<details>

<summary>Actively Cancelled Subscriptions (ending)</summary>

The number of subscriptions at the end of the month that have been cancelled by the customer or by the merchant by clicking on “cancel subscription” in the Recurly Commerceportal/merchant admin.

</details>

<details>

<summary>Passively Cancelled Subscriptions (ending)</summary>

The number of subscriptions at the end of the month that have been cancelled because they have had a failed payment method, gone through dunning management, and payment was not updated. See your dunning management settings to configure your policy on whether or not a subscription gets cancelled after failed payment attempts.

</details>

<details>

<summary><strong>Migrated Cancelled Subscriptions (ending)</strong> </summary>

Total subscriptions that were migrated to Recurly Commercefrom other providers as cancelled.

Helps answer: "At the end of the month, how many migrated cancelled subscriptions did we have?"

</details>

<details>

<summary>Paused Subscriptions (ending)</summary>

The number of subscriptions at the end of the month that are in a paused state. Depending on your store configuration, customers may have paused for an indefinite period of time (only will unpause if an action to unpause is taken), or for a specific period of time (i.e 3 renewals), at which point they will automatically unpause. See Customer Portal tab to configure your pause settings.

</details>

<details>

<summary>Failed/Dunning Subscriptions (ending)</summary>

The number of subscriptions at the end of the month that are in a failed state and are going through active dunning management. These are subscriptions where the system tried to process payment at the time of renewal and failed to do so (generally due to expired credit cards, insufficient funds, etc). If a customer updates their payment method, the subscription will become active and will no longer be in a failed state.

</details>

<details>

<summary>All Subscriptions (ending)</summary>

The total number of subscriptions at the end of the month. The sum of Active Subscriptions (including paused & dunning) and Cancelled Subscriptions.

</details>

<details>

<summary>Active Subscribers (including paused &#x26; dunning) (ending)</summary>

Total number of subscribers at the end of the month with at least 1 active, paused, or dunning subscription. The number of active subscribers can be lower than active subscriptions since a subscriber can have multiple active subscriptions under the same email/account.

</details>

<details>

<summary>Churned Subscribers (ending)</summary>

Total number of subscribers with 0 active, paused, or dunning subscriptions at the end of the month.

</details>

<details>

<summary>Actively Churned Subscribers (ending)</summary>

Total number of subscribers who churned as a result of them, or the merchant, directly cancelling their subscriptions, at the end of a month.

</details>

<details>

<summary>Passively Churned Subscribers (ending)</summary>

Total number of subscribers who churned as a result of their subscriptions being passively cancelled, at the end of the month.

</details>

<details>

<summary>All Subscribers (ending)</summary>

All Subscribers (ending) = Active Subscribers (including paused & dunning) (ending) + Churned Subscribers (ending)

</details>

## Subscription Daily Summary&#x20;

<figure><img src="../../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

The Subscription Daily Summary provides a day by day breakdown for all of the subscription metrics found in the Executive Report. For metric definitions, see "Monthly Executive Report" above.&#x20;

## Subscriber Daily Summary&#x20;

<figure><img src="../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

The Subscriber Daily Summary provides a day by day breakdown for all of the subscriber related metrics found in the Executive Report. For metric definitions, see "Monthly Executive Report" above.&#x20;

{% hint style="info" %}
All data is shown in the timezone of your store and may differ from Shopify's analytics timezone and data aggregation cutoffs. Shopify and Recurly Commerceanalytics will not match 1-1 due to different policy decisions. This does not mean the data from either source is incorrect.&#x20;
{% endhint %}
