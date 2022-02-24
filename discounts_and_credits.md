# Discounts and credits {#discounts_and_credits .concept}

## Summary {#section_zw3_z3f_sqb .section}

## Detailed overview {#section_qwy_z3f_sqb .section}

- Discounts: Gives a customer a percentage discount on the total cost or a set of resources.

- Discounts are tied to a pricing and to an organization. Tying it to an applied pricing makes sense. \(?\)

- Default discounts? What would this look like?

- Discounts should apply only on utility pricing, and not to commitments \(that makes no sense\).

- One comparison is that commitments act on usage, while discounts act on price <-- Sums it up nicely!

- Should be able to give a discount on the total

- Should be able to give a discount on individual products

- Discounts are under applied pricing

- A discount is an amount of money that you would like to deduct from a total amount at the invoicing stage.

- A credit is an amount of money that a customer has access to inside the platform. When using resources on the platform, the cost of those resources are deducted from the credits they have.

- Credits should be automatically configured for an organization once they are onboarded. This will depend on the offer they selected.

- Credits are automatically applied for a user when calculating reports / invoices.

- Example credits:

- 200$ no strings attached. 200$ that can be used on anything in the application.

- 100$ on edge database. 100$ that can be used for edge database features.

- Credits for an SP-1 \(per SKU/per Product\). Set credits for a specific product.

- Credits have an expiry date associated to them. For example, the credit must be used in the following three months.

- Can be recurring, eg I get 300$ credits every year.

- Credits will only be displayed on reports on the monthly invoice. No need for hour-to-hour tracking.

- Credits are applied per billing cycle with the caveat of org-specific recurring discounts.

- These are matched with a pricing to make a package.

- Need to be able to track how much of your credit you use per month, if for example you have a 3 month credit, so something will have to be persisted. A credit that lasts 3 months is different than a 300$ credit monthly.

- Discounts are a percentage discount on:

- Everything, eg 20% off the total cost

- A single "service" eg 20% off Edge Database

- One or multiple products, eg 20% off on disks of type X

- Can have an expiry date, eg I get 20% discount for the next 2 months

- Discounts are applied before credits <-- Important

- ~~These discounts might need a maximum value, eg 20% off until 200$.~~

- Discounts are applied per billing cycle, caveat of org-specific recurring discounts.

- Discounts are matched with a pricing to make a package.

- Future possibilities:

- $ discount after X spend, eg Get 20% after spending 100$

- Can be up to a $ value, eg 20% discount for a maximum of 200$.

- What about overlapping discounts?

- What about things like 10% off edge services + 10% off everything?

- What about retroactively discounting things?

- You can't discount things already invoiced and paid

- Discounts and credits should be applied at the end of the billing cycle.

- Reports won't have discounts applied, invoices will have them applied.

- Discounts and credits will be displayed on the organization details page. High-level visibility.

- More examples:

- Everything in a category 20% with max of 200$ month

- Everything 10% off plus credit

- Single product CPU off 25% plus 3 months off 500$ credit \(this can be an org dicount that we've already used 400$ of\)

- Discounts are applied at invoice-generation time \(always on the fly\).

- When does the "counter" for duration start?

- Currently the duration begins right at the first time you get the credit applied \(ie the first billing period you actually consume that category or product type\).

- There are alternative ways to mark the start time.

- Credits if contained in the billing period apply to the entire invoice.

- Discounts / Credits

- Discounts are applied at the end of the billing cycle at invoice generation

- Discounts are additive

- eg 5% off a product, 10% total. We will apply r% on the product first and then 10% on the final total

- Cut off date of a discount:

- Once a customer receives a discount, they get the discount for the remainder of the duration promised to them. Cut off date means that no other orgs created after the cutoff date should receive the discount.

- After the cut off date, discounts will not be renewed.

- Credits are carried over to the next month until the duration of the credit is over. Once over, the credits are lost.

- Discounts are pre-tax and credits are post-tax.

## Example {#section_umt_1jf_sqb .section}

-   **[Offer a limited-time discount](offer_a_limited_time_discount.md)**  


