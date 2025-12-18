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

# Step 4: Run a Free Demo Migration

The next critical step is a **Free Demo Migration**, which is a live, limited-scope test of the migration tool on your real data.

The demo will:

* Connects your **Source** and **Target** stores (via API or KitConnect).
* Migrates a **small, fixed sample** of your key entities (typically 10 products, 10 customers, 10 orders, 10 blog posts, 10 CMS pages + related data).
* Preserves links between data (products ↔ categories, orders ↔ customers, etc.).
* Runs in **read-only** mode and does not affect your live source store.

You will see exactly how your data appears on the new platform before you commit to a full migration.

> You should **never** purchase or run a full migration without a successful demo first.\
> This is the primary method for verifying **connections, mapping, and data structure**.
