# Product catalog

## Summary

This article will describe how CloudMC uses product catalogs to define a set of goods for sale. You bought CloudMC to make money off your cloud resources. We call this monetization. Monetization in CloudMC builds around the concept of a product catalog. A product catalog contains a set of products that you have defined, and you can use the product catalog to apply pricings and create packages for your target market.

## Detailed overview

- A product catalog is a container for product definitions. Products are created inside a category \(eg, compute, networking, storage\). The product catalog does not define any pricing information for products. Each category in a product catalog will appear on customer invoices as a separate grouping of charges.

- A product catalog can regroup multiple connections of a specific type. A product catalog has one and only one service connection type. Once you save a product catalog, you can't change the type of service connection, nor add another. The two available options should be:

1.  select from N connections
2.  select all connections of type X

- Product catalog will not allow the deletion of a product. Only the deprecation. Removing a catalog will remove all products from the pricing.

- A product catalog is either global or accessible to the org in which it was created.

- Default catalogs?

- What are the use cases for multiple product catalogs? Multiple types of service connections \(CloudStack, StackPath, etc\)

Do I need a section on "designing a product catalog"?

A product catalog may only be deleted if there are no pricings using the catalog.

I see in the Update Product Catalog page that some items have a tax code that appears as *overridden*. What does this mean? And why does it appear only when editing a product catalog? Tax codes can be specified at the product category or product level.There are use cases where you may want all products in a category to be **tax code A**but you want a specific tax code in the category to have **tax code B.** The overidden label just indicates that the tax code assigned to a specific product differs from the tax code that was assigned on the category

![Simplified product catalog workflow diagram](Monetization%20model%20-%20Frame%203.jpg "Simplified product catalog workflow")

## Example

-   **[Add a new product catalog](create_product_catalog.md#)**  


