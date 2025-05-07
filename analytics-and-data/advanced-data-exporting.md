---
description: Export all your important subscription data easily into a CSV
---

# ⬇️ Advanced Data Exporting

{% hint style="info" %}
Recurly Commerceoffers advanced data exports in both the “Subscription Contracts” tab and the “Settings” tab of the Recurly Commerceapp. These exports depict all subscriber data from names, emails, billing and shipping addresses, frequencies, next order dates, and more.
{% endhint %}

## Reports Available for Export Overview

Navigate to "Settings" in the side navigation of your Recurly Commerceadmin account. Scroll to the bottom of the settings page to see reports available for export.&#x20;

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

Select one or more reports on the right hand side to export the report as a CSV.  To understand what data is contained in each report, click on the report name in the "Reports Detailed Description" panel.&#x20;

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

Reports are broken down into **General** and **Historical** reports.&#x20;

### General Reports&#x20;

General reports include data that reflects the current state of your subscription business:&#x20;

<details>

<summary>All subscription contracts </summary>

* Contains a list (current snapshot) of all of your subscription contracts
* Each row represents a unique contract that has a unique contractId. Each row has the associated email and customerId of who purchased the contract and a tonne of metadata like when the next order will be placed, the delivery and billing cadences etc.
* Contracts create orders according to the delivery cadence.

</details>

<details>

<summary>Subscription contracts product breakdown </summary>

* Contains a detailed breakdown of each of the products in the contract (e.g. what skus were purchased, the quantity etc.)
* Each row represents a contract line item (each contract line item is associated with a sku). A contact (contractId) can have multiple products hence multiple contract line items (contractLineId)
* You can use this to answer questions like how many of my subscribers are subscribed to a specific sku and on what cadence. What is my most popular sku on subscription

</details>

### Historical Reports

Historical reports include source of truth data on what has occured or been processed in the past. Select the date range of data you want to analyze prior to downloading:&#x20;

<details>

<summary>Orders (Historical) </summary>

* Contains a list of orders that were placed through the Recurly Commercesystem.
* Each row represents a unique order as per orderId. Each order is associated with a contract.
* You can calculate things like AOV by averaging over the chargeAmount (where chargeAmount = price+shipping+tax). The chargeAmount is the total amount the customer was charged for the order

</details>

<details>

<summary>Subscription Contract Activity (Historical) </summary>

* Each row represents an event (event\_id) that happened on the contract (contractId).

- Helps you answer historical questions like when a contract was created and when it was canceled.
- You can order the data by contractId and by timestamp to get a list of events that happened to that contract

</details>

<details>

<summary>Subscription Contract Detailed Activity (Historical) </summary>

* Similar to Subscription Contact Activity but contains more events such as when the user paused or skipped etc.
* You can group the data by subscriptionContractId and sort by timestamp to get a list of actions that happened to that contract
* Flag that detailed events like swapping or pausing or skipping are only available after April 29th 2022 (when we launched the activity feed feature). But you can always rely on the contract\_event table to answer when a contract was started or cancelled.

</details>

<details>

<summary>Cancellation Survey (Historical) </summary>

* List of cancellation from shoppers that contains the reason and others fields.

</details>

<details>

<summary>Retention Strategy Results (Historical) </summary>

* List of retention strategies accepted from shoppers that contains the reason and others fields.

</details>

<details>

<summary>Billing Failures (Historical) </summary>

* List of billing failures from contracts that contains the error message and others fields.

</details>
