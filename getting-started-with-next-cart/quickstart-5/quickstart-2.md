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

# Run a Recent Data Migration

**Purpose**\
Bring the target store in sync with any **new or updated data** created on the source store after the last full migration, without re-migrating everything.

**Key Concept**

* **Recent Data Migration** compares your source and target stores and moves only the **new or changed entities** since the last run (e.g., new orders, customers, products).

**Prerequisites**

* At least one completed **Full Migration** for the project.
* No structural changes to the target store that would invalidate mappings.
* Source store still accessible with valid connection credentials.

**Instructions**

1. **Confirm When to Use Recent Data Migration**
   * Use Recent Data Migration when:
     * The main migration is complete.
     * The source store stayed live and collected new data (orders, customers, products).
   * Do **not** use it if you changed core mapping or structure; in that case, consider a re-run of the full migration under guidance.
2. **Open the Existing Migration Project**
   * Sign in to your Next-Cart account.
   * Go to **Migration Tool Management** and open the migration project that contains the completed full migration.
3. **Select Recent Data Migration Mode**
   * Locate the option tied to your existing migration, such as:
     * **Recent Data Migration**, or
     * **Continue Previous Migration (Recent Data)**.
   * Ensure you are not creating a brand new migration project; you should continue from the same one used for the full migration.
4. **Check Entity Points for This Run**
   * Estimate the new entities added since the full migration (e.g., additional orders, customers, products).
   * Ensure the total for this **single Recent Data Migration run** is within your plan’s Entity Points limit.
5. **Run Recent Data Migration**
   * Start the run in Recent Data mode.
   * The tool will detect and migrate only the **new or changed entities** since the last recorded migration for this project.
   * The process runs in the background (like a full migration), according to your plan behavior.
6. **Verify Sync**
   * Once the run completes, log in to your **Target Store admin**.
   * Confirm that:
     * New orders, customers, and products from the source now appear on the target.
     * The latest order history and customer data are present.
   * Once satisfied, you can finalize domain cut-over or complete your go-live actions.
