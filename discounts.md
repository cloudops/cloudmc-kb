# Discounts

## Summary

## Detailed overview

Gives a customer a percentage discount on the total cost or a set of resources. A discount is an amount of money that you would like to deduct from a total amount at the invoicing stage. Discounts are an important component of a pricing package. Discounts should apply only on utility pricing, and not to commitments \(that makes no sense\).

Once a customer receives a discount, they get the discount for the remainder of the duration promised to them. Cut off date means that no other organizations created after the cutoff date should receive the discount.

- Default discounts? What would this look like?

One comparison is that commitments act on usage, while discounts act on price <-- Sums it up nicely!

Should be able to give a discount on the total. Should be able to give a discount on individual products.

- Discounts are applied before credits <-- Important

- ~~These discounts might need a maximum value, eg 20% off until 200$.~~

Discounts are applied per billing cycle, caveat of org-specific recurring discounts.

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

- Discounts are applied at invoice-generation time \(always on the fly\).

- When does the "counter" for duration start?

- Discounts / Credits

- Discounts are applied at the end of the billing cycle at invoice generation

- Discounts are additive. This means that discounts are applied on top of each other.

- eg 5% off a product, 10% total. We will apply r% on the product first and then 10% on the final total

- Cut off date of a discount:

After the cut off date, discounts will not be renewed.

Can we do multiple discounts on the same package? If so, if we do 20% discount on all products, and add a 10% discount on SP-1, what happens?

Discounts are pre-tax and credits are post-tax.

- Everything, eg 20% off the total cost

- A single "service" eg 20% off Edge Database

- One or multiple products, eg 20% off on disks of type X

- Can have an expiry date, eg I get 20% discount for the next 2 months

- Everything in a category 20% with max of 200$ month

- Everything 10% off plus credit

- Single product CPU off 25% plus 3 months off 500$ credit \(this can be an org dicount that we've already used 400$ of\)

-   **[Offer a limited-time discount](offer_a_limited_time_discount.md)**  


