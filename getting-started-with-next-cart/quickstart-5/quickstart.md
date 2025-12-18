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

# Configure a Full Migration

**Purpose**\
Set up the configuration that will be reused for your full and later Recent Data migrations: entities, options, and mappings.

**Prerequisites**

* Successful **Free Demo Migration** with acceptable results.
* Entity Points plan calculated.
* Any required customizations planned (e.g., using Custom Migration if needed).

**Instructions**

1. **Open Your Migration Project**
   * Sign in to your Next-Cart account.
   * Go to **Migration Tool Management** from your dashboard.
   * Open the existing migration project you used for the demo, or create a new project with the same source/target setup.
2. **Confirm Connections**
   * Verify that **Source** and **Target** carts are still connected:
     * URLs are unchanged.
     * API credentials or KitConnect path are still valid.
   * If connection checks fail, resolve using the **Instruction & Troubleshoot** page.
3. **Select Entities**
   * On the **configuration screen**, select the entities to migrate:
     * Products, Categories/Collections, Customers, Orders, Coupons, Reviews, Blog posts, CMS pages, URL redirects, and any other supported types.
   * For a full migration, select **all entities** that must move to the new store.
4. **Configure Additional Options**
   * Review available options such as:
     * _Migrate SEO URLs_
     * _Preserve Order IDs_ (where supported)
     * _Migrate images_, _migrate meta data_, or platform-specific switches.
   * Enable only options that match your target store requirements and platform capabilities.
5. **Review and Adjust Mappings**
   * Open the **Attributes / Fields Mapping** section.
   * Check that key fields map correctly, for example:
     * Brands → Vendors (e.g., when moving to Shopify).
     * Status fields, visibility, tax classes, etc.
   * For complex or non-standard data structures, document any custom mapping requirements (these may fall under **Custom Migration** work if implementation requires custom jobs).
6. **Save Configuration**
   * Save the full migration configuration.
   * Confirm that this configuration will be reused when running:
     * The **Full Migration**.
     * Any later **Recent Data Migration** for the same project.
