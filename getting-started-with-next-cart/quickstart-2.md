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

# Run a Free Demo Migration

#### **Purpose**

Use the Free Demo Migration to verify connections, mapping, and data structure before running a full migration.

#### **Prerequisites**

* Pre-migration checklist completed.
* Source and Target carts created and reachable.
* Connection method set up (API / KitConnect / file import)
* Next-Cart account created and logged in.

#### **Instructions**

1. **Open the Demo Migration Wizard**
   * Sign in to your Next-Cart account.
   * From **Migration Tool Management**, create a new migration or open your existing draft migration.
   * Choose the option to **run a Free Demo Migration** (or “Start Free Demo”).
2. **Connect the Source and Target Carts**
   * Select your **Source Cart** platform.
   * Enter the **Source Store URL**.
   * Provide connection details:
     * **Open-source platforms** (e.g., WooCommerce, Magento): upload KitConnect to your web root via FTP or cPanel File Manager, then confirm the KitConnect URL.
     * **SaaS platforms** (e.g., Shopify, BigCommerce): enter the required **API credentials** (Admin URL / API key / token / secret) as indicated for that platform.
   * Repeat the same steps for your **Target Cart** (URL + credentials).
   * **Notice**: Next-Cart will require login information (email & password) on certain platforms. Please check the information required in the Source Cart settings.
3. **Configure Demo Entities & Options**
   * On the **configuration screen**, leave the main entities selected:
     * Products, Customers, Orders, Blogs, and CMS pages (default selection is usually sufficient).
   * (Optional) Enable any **additional options** you want to test, such as:
     * _Migrate SEO URLs_
     * _Preserve Order IDs_
     * Other platform-specific options shown in the interface.
   * Check the **attribute / field mapping**:
     * Keep defaults if your data structure is standard.
     * Adjust mappings only if you understand how your source fields should map into target fields.
4. **Run the Demo**
   * Click **Start Demo Migration**.
   * Keep your **browser window open** until the demo finishes; demo runs do **not** process in the background.
   * Wait for the status to report **Completed**.
     * The demo typically moves up to **10** records for each main entity (Products, Customers, Orders, Blogs, CMS pages).
5. **Review Demo Results**
   * Log in to your **Target Store admin**.
   * Inspect a sample product, order, customer, blog post, and CMS page:
     * Verify names, prices, descriptions, and images.
     * Check categories/collections and attribute/variant configuration.
     * Confirm that customers and orders are properly linked.
   * Note any missing elements that are **intentionally excluded** from demos (e.g., reviews, coupons, most custom plugin data).

If you experience difficulty running the Demo Migration, feel free to contact Next-Cart's expert via **Live Chat** or **Submit a Ticket** to request our technical team to run the Demo process for your store (with or without custom requests).
