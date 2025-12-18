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

# How to Check Your Store’s Total Entities

Typical pattern:

* Navigate to the **Products** list – read the “X records found” number.
* Navigate to **Customers** – read total count.
* Navigate to **Orders** – read total count.
* Navigate to **Blog / Content** – read total post count.

Repeat for each store, and record the totals in your internal worksheet or project tracker.

#### **Calculate Entity Points**

Use the current Entity Points formula:

{% code overflow="wrap" %}
```
Entity Points = (Total Products × 1.0) + (Total Customers × 0.5) + (Total Orders × 0.8) + (Total Blog Posts × 0.6)
```
{% endcode %}

This number determines which Entity Points plan you will need and whether your full migration run fits within a single plan.

<br>
