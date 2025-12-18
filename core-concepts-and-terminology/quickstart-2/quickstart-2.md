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

# Relationships Between Entities

A key part of a professional migration is preserving relationships, not just copying rows of data. Next-Cart’s migration engine maintains links such as:

* **Products** ↔ **Categories**
* **Orders** ↔ **Customers**
* **Products** ↔ **Reviews**
* **Products** ↔ **Images**
* **Coupons** ↔ **Orders**
* **Blog posts** ↔ **Categories/tags**

This is why many **“export/import” methods fail**: they often break these relationships, causing orphaned data and inconsistent customer experiences.
