# 👩‍💻 Widget API Documentation

### Links

* [Shopify Subscription Documentation](https://shopify.dev/apps/subscriptions)
* Selling Plan Fields: [https://shopify.dev/api/admin-graphql/2022-07/objects/sellingplan](https://shopify.dev/api/admin-graphql/2022-07/objects/sellingplan)

### Liquid Objects

Prive subscription related data is available in Shopify liquid template objects

* [Product](https://shopify.dev/api/liquid/objects#product)
* [Selling Plan](https://shopify.dev/api/liquid/objects#selling_plan)

### Product Details

Gets the product information for a given productId

```
method GET
https://subs.api.tryprive.com/stores/${storeUrl}/products/${productId}/new
```

#### Selling Plan Groups

Represents a selling method (for example, "Subscribe and save" or "Pre-paid").

| Field                   | Description                                                                    | Value                                                                                                                       |   |
| ----------------------- | ------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------- | - |
| productId               | Shopify Product ID                                                             |                                                                                                                             |   |
| hasVariantLevel         | boolean that indicates whether the product has any product variants available. |                                                                                                                             |   |
| requires\_selling\_plan | Whether the product has subscription offers available.                         |                                                                                                                             |   |
| variants                | Product variants                                                               |                                                                                                                             |   |
| type                    |                                                                                | “ONETIME\_AND\_SUBSCRIPTION\_AND\_PREPAID”, “ONETIME\_AND\_SUBSCRIPTION”,"PREPAID\_SUBSCRIPTION\_ONLY, “SUBSCRIPTION\_ONLY” |   |

#### Selling Plan

Represents how a product can be sold and purchased.

| Field                   | Description                                                                                                             | Value                                                                                                                                                                   |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| specialDiscountActive   | Whether the subscription has any discount available                                                                     | boolean                                                                                                                                                                 |
| specialDiscount         | Discount amount                                                                                                         | number                                                                                                                                                                  |
| discountType            | Description: By Quantity, By Orders or Free Shipping                                                                    | “ORDER”, “QUANTITY”                                                                                                                                                     |
| specialDiscountModifier | The unit of the special discount                                                                                        | “PERCENTAGE”, “AMOUNT”, “FIXED\_AMOUNT”                                                                                                                                 |
| numberOfOrders          | Number of orders of the selling plan                                                                                    | number                                                                                                                                                                  |
| shippingDiscount        | discount applied to the shipping (free shipping)                                                                        | { active: boolean; countries: { all: boolean; countries: null; }; requirements: { type: string; amount: number; }; numberOfOrders: null; }                              |
| specialDiscountType     | Type of the special discount                                                                                            | 'QUANTITY', 'SHIPPING', 'ORDER', 'NONE'                                                                                                                                 |
| discount                | Amount of the discount                                                                                                  | number                                                                                                                                                                  |
| discountModifier        | The unit of the discount                                                                                                | “PERCENTAGE”, “AMOUNT”, “FIXED\_AMOUNT”                                                                                                                                 |
| optionOrder             | The order of the selling plan relative to the other selling plans (in which position of the dropdown it should show up) | number                                                                                                                                                                  |
| deliveryCadenceCount    | Delivery frequency (if it’s delivered every 2 weeks, then it’s 2).                                                      | number                                                                                                                                                                  |
| deliveryCadenceUnit     | Delivery frequency unit (if it’s every 2 months, then it’s “MONTH”)                                                     | 'DAY', 'MONTH', 'WEEK', 'YEAR'                                                                                                                                          |
| billingCadenceCount     | Billing frequency (if it’s every 2 weeks, then it’s 2)                                                                  | number                                                                                                                                                                  |
| billingCadenceUnit      | Billing frequency unit (if it’s every 2 weeks, then it’s “WEEK”)                                                        | 'DAY', 'MONTH', 'WEEK', 'YEAR'                                                                                                                                          |
| name                    | The default name of the selling plan, displayed in the widget subscription offer options dropdown.                      | string                                                                                                                                                                  |
| nameOverride            | The custom name of the selling plan, displayed in the widget subscription offer options dropdown.                       | string                                                                                                                                                                  |
| visibility              |                                                                                                                         | Array ('MERCHANT\_CONTRACT', 'STOREFRONT', 'SHOPPER\_CONTRACT', 'OFFER')                                                                                                |
| isDefault               | Indicates whether the selling plan should be selected by default                                                        | boolean                                                                                                                                                                 |
| discountCode            | Discount code available for the selling plan.                                                                           | string                                                                                                                                                                  |
| type                    | The selling group type                                                                                                  | 'ONETIME\_AND\_SUBSCRIPTION', 'ONE\_TIME\_AND\_PREPAID\_SUBSCRIPTION', 'SUBSCRIPTION\_ONLY', 'PREPAID\_SUBSCRIPTION\_ONLY', 'ONETIME\_AND\_SUBSCRIPTION\_AND\_PREPAID', |
| optionType              | Type of the selling plan, Note: use when type is “ONETIME\_AND\_SUBSCRIPTION\_AND\_PREPAID”                             | 'ONETIME\_AND\_SUBSCRIPTION', 'ONE\_TIME\_AND\_PREPAID\_SUBSCRIPTION', 'SUBSCRIPTION\_ONLY', 'PREPAID\_SUBSCRIPTION\_ONLY', 'ONETIME\_AND\_SUBSCRIPTION\_AND\_PREPAID', |
| giftOptions             | Contains the maximum number of deliveries for the gift purchase option                                                  | { maxDeliveries: number }                                                                                                                                               |
| sellingPlanGroupId      | Selling plan id from shopify                                                                                            | string                                                                                                                                                                  |

#### Prepaid - Example

```jsx
{
    "productId": "gid://shopify/Product/7604549058805",
    "hasVariantLevel": false,
    "selling_plan_groups": [
        {
            "requires_selling_plan": true,
            "id": "gid://shopify/SellingPlanGroup/628818165",
            "type": "PREPAID_SUBSCRIPTION_ONLY",
            "variants": [],
            "selling_plans": [
                {
                    "variants": null,
                    "specialDiscountActive": true,
                    "specialDiscount": 12,
                    "discountType": "QUANTITY",
                    "specialDiscountModifier": null,
                    "numberOfOrders": 3,
                    "shippingDiscount": null,
                    "specialDiscountType": "QUANTITY",
                    "sellingPlanGroupId": "gid://shopify/SellingPlanGroup/628818165",
                    "sellingPlanId": "3192750325",
                    "discount": 4,
                    "discountModifier": "PERCENTAGE",
                    "optionOrder": null,
                    "deliveryCadenceCount": 2,
                    "deliveryCadenceUnit": "MONTH",
                    "billingCadenceCount": 12,
                    "billingCadenceUnit": "MONTH",
                    "type": "PREPAID_SUBSCRIPTION_ONLY",
                    "name": "Delivery every 2 months, prepay every 12 months - 4% off",
                    "nameOverride": "Name Custom Discount",
                    "visibility": null,
                    "isDefault": false,
                    "discountCode": null,
                    "optionType": "PREPAID_SUBSCRIPTION_ONLY",
                    "giftOptions": null
                },
                {
                    "variants": null,
                    "specialDiscountActive": true,
                    "specialDiscount": 12,
                    "discountType": "QUANTITY",
                    "specialDiscountModifier": null,
                    "numberOfOrders": 3,
                    "shippingDiscount": null,
                    "specialDiscountType": "QUANTITY",
                    "sellingPlanGroupId": "gid://shopify/SellingPlanGroup/628818165",
                    "sellingPlanId": "3192881397",
                    "discount": 15,
                    "discountModifier": "PERCENTAGE",
                    "optionOrder": null,
                    "deliveryCadenceCount": 1,
                    "deliveryCadenceUnit": "MONTH",
                    "billingCadenceCount": 12,
                    "billingCadenceUnit": "MONTH",
                    "type": "PREPAID_SUBSCRIPTION_ONLY",
                    "name": "Delivery every 1 month, prepay every 12 months - 15% off",
                    "nameOverride": "1m X 12 months",
                    "visibility": null,
                    "isDefault": false,
                    "discountCode": null,
                    "optionType": "PREPAID_SUBSCRIPTION_ONLY",
                    "giftOptions": null
                },
                {
                    "variants": null,
                    "specialDiscountActive": true,
                    "specialDiscount": 12,
                    "discountType": "QUANTITY",
                    "specialDiscountModifier": null,
                    "numberOfOrders": 3,
                    "shippingDiscount": null,
                    "specialDiscountType": "QUANTITY",
                    "sellingPlanGroupId": "gid://shopify/SellingPlanGroup/628818165",
                    "sellingPlanId": "3193012469",
                    "discount": 24,
                    "discountModifier": "PERCENTAGE",
                    "optionOrder": null,
                    "deliveryCadenceCount": 3,
                    "deliveryCadenceUnit": "MONTH",
                    "billingCadenceCount": 6,
                    "billingCadenceUnit": "MONTH",
                    "type": "PREPAID_SUBSCRIPTION_ONLY",
                    "name": "Delivery every 3 months, prepay every 6 months - 24% off",
                    "nameOverride": null,
                    "visibility": null,
                    "isDefault": false,
                    "discountCode": null,
                    "optionType": "PREPAID_SUBSCRIPTION_ONLY",
                    "giftOptions": null
                }
            ]
        }
    ]
}
```

#### One-time, Subscribe & Save, Prepaid - Example

```jsx
{
    "productId": "gid://shopify/Product/7604549058805",
    "hasVariantLevel": false,
    "selling_plan_groups": [
        {
            "requires_selling_plan": false,
            "id": "gid://shopify/SellingPlanGroup/633340149",
            "type": "ONETIME_AND_SUBSCRIPTION_AND_PREPAID",
            "variants": [],
            "selling_plans": [
                {
                    "variants": null,
                    "specialDiscountActive": false,
                    "specialDiscount": null,
                    "discountType": "NONE",
                    "specialDiscountModifier": null,
                    "numberOfOrders": null,
                    "shippingDiscount": null,
                    "specialDiscountType": "NONE",
                    "sellingPlanGroupId": "gid://shopify/SellingPlanGroup/633340149",
                    "sellingPlanId": "3203006709",
                    "discount": 10,
                    "discountModifier": "PERCENTAGE",
                    "optionOrder": 1,
                    "deliveryCadenceCount": 3,
                    "deliveryCadenceUnit": "WEEK",
                    "billingCadenceCount": 3,
                    "billingCadenceUnit": "WEEK",
                    "type": "ONETIME_AND_SUBSCRIPTION_AND_PREPAID",
                    "name": "Delivery every 3 weeks - 10% off",
                    "nameOverride": null,
                    "visibility": null,
                    "isDefault": false,
                    "discountCode": null,
                    "optionType": "ONETIME_AND_SUBSCRIPTION",
                    "giftOptions": null
                },
                {
                    "variants": null,
                    "specialDiscountActive": false,
                    "specialDiscount": null,
                    "discountType": "NONE",
                    "specialDiscountModifier": null,
                    "numberOfOrders": null,
                    "shippingDiscount": null,
                    "specialDiscountType": "NONE",
                    "sellingPlanGroupId": "gid://shopify/SellingPlanGroup/633340149",
                    "sellingPlanId": "3203039477",
                    "discount": 15,
                    "discountModifier": "PERCENTAGE",
                    "optionOrder": 2,
                    "deliveryCadenceCount": 12,
                    "deliveryCadenceUnit": "WEEK",
                    "billingCadenceCount": 12,
                    "billingCadenceUnit": "WEEK",
                    "type": "ONETIME_AND_SUBSCRIPTION_AND_PREPAID",
                    "name": "Delivery every 12 weeks - 15% off",
                    "nameOverride": null,
                    "visibility": null,
                    "isDefault": false,
                    "discountCode": null,
                    "optionType": "ONETIME_AND_SUBSCRIPTION",
                    "giftOptions": null
                },
                {
                    "variants": null,
                    "specialDiscountActive": false,
                    "specialDiscount": null,
                    "discountType": "NONE",
                    "specialDiscountModifier": null,
                    "numberOfOrders": null,
                    "shippingDiscount": null,
                    "specialDiscountType": "NONE",
                    "sellingPlanGroupId": "gid://shopify/SellingPlanGroup/633340149",
                    "sellingPlanId": "3203072245",
                    "discount": 12,
                    "discountModifier": "PERCENTAGE",
                    "optionOrder": 3,
                    "deliveryCadenceCount": 4,
                    "deliveryCadenceUnit": "WEEK",
                    "billingCadenceCount": 4,
                    "billingCadenceUnit": "WEEK",
                    "type": "ONETIME_AND_SUBSCRIPTION_AND_PREPAID",
                    "name": "Delivery every 4 weeks - 12% off",
                    "nameOverride": null,
                    "visibility": null,
                    "isDefault": false,
                    "discountCode": null,
                    "optionType": "ONETIME_AND_SUBSCRIPTION",
                    "giftOptions": null
                },
                {
                    "variants": null,
                    "specialDiscountActive": false,
                    "specialDiscount": null,
                    "discountType": "NONE",
                    "specialDiscountModifier": null,
                    "numberOfOrders": null,
                    "shippingDiscount": null,
                    "specialDiscountType": "NONE",
                    "sellingPlanGroupId": "gid://shopify/SellingPlanGroup/633340149",
                    "sellingPlanId": "3203105013",
                    "discount": 15,
                    "discountModifier": "PERCENTAGE",
                    "optionOrder": 4,
                    "deliveryCadenceCount": 1,
                    "deliveryCadenceUnit": "MONTH",
                    "billingCadenceCount": 6,
                    "billingCadenceUnit": "MONTH",
                    "type": "ONETIME_AND_SUBSCRIPTION_AND_PREPAID",
                    "name": "Delivery every 1 month, prepay every 6 months - 15% off",
                    "nameOverride": null,
                    "visibility": null,
                    "isDefault": false,
                    "discountCode": null,
                    "optionType": "PREPAID_SUBSCRIPTION_ONLY",
                    "giftOptions": null
                },
                {
                    "variants": null,
                    "specialDiscountActive": false,
                    "specialDiscount": null,
                    "discountType": "NONE",
                    "specialDiscountModifier": null,
                    "numberOfOrders": null,
                    "shippingDiscount": null,
                    "specialDiscountType": "NONE",
                    "sellingPlanGroupId": "gid://shopify/SellingPlanGroup/633340149",
                    "sellingPlanId": "3203137781",
                    "discount": 20,
                    "discountModifier": "PERCENTAGE",
                    "optionOrder": 5,
                    "deliveryCadenceCount": 2,
                    "deliveryCadenceUnit": "MONTH",
                    "billingCadenceCount": 6,
                    "billingCadenceUnit": "MONTH",
                    "type": "ONETIME_AND_SUBSCRIPTION_AND_PREPAID",
                    "name": "Delivery every 2 months, prepay every 6 months - 20% off",
                    "nameOverride": null,
                    "visibility": null,
                    "isDefault": false,
                    "discountCode": null,
                    "optionType": "PREPAID_SUBSCRIPTION_ONLY",
                    "giftOptions": null
                }
            ]
        }
    ]
}
```

### Store Theme

```
method GET
<https://subs.api.tryprive.com/stores/><shopify store url>/settings?themeId=<theme_id>
```

| currency             | The currency used for the store                                                                                               | string                                                               |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| money\_format        | The price format                                                                                                              | string                                                               |
| multilocation        | You can set up multiple locations in your Shopify store so that you can track inventory and fulfill orders at your locations. | boolean                                                              |
| oneTimeFirst         | Whether the One-Time purchase should show up first, relative to the other offer options position                              | boolean                                                              |
| onetimeCopy          | The text for the One-Time Purchase option title                                                                               | string                                                               |
| subscribeCopy        | The text for the Subscription Offer option title                                                                              | string                                                               |
| prepaidCopy          | The text for the Prepaid Offer option title                                                                                   | string                                                               |
| subOptionCopy        | ?                                                                                                                             | string                                                               |
| bgColor              | The background color for the widget elements                                                                                  | string                                                               |
| borders              | The border properties for the widget elements                                                                                 | { borderRadius: string; borderWeight: string; borderColor: string; } |
| accentColor          | Radio button color                                                                                                            | string                                                               |
| quantityStyle        | Style for the quantity selector                                                                                               | string                                                               |
| bgColorOnSelection   | Color for the product variant selection box                                                                                   | string                                                               |
| deliveryEveryStyle   | custom CSS for the delivery frequency options                                                                                 | CSS Object                                                           |
| purchaseOptionsStyle | ?                                                                                                                             | CSS Object                                                           |
| selectedOptionsStyle | Styles for the text area                                                                                                      | CSS Object                                                           |
| rank                 | Order for the subscription offer options                                                                                      | defaults to: { one-time: 1 subscribe: 2 prepay: 3 }                  |

```jsx
{
    "currency": "USD",
    "money_format": "${{amount}} USD",
    "multilocation": true,
    "widget_settings": {
        "elements": {
            "buttonPrice": "not-existing-tag"
        },
        "customCss": null,
        "onetimeFirst": false,
        "onetimeCopy": null,
        "subscribeCopy": "Discount Subscription",
        "prepaidCopy": "Prepaid Subscription",
        "subOptionCopy": null,
        "styling": {
            "bgColor": null,
            "borders": null,
            "accentColor": "#000000",
            "quantityStyle": null,
            "bgColorOnSelection": "#dbe4ff",
            "deliveryEveryStyle": null,
            "purchaseOptionsStyle": null,
            "selectedOptionsStyle": {
                "color": "#000000",
                "fontSize": "1",
                "fontWeight": "bold"
            }
        },
        "rank": null
    }
}
```
