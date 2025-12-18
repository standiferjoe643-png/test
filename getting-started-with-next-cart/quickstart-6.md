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

# Go-Live Checklist (After Your Migration)

#### Purpose

Use this checklist **after your full migration has completed** and before you point your domain to the new store. It ensures that your data is correct, your new store is fully in sync using **Recent Data Migration**, and your first live orders and redirects work as expected.

***

#### Phase 1 – Site Walk-Through (Verify Your Data)

**Goal:** Confirm that key data on your Target Store is present, linked correctly, and usable before anything goes live.

1. **Sign in to your Target Store admin**
   * Use the **temporary URL** or staging domain for your new store.
   * Ensure you are logged in with an account that has full admin permissions.
2. **Check products**
   * Open **5–10 complex products** (multiple variants, images, pricing rules).
   * Confirm:
     * Product title, description, and SKU.
     * All variants/options (sizes, colors, etc.) are present and selectable.
     * Main image + gallery images appear correctly.
     * Prices, sale prices, and tax rules look reasonable.
3. **Check categories / collections**
   * Review your **category or collection tree** in the Target Store admin.
   * Confirm:
     * Parent/child hierarchy is correct.
     * Products appear in expected categories/collections.
     * Navigation menus reference valid categories/collections (no empty links).
4. **Check customers & orders**
   * Locate **several migrated customers**, including one with multiple orders.
   * Confirm:
     * Customer contact details (name, email) are present.
     * Order history is correctly linked to each customer.
     * Order totals, line items, and statuses match your expectations.
   * If you are using **Customer Password Plugin** (where supported):
     * Log in as a test customer on the new store using the **old password** to confirm password migration is working.
5. **Check content & SEO-relevant pages**
   * Verify key **CMS pages** (e.g., Home, About Us, Contact, Shipping & Returns).
   * Check:
     * Blog posts and key landing pages are present.
     * URLs look structurally correct for the new platform.
     * Basic SEO metadata (page titles, meta descriptions) appears where expected, if it was part of the migration.
6. **Log any gaps**
   * For each issue, note:
     * Example URL or entity ID.
     * Expected vs. actual behavior.
   * Classify gaps as either:
     * **Configuration / mapping adjustment** (handled in migration settings), or
     * **Custom Migration requirement** (third-party app data, highly custom fields, etc.).

***

#### Phase 2 – Final Sync With Recent Data Migration

**Goal:** Bring your new Target Store fully up to date by syncing only the **new data created after the full migration** finished (orders, customers, products), using **Recent Data Migration**.

1. **Confirm your full migration is stable**
   * Ensure no additional configuration changes are pending.
   * Resolve any **blocking issues** found during Phase 1 (e.g., mapping errors, critical missing fields).
2. **Freeze changes on the Source Store (where possible)**
   * Choose a **low-traffic window** (late night in your core market).
   * Ask your team to avoid:
     * Editing products or categories.
     * Installing new apps that change data structures.
     * Making bulk data updates during the final sync window.
3. **Run Recent Data Migration**
   * Go to your Next-Cart **Account Dashboard** and open the completed migration record.
   * Select **Recent Data Migration** (do not select any options that would clear data or re-run a full remigration).
   * Confirm:
     * The source and target connections are still valid.
     * The time window for “recent data” is correct (based on when the full migration ended).
4. **Verify synced data**
   * After Recent Data Migration finishes, check:
     * New orders placed since the full migration exist in the Target Store.
     * Any newly created customers are present and linked to the new orders.
     * Any newly added or updated products are reflected correctly (stock, price, visibility).

***

#### Phase 3 – Point Your Domain (DNS Cut-Over)

**Goal:** Safely switch your live domain from the old store to the new Target Store once data is fully verified and synced.

1. **Prepare DNS information**
   * Collect the new store’s:
     * IP address (for self-hosted / open-source setups), or
     * CNAME/URL (for SaaS platforms like Shopify, BigCommerce, etc.).
   * Confirm DNS settings recommended by your target platform’s documentation.
2. **Update DNS at your registrar**
   * Log in to your **domain registrar** (e.g., GoDaddy, Namecheap, Cloudflare).
   * Locate DNS/Name Server settings for your domain (e.g., `mystore.com`).
   * Update the relevant records (A or CNAME) to point to your new store.
3. **Allow time for propagation**
   * DNS changes can take from a few minutes to several hours to propagate globally.
   * During this time, some visitors may still see the old store while others see the new one.
   * Monitor:
     * Whether the **admin URL** and **front-end** both resolve to the new store.
     * If any SSL certificate warnings appear (resolve via your hosting or SaaS platform if needed).
4. **Lock down the old store (optional but recommended)**
   * Once you are sure the new store is live for most visitors:
     * Disable checkout on the old store or show a maintenance message.
     * Add a clear note that the store has moved, if the old URL is still accessible.

***

#### Phase 4 – Post-Launch Smoke Test

**Goal:** Confirm that the live store works end-to-end for real users and that SEO-critical redirects behave correctly.

1. **Place a real test order**
   * Use a **real payment method** (card or payment gateway that you normally use).
   * Complete the full checkout flow:
     * Add a product to cart.
     * Apply a coupon or discount if that is part of your normal flow.
     * Confirm shipping and tax calculations look correct.
   * Verify:
     * Payment is captured/authorized successfully.
     * The order appears in the Target Store admin with correct details.
     * All related emails (order confirmation, payment receipts) are sent and formatted correctly.
2. **Check 301 redirects and legacy URLs**
   * In a private/incognito browser, search for some of your old product URLs in Google or open URLs from your old sitemap.
   * Confirm:
     * Old URLs automatically redirect to the correct new product or page.
     * No obvious 404 pages for key products, categories, or CMS pages.
   * If you used Next-Cart’s 301/URL Redirect add-ons, this step validates the mapping.
3. **Monitor basic site health**
   * Check:
     * Homepage load time and key category pages.
     * Mobile navigation and checkout usability.
     * Error logs in your Target Store or hosting control panel for any new critical errors.
   * Optionally, run:
     * A quick crawl with an SEO tool (to check for broken links and server errors).
     * Analytics events to confirm page views and conversions are tracking correctly.
4. **Document completion**
   * Record:
     * Date and time of go-live.
     * DNS change details and who approved them.
     * Any known limitations or backlog items (e.g., minor design tweaks, non-critical redirects).
   * Store this record with your internal documentation and governance notes, alongside backup and rollback information.
