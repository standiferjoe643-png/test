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

# Handle “Entity Points Limit Exceeded” & Upgrade Your Plan

#### **Purpose**

Resolve situations where a migration run exceeds your current Entity Points plan and proceed correctly.

#### **When the Limit Is Exceeded**

* You may see a message similar to **“Entity Points limit exceeded”** when:
  * Your entity count estimate was too low.
  * The data on the source store grew before the run started.

#### **Steps to Upgrade**

1. **Decide if an Upgrade Is Needed**
   * Confirm that the planned run cannot be reduced by:
     * Excluding some entities, or
     * Splitting into smaller runs while respecting data consistency.
   * If the run must include all entities and still exceeds your plan, proceed with an upgrade.
2. **Open the Upgrade Option**
   * Log in to your Next-Cart account.
   * Navigate to **My Licenses / My Services** or **Migration Tool Management**.
   * Locate the migration that shows **Over Limit** and click **Upgrade**.
3. **Choose a New Plan**
   * Select the higher Entity Points plan that covers your estimated run size.
   * The system calculates the **price difference** between your current plan and the new plan; you pay only this difference.
4. **Confirm and Resume Migration**
   * Complete the payment process.
   * After payment, your **Entity Points limit** is updated instantly.
   * Return to your migration project and restart the run.
