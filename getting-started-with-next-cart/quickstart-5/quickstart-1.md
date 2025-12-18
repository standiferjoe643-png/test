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

# Run a Full Migration

**Purpose**\
Execute the full, background migration that moves all selected entities to the target store.

**Prerequisites**

* Full migration configuration completed.
* Plan Entity Points are sufficient for the run.
* Recent backup of the source store.

**Steps**

1. **Confirm Entity Points for This Run**
   * Estimate total Entity Points for this migration run (products, customers, orders, and other counted entities).
   * Make sure the total is within your **Entity Points plan limit**.
     * The limit applies **per migration run**, not as a shared pool across all runs.
2. **Start the Full Migration**
   * In **Migration Tool Management**, open your configured migration project.
   * Ensure the configuration is set to **Full Migration** (not demo, not Recent Data).
   * Click **Start Migration**.
3. **Allow Background Processing**
   * After the full migration starts, the job runs on Next-Cart’s servers, not in your browser.
   * You may safely close your browser or continue other work; the migration will continue in the background (unlike the Free Demo, which requires the browser to remain open).
4. **Monitor Status**
   * Return to **Migration Tool Management** to monitor progress and status.
   * If the migration pauses or reports errors, refer to the Troubleshooting section for:
     * Connection errors
     * API limits
     * File permission issues, etc.
5. **Verify Full Migration Results**
   * When the full migration reports **Completed**, log in to the **Target Store admin**.
   * Verify a representative sample across:
     * Products + categories/collections
     * Customers + order history
     * Coupons, reviews, redirects, blogs, CMS pages
   * Confirm that URLs, relationships, and basic SEO fields behave as expected.
6. **Plan for Go-Live**
   * After confirming data quality, follow your **Go-Live plan** to schedule domain cut-over and final Recent Data Migration.
