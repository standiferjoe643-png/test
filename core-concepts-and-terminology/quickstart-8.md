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

# Background Migration & No Downtime

One of Next-Cart’s core promises is that your Source Store keeps running while data is being migrated.

* The migration engine runs on Next-Cart’s servers.
* Once a migration is started, it continues to run in the background even if you close your browser.
* The Source and Target stores remain online; the process is designed to copy data, not to lock tables or block checkout on the Source Store.

Best practices:

* Avoid editing the same entities on the Target Store while a migration is in progress, as it can introduce mismatches.
* Always back up your Target Store before running a Recent Data Migration or Re-Migration.
