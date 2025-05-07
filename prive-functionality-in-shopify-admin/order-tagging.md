# 🏷️ Order Tagging

{% hint style="info" %}
Recurly Commerceleverages Shopify checkout so both one-time purchases and subscription orders appear together in the “orders” page of Shopify. Recurly Commercetags subscription orders so that merchants may differentiate them from one-time purchases or use them for analytics. Recurly Commercedoes not tag one-time purchase orders.
{% endhint %}

Note: If you are a Pro or Enterprise merchant contact: **cs@tryprive.com** to inquire about custom tags.

### Subscription Tag Types

Depicted below are the 5 standard tags Recurly Commerceutilizes for subscription orders:

| Subscription order           | Tagged on every single subscription order. This tag can be used to differentiate a one-time purchase from a subscription order.                                                                                                                 |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Subscription order \<number> | Tagged on every subscription order. The initial subscription purchase will have the tag “Subscription order 1”. Ever order within the same subscription after will uptick the number. (i.e. “Subscription order 2” “Subscription order 3” etc.) |
| First time subscriber        | The first ever initial subscription purchase and subscriber for a merchant. Can be used to distinguish brand new subscribers. (Migrated customers will not have this tag.)                                                                      |
| Recurring subscription order | Tagged on every subscription order after the initial subscription purchase on checkout. Can be used to determine subscription renewal orders. This is a returning subscriber.                                                                   |
| Shipping Profile             | Tagged on every subscription order to depict the type of shipping the order should receive. (i.e. economy, free shipping, etc.)                                                                                                                 |

### Filter by Tags

In the Shopify orders section of your Shopify storefront, you can select the “filter” button to find and view orders that are assigned to specific tags.

1. Navigate to the Shopify orders page.
2. Select the “filter” button at the top of the page.
3. Select “tagged with” from the dropdown options.
4. Click the “select value” button and type in the tag you would like to find.
5. Add more than one tag to the filter to find comparisons of 2 or more tags.

### Video

Watch the video below to view order tag filtering

{% embed url="https://www.loom.com/share/5f9882b2fca94287b34bf53f93e37df2" %}
