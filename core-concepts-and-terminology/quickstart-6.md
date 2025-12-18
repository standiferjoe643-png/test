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

# Data Compatibility

Data Compatibility describes how well the structure of your Source Store’s data matches what the Target Store supports.&#x20;

#### **Key ideas:**

* Different platforms have different rules for:
* product types (simple/bundle/downloadable),
* variant structures and option limits (e.g. Shopify’s variant limits),\
  Migrating to WooCommerce Handbo…
* tax engines,
* URL structures and SEO fields.
* A migration cannot make the Target Store support something the platform itself does not support.

#### Next-Cart handles data compatibility by:

* mapping fields wherever a direct equivalent exists,
* using reasonable defaults when there is no perfect match,
* flagging constraints (like variant limits) in advance wherever possible,
* offering Custom Migration Service when plugin-stored or highly custom data requires one-off logic.

Next-Cart’s configuration phase is where these compatibility decisions are set up so that automated migration can handle them consistently.
