# Usage types

A usage type is defined as the source of a product. All attributes have a type, which indicates how to interpret the data provided by the attribute. There are two types:

-   **Counter**: A counter-based attribute represents a simple total of resource usage over a given period of time. This is used for resources that are used incrementally over a billing period. The counter never decreases during a billing period, it only increases as a resource is consumed, and is reset to zero at the beginning of a new billing period. Examples of counter-based attributes would include the number of requests served, or the number of bytes transferred over the network.
-   **Gauge**: A gauge-based attribute represents the amount of resources being used at a given point in time. This is used for resources that may be provisioned and released over a billing period. The gauge increases as resources are allocated, and decreases as resources are deallocated. At the end of a billing period, the system will calculate the amount of resource consumed using rules specified in the product definition. Examples of gauge-based attributes would include the number of vCPUs or the number of gigabytes of memory assigned to an instance.

Gauge-based attributes have an additional property, the *period*. The period represents the length of time the system will use when calculating usage for this attribute, and can be set to either *hourly* or to *monthly*. An attribute with an hourly period will have a data point calculated for every hour in the billing cycle. This is appropriate for attributes that may vary frequently through the billing period, such as vCPU or memory. An attribute with a monthly period will have a single data point calculated at the end of the billing cycle, and is appropriate for attributes that are expected to remain largely static through the billing period, such as the size of a storage volume.

Each attribute is also always associated with a unit. The unit indicates what the attribute's raw data represents. For example, an attribute for memory could be expressed in megabytes \(MB\) or gigabytes \(GB\), an attribute for network bandwidth consumed could be expressed in megabits per second \(Mbps\), or an attribute for compute resource as a count of vCPUs allocated to instances. A default unit is always provided for an attribute.

**Parent topic:**[Products](products.md)

