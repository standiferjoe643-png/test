---
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
---

# Entity Points

Entity Points are a weighted way of measuring “how big” your migration is by assigning different point values to different entity types. This reflects:

* The complexity of an entity (e.g., orders are more complex than products).
* The processing cost to read, transform, and import it.
* The load is placed on your servers and the migration infrastructure.

Instead of counting only raw items, Entity Points give a more realistic picture of the workload.

#### **How Entity Points Are Calculated**

Each entity type is assigned a point value. Your store’s Entity Points total is:

* (Number of Products × 1)
* (Number of Customers × 0.5)
* (Number of Orders × 0.8)
* (Number of Blog Posts × 0.6)

{% code overflow="wrap" %}
```
Entity Points = (Total Products × 1.0) + (Total Customers × 0.5) + (Total Orders × 0.8) + (Total Blog Posts × 0.6)
```
{% endcode %}
