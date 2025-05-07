# 💸 Managing payment failures & dunning

### What is Dunning?

Dunning is an automated payment management process that allows a merchant to set up retries for failed payment methods on a specific frequency and send reminders about an outstanding due from a declined payment method.

### Dunning Configuration

Recurly Commerce offers configuration of the Dunning process in the “Settings” tab of the Recurly Commerce portal. Merchants may choose from 3 Dunning options to implement for their subscribers and can choose whether contracts go into a paused or cancelled state once dunning is complete:

1. **Prive’s Standard Dunning Setting**:

Subscription contracts will be automatically canceled when they complete dunning with this setting. The subscriber’s payment method will be retried every 2 days for a maximum of 5 times.

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

2. **Retry-After Failed Billing:** Merchants can choose the number of days and the number of retires a subscriber’s payment method will be retried **after** the expected renewal date. Merchants can also choose whether contracts will be paused or canceled once dunning is complete.

<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

3. **Retry Before Failed Billing:** Merchants can choose the number of days and the number of retires a subscriber’s payment method will be retried before the expected renewal date. Merchants can also choose whether contracts will be paused or canceled once dunning is complete.

<figure><img src="../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

### Payment Failure Notification

The “**Failed payment method”** communication is a highly recommended transactional notification that can be configured on in the notifications tab of the Recurly Commerce app. This comm notifies customers when their order could not be placed due to a payment failure and includes a link to their customer portal where the customer can login and reset their billing information.

<figure><img src="../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

### Reset Billing Information

As a merchant, while you cannot reset the billing information for the subscriber, you can navigate to the “customers” tab, select the subscriber in question, scroll down to the “Billing & Shipping” section of the subscription contract, and select the “send email to reset” button.

This action will send an email to the subscriber where they will click a link that redirects them to update their billing information with Shopify payments. This will automatically update in the Recurly Commerce system.

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

### Process Failed Payment

Once the failed payment has been updated, as a merchant, you can select the “process now” button in the subscription contract of the subscriber in question. This will immediately charge their payment method and if the transaction is successful, the next order will renew immediately. Selecting “process now” will not interrupt the future renewal dates of the contract.

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>
