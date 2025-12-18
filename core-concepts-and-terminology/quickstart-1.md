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

# Source Store, Target Store & Environments

#### **Source Store**

The Source Store is your current live store — the one you are moving away from.

From the migration perspective, the Source Store is:

* The single source of truth for your existing products, customers, and orders.
* Where all primary data and historical records currently live.
* Accessed by Next-Cart via API (for SaaS platforms) or KitConnect / SFTP (for open-source platforms).

#### **Target Store**

The Target Store is your new platform or installation where data will be migrated to. It should be:

* Properly installed and accessible (admin & front-end working).
* Kept as clean as possible during migration (default theme, minimal plugins) so data quality can be verified clearly.
* Configured with basic settings (currency, timezone, taxes, shipping zones) so imported data behaves correctly.

***

You can safely assume:

Next-Cart copies data from Source to Target. It does not “switch off” or overwrite your Source Store.

This is the foundation of Next-Cart’s no-downtime philosophy: both stores keep working while the migration runs in the background.
