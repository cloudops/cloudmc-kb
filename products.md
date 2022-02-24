# Products

## Summary

## Detailed overview

A `product` represents a consumable resource whose usage CloudMC will meter and charge for. Products are created within a `product category` \(e.g., *Compute*, *Networking*, *Storage*, etc\), which in turn is created inside a `product catalog`. To add a new product or to modify an existing product, you must edit or create a product catalog and then create the product within the catalog.

![Diagram of attributes of a product](Monetization%20model%20-%20Frame%202.jpg "Elements of a product")

A product may be associated with tax code, which will be used when calculating sales tax on an invoice. Also, a name and a stock keeping unit \(SKU\) is required for every product so that it can be uniquely identified.

The system provides two important mechanisms for refining the product definition: *transformations* and *filters*. A transformation can be applied to modify the raw usage. Both filters and transformers support an expression using the SpEL DSL. SpEL \(Spring expression language\) for taking in a string expression and evaluating it.

- Fields can be captured to be the attribute of the usage \(eg, capture the vCPU usage for my vCPU product\) <-- I don't understand this part. Actually, I do understand now, it just means that a field in a usage record can also be used as the attribute. I think this is useful for writing filters using the value of attributes.

- COGS and unit price should be set for every product. However, the product definition does not contain any cost or pricing information.

A product exists only within a product catalog. A product does not exist outside of a catalog. A product is added or modified by editing a product catalog. Removing a catalog will remove all products from the pricing.

SpEL:

proportion of used time

If you have a license \(0 or 1\)

A product by itself has no price or currency.

yes we do… use we SPEL expression and you can use the rawUsage and attributeValue if you are using let say the memory of a vm

Perfect! Oh yes I came across the choice of SPEL in one of the design docs. And yes, I've seen rawUsage in an example transformation \(rawUsage / 1024\), but I didn't know about attributeValue. That's great, thank you my friend :smile:

## Example

-   **[Sources and attributes](sources_and_attributes.md)**  

-   **[Usage types](usage_types.md)**  

-   **[Transformations](transformations.md)**  

-   **[Filters](filters.md)**  

-   **[Add a new product](create_a_product.md#)**  

-   **[Change the name of a product](change_the_name_of_a_product.md#)**  


