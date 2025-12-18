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

# KitConnect

KitConnect is a lightweight PHP “bridge” script uploaded to your store’s root directory.

It provides a direct, read-only connection to your database:

* Runs SELECT-only queries (no UPDATE/DELETE/INSERT).
* Is protected by a unique security token.
* Is temporary and can be deleted after migration.

This bypasses API rate limits and incomplete endpoints, making it significantly faster for full migrations.
