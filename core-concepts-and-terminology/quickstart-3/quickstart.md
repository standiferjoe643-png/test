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

# Why Not Just Count All The Data?

A store with:

* 500 products and 200 orders

is very different from

* 500 products and 50,000 orders.

Orders and customers are relationally heavier — they contain line items, statuses, taxes, payments, and links to customers and addresses. Treating each item as “1 unit” would under-represent the true complexity.

Entity Points solves this by weighting entities appropriately.
