# Add a new tiered pricing

Monetization is configured from the **Administration** \> **Monetization** page.

-   At least one product catalog must be configured.
-   At least one product must exist in the catalog.
-   You must know the desired selling price and cost of goods sold for the product in all relevant currencies.

1.  Navigate to **Administration** \> **Monetization** \> **Pricings**, and click on **Add pricing**.

2.  Enter a name for the new pricing.

    If multiple languages are enabled, a name must be provided for each language. Click the language gadget on the right of the text field to switch to the other languages, then enter a name for the tiered pricing in each language.

3.  Add an optional description.

4.  Select the effective date for the new pricing.

    This is the earliest date that the pricing will apply to applicable usage data. New pricing packages using this pricing cannot be applied on a date earlier that the pricing's effective date.

5.  Select the currency or currencies that will be supported by the new pricing.

    If you choose more than one currency, you will be required to add prices to each product for every currency selected.

6.  Select the product catalog or catalogs to include in the pricing.

7.  Select a product, and the **Add pricing** dialog box will appear.

8.  If multiple currencies are selected, a pop-up menu labeled **Currency** will appear at the top of the dialog box. Choose the first currency to configure. If only one currency is selected, skip to the next step.

9.  Enter the price to be extended to the customer into the field labeled **Price**.

    The price is the value that will appear on the customer's invoice and will be used for calculating usage charges. This represents the first tier of pricing, which is the amount that will be charged for the least possible usage of a product.

10. Enter the cost that the reseller pays for the product into the field labeled **Cost of goods sold \(COGS\)**.

    This is the value that will appear on the revenue report, and will be used for calculating the profit margin. It remains constant for all tiers.

11. Click on **Configure pricing tiers**, then click on **Add pricing tier**.

12. Enter the values for the second pricing tier for this product.

    Each new pricing tier is defined by the minimum amount of usage that qualifies for this tier, and the price. When usage exceeds this bottom threshold, the customer will be charged for all usage in the billing cycle at the price of this tier, unless usage exceeds the bottom threshold of the next tier.

    1.  Enter the bottom threshold for the tier into the **Usage over** field.

    2.  Enter the price to be charged to the customer into the **Charged** field.

    3.  To add another pricing tier above this one, click on **Add pricing tier**, and repeat sub-steps **a**, **b**, and **c**. If this is the top tier, skip to the next sub-step.

    4.  If multiple currencies are selected for this pricing, choose the next currency to configure from the **Currency** pop-up menu, and repeat steps **9**, **10**, **11**, and **12** until all tiers are defined in all currencies. If only one currency is selected, skip to the next sub-step.

    5.  Click **Add**. You are returned to the **Add pricing** page, and the new pricing is listed under the appropriate product category.

13. You may add pricings for other products in the catalogs, or you may click **Submit** to save the new pricing.


-   The new pricing will be listed on the **Pricings** page.
-   Customers using the products in a pricing package containing this pricing will be charged at the new rates between the start and end dates of the package.
-   If the effective date of the pricing is in the past, an automatic rollback will be triggered and past usage data will be processed. This may result in additional charges or credits appearing on future invoices.

**Parent topic:**[Pricing](pricing.md)

## Example for add a new tiered pricing

