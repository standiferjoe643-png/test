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

# Step 3: Back Up Your Source Store

Even though Next-Cart’s tools operate in **read-only mode** (copying data, not deleting it), the Pre-Migration Checklist treats a full backup as “non-negotiable”.

* Export both the **database** and **files** (or ensure your hosting provider has recent snapshots).
* Verify that you can restore from backup if needed.
* Document the backup location and timestamp as part of your internal governance.

This step is mandatory for **all service types** (Standard, Managed, Custom).

#### Why it matters even with a safe tool

Backups are essential because:

* You might make manual changes during preparation.
* Third-party extensions or hosts may behave unpredictably.
