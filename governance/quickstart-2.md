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

# Data Security

#### Security Principles

* **Data-minimization**: Only the data needed to perform the migration is accessed and stored, and only for as long as required.
* **Read-only access to the Source Store**: Connectors are designed to copy, not to modify, delete, or insert data in your original store.
* **Revocable connections**: API keys, KitConnect bridges, and SFTP credentials can be revoked or removed at any time by the merchant.
* **No data resale**: Customer lists and sales data are never sold or reused; Next-Cart positions itself strictly as a “data mover,” not a data broker.

#### Connection Methods and Access Control

Next-Cart uses different connection methods depending on the platform:

1. **API Connections (for SaaS / hosted platforms)**

* Used for Shopify, BigCommerce, Wix, etc.
* You create an API key or access token in your store’s admin.
* The API key usually has read-only or limited permissions, allowing Next-Cart to fetch products, customers, and orders without needing your admin password.
* All communication happens over HTTPS, using the platform’s official API endpoints.

2. **KitConnect (for open-source platforms)**

* A lightweight PHP “bridge” uploaded to your store’s root directory.
* Designed to run SELECT-only database queries; it cannot execute UPDATE, DELETE, or INSERT commands on your Source Store.
* Protected by a unique security token; only the migration engine with this token can use the bridge.
* **Temporary**: once migration is done, you delete the KitConnect folder and the connection is gone.

3. **File / SFTP / Hosting Manager Access**

* Used primarily to upload KitConnect or handle file-based migrations.
* Best practice is to use SFTP (encrypted) rather than plain FTP.
* Access can and should be revoked or passwords changed once the migration is complete.

Support access (admin or hosting logins) is requested only when needed to troubleshoot a specific migration issue and is handled under the same confidentiality and security expectations.

#### Data Handling During Migration

* During an active migration project, Next-Cart processes:
  * Store content such as products, categories, attributes, customers, orders, coupons, blog posts, pages, and reviews.
  * SEO-related information where supported (URLs, meta titles/descriptions, and, when applicable, redirect information).
* **Processing environment**
  * The migration engine runs on controlled cloud servers; processing is done server-side even if you close your browser.
* **Access control**
  * Internal staff are bound by strict confidentiality rules and NDAs, and only senior technicians handle sensitive migration projects.
* **Support access**
  * When support needs temporary admin / hosting / SFTP access, they request only what is necessary and use it solely to troubleshoot your migration.

#### After Migration: Deletion & Revocation

* Once your migration is completed and your support window ends, store data used for the migration is purged from Next-Cart’s systems.
* **What remains:**
  * Your account details (e.g., login email) and
  * Billing / invoice information required by law.
* **Recommended post-migration actions** for merchants:
  * Delete any API keys or app tokens that were created solely for the migration.
  * Delete the KitConnect folder from your Source Store.
  * Change temporary passwords for admin, SFTP/SSH, or hosting accounts shared with support.

These steps ensure that both sides fully close authentication paths that were opened for the project.

#### Incident Handling, Limitations & Shared Responsibility

* **Next-Cart is responsible for:**
  * Securing its migration infrastructure and internal processes.
  * Handling data in accordance with its Privacy and Data policies.
  * Investigating and resolving migration-related issues reported by customers.
* **You remain responsible for:**
  * Maintaining secure passwords and accounts for your own systems.
  * Keeping your hosting and platforms patched and hardened.
  * Promptly notifying Next-Cart if you suspect misuse of credentials shared for migration.

If you believe there has been any security incident affecting your data, the recommended actions are:

1. Immediately revoke or rotate any credentials that may be exposed.
2. Contact Next-Cart support with a detailed description of the issue.
3. Review logs and platform-level security alerts in coordination with your hosting provider.
