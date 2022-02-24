# Overview of monetization

## Summary

Monetization is the set of features that enable a reseller to bill their customers based on metered usage of their cloud resources. This article will describe the powerful and flexible CloudMC monetization model, and the concepts that resellers will need for configuring and managing how the platform will track and charge customers.

## Detailed overview

The monetization process is a multi-step pipeline that takes raw usage data, applies product and pricing definitions which are scoped by organization, and generates reports and invoices that can be sent to customers. The system supports *utility pricing*, which means customers are charged only for what they use in a given billing period, and *commitment pricing*, by which a customer purchases a minimum quantity of resource every billing period at a set price.

![Diagram of monetization entities](Monetization%20model%20-%20Frame%201.jpg "Simplified view of monetization entities")

This simplified illustration of the monetization model shows the basic entities that take part in the pipeline. The core concept is the *product catalog*, which serves as a container for the *products* associated with a given *service connection*. A product catalog has one and only one service connection type. A product exists only within a product catalog, and other than a tax code a product definition itself does not have any pricing information. Once a product catalog has been defined, *pricing* for the products in a product catalog can be defined. A pricing includes the price at which the product will be made available for a customer, as well as the cost of goods sold for the product. Tiered price levels are supported. A pricing can be applied to a product catalog and scoped to an organization to create a *pricing package*.

A reseller has access to configure monetization for the organizations that they own. Resellers can create their own products or use the default ones. Monetization can be configured for any top-level organization, and includes usage of its sub-organizations. Because product definitions rely on information that is specific to a service connection, a product catalog is defined for exactly one kind of service connection.

- Can be done for any environment of a top-level org \(but not environment of sub-org\), including previously deleted environment.

Raw usage data is gathered on an hourly basis. Pricing is per usage type \(type of service connection\) and per service connection

Why? What is the point?

Reporting:

- Can be done on any period of time \(aligned with UTC daily boundaries\).

- Modifying past pricing/resource commitments should recalculate usage from that period.

- Should be able to generate reports that compare actual cost vs price charged. This is the Cost of Good Sold.

Usage collection -\> Products -\> Pricing -\> Applied pricing -\> Resource commitment -\> Discount

- In Pricing 2.0, we have the following entities:

- Products

- Pricing

- Applied pricing

- Modifying any of those entities has implications to the past and future reports of customers.

- There will be a page called Changes under the Details page that will list all past and upcoming changes.

- Warns user when an update might modify past usage.

- Product catalog will not allow the deletion of a product. Only the deprecation.

What about the last-usage record field on the Organization details page?

An organization can define multiple product catalogs and multiple pricings, but all of it has to go together into a single pricing package that must address all products available for usage in an organization.

What happens if you edit an org's billable flag? Does it void all draft invoices? How about if you change the org's billing cycle?

## Example

