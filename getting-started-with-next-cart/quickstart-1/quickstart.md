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

# Step 1: Audit Your Current Store & Data

This is the single most important preparation step.

#### **Count your key entities**

You need accurate counts for at least the **“big four”**:

* Products
* Customers
* Orders
* Blog posts (and optionally key CMS pages if they are important for SEO)

#### **Convert them into Entity Points**

Next-Cart uses **Entity Points** as a weighted measure to determine your migration plan. The formula is:

{% code overflow="wrap" fullWidth="true" %}
```
Entity Points = (Total Products × 1.0) + (Total Customers × 0.5) + (Total Orders × 0.8) + (Total Blog Posts × 0.6)
```
{% endcode %}

Example:

* 500 Products
* 100 Customers
* 600 Orders
* 100 Blog Posts

→ (500 × 1) + (100 × 0.5) + (600 × 0.8) + (100 × 0.6) = **1,090 Entity Points**

This total **directly maps** to your pricing plan and determines whether you will need a larger plan or a per-run upgrade.

#### **Audit your custom & third-party data**

Make a list of:

* Loyalty programs, reward points, store credit
* Advanced product options or product add-ons
* Third-party review apps (e.g., photo reviews, Q\&A)
* Subscription / recurring billing plugins
* Custom fields or attributes specific to your industry

The guide on plugins & extensions explains that **standard migration** covers native platform data only, while non-native or app-specific data often requires **Custom Migration (Custom Job)**.

Use this audit to decide early whether you will likely need **Standard**, **Managed** or **Custom Migration**.
