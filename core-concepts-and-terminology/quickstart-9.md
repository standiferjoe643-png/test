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

# Security, Privacy & Data Handling

Security and compliance are first-class concepts, not an afterthought.

A full security policy lives in the Governance section, but a few conceptual terms are important here:

* Read-only migration
* KitConnect scripts are restricted to SELECT queries on the Source Store.
* API connections use permission scopes; Next-Cart typically requests only read access where possible.
* Temporary access
* API keys and KitConnect bridges can be deleted as soon as the migration is finished, instantly revoking access.&#x20;
* Data handling
* The migration system processes data in secure cloud environments; long-term retention is governed by separate policies covered in the Governance section.

Next-Cart works by creating controlled, revocable connections to read data from your Source Store and write it to your Target Store, without altering the original database.
