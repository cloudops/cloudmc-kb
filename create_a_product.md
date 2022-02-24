# Add a new product

-   A product may be added only while editing an existing product catalog, or while adding a new product catalog.
-   A product category must already exist within the target product catalog

Edit the desired product catalog or [add a new catalog](create_product_catalog.md#) to add or edit a product.

1.  From the Update Product Catalog screen, select the desired product category for adding the new product. You may also create a new category for your product, if desired.

2.  Click the button labeled **Add new product**. The Product Details section will appear.

3.  Enter a name and a SKU for your product.

    If multiple languages are enabled, a name must be provided for each language. Click the language gadget on the right of the text field to switch to the other languages, then enter a name for the product in each language.

    The SKU exists in only one language, and it cannot be modified once the product is created.

4.  Select the source that will define your product.

    The source represents the type of data that will be used for metering the usage of this product. The pop-up list contains all of the sources that are provided by the selected service type. Sources will vary between service types, and the choice of source will affect the attributes which can be used in the product definition, as well as the fields and values available for filtering.

5.  Select the attribute to use for your product.

    The attribute is the actual data record that will be used for calculating usage. The attributes will vary between sources. The pop-up list contains all of the attributes that are provided by the selected source. The most common attribute is `Raw Usage`.

    See [Sources and attributes](sources_and_attributes.md) for details.

6.  Select the unit to use for your product.

    The unit describes the quantity represented by the raw number provided in the attribute.

    All attributes have a reasonable default unit defined. See [Reference of units](reference_of_units.md) for details on supported units.

7.  Some attributes allow you to select the time period to use for calculating usage.

    If the selected attribute supports time periods, you may choose between hourly and monthly periods. All attributes have a reasonable default period defined. See [Usage types](usage_types.md) for details.

8.  Taxes. Ugh.

9.  Select the type of transformation desired for the product.

    Transformations allow you to modify the raw usage provided in the attribute. See [Transformations](transformations.md) for details.

10. Select the type of filter desired for the product.

    Filters allow you to exclude data records from the billing calculations, using data that is found in the data record itself. See [Filters](filters.md) for details.

11. Click the **Add new product** button to add the new product, then click **Submit** to save all changes.

    You may return to step 2 and add more products before clicking the **Submit** button.

    CAUTION:

    You must click the **Submit** button in the product catalog in order to save your new product. If you do not save the changes to the product catalog, your new product will be lost.


**Parent topic:**[Products](products.md)

## Example for add a new product

In this article, we will add a new product to Acme Corporation's product catalog. Our service connection allows users to create virtual machines using a specification \(in this case, *SP-1*\), and we will define the product using a filter which selects usage records that match the exact title of that specification . The product catalog has already been created, with a product category named `Compute`. We begin by navigating to the **Administration** \> **Monetization** page, and then editing our product catalog, `Acme Private Cloud`.

1.  From the Update Product Catalog screen, scroll down to the **Products** section, and select the `Compute` category.

2.  Click the button labeled **Add new product**. The Product Details section will appear.

3.  Enter `VM - Basic (1 vCPU, 2GB RAM, 25GB disk)` into the **Name** field, and `APC-VM-001` into the **SKU** field.

4.  Select `Specification` from the **Source** pop-up menu.

5.  Select `Raw Usage` from the **Attribute** pop-up menu.

6.  Keep the default unit \(`Unit`\).

7.  Keep the default time period \(`hour`\).

8.  Select the appropriate tax code from the **Taxes** pop-up menu.

9.  Select `Proportion of used time` from the Transformation pop-up menu.

    This transformation will ensure that the customer is charged only for the amount of time that their VM was running.

10. Define the filtering rule for this particular product.

    1.  From the first pop-up menu, select `Following rule`.

    2.  Select `VM Spec` from the **Field** pop-up menu.

    3.  Select `equals` from the **Operator** pop-up menu.

    4.  Select `SP-1 (1 vCPU, 2Gi RAM, 25Gi Root Disk)` from the **Value** pop-up menu.

    5.  Click the **+** icon to add the filter.

    This filter allows us to include only usage records for virtual machines configured with the `SP-1` specification, the product we wish to bill for.

11. Click the **Add new product** button to add the new product, then click **Submit** to save all changes.


