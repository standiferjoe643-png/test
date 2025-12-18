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

# Recent Data Migration

It is designed for the final synchronization before go-live:

* After you have completed a successful Full Migration and verified your Target Store.
* Your Source Store continues receiving new orders, new customers, and updated products.
* Recent Data Migration copies only the new and recently changed data from Source to Target, instead of re-migrating everything.

Typical use cases:

* Migrate orders placed during the transition period.
* Migrate new customers who registered after the full migration.
* Update inventory, prices, or product details modified since the last run.

Recent Data Migration ensures your Target Store goes live with up-to-date data, while avoiding unnecessary load or duplication.
