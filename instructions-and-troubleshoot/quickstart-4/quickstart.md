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

# Common Errors

<details>

<summary><strong>Connection successful, but demo migrated 0 records</strong></summary>

**Problem**\
The Free Demo Migration completes without error, but no products/customers/orders appear in the Target Store.

**What it usually means**

* Source store is empty or filters exclude most data.
* Only unsupported entities were selected.
* You are looking at the wrong store / wrong environment on the target side.

**How to fix**

1. **Verify source data really exists**
   * Log in to the **Source Store admin** and confirm there are active products, customers, and orders in the expected ranges (not all deleted, archived, or in draft).
2. **Check your demo configuration**
   * Re-open the demo migration configuration.
   * Make sure **Products, Customers, Orders, Blogs, CMS pages** are checked (not just obscure or custom entities).
3. **Confirm you’re checking the correct target**
   * Ensure you are logging into the same **Target Store** you used in the migration (same URL, same environment—no confusion with staging vs production).
4. **Re-run the demo**
   * Start a new Free Demo Migration after adjusting configuration and verify that sample data appears.

</details>

<details>

<summary><strong>Recent Data Migration finished, but no new data appears</strong></summary>

**Problem**\
Recent Data Migration completes successfully, but there are no new orders/customers/products on the Target Store.

**What it usually means**

* No new entities were created on the Source Store since the last migration run.
* You accidentally created a _new_ project instead of continuing the **original** one (so there’s no baseline to compare).
* Source and target mappings changed so new records don’t match the expected structure.

**How to fix**

1. **Confirm new data exists on the source**
   * Check the Source Store for **orders/customers/products dated after** the last full migration or last Recent Data Migration.
2. **Ensure you used the same migration project**
   * In **Migration Tool Management**, open the original project (the one that contains the completed full migration).
   * Use the **Recent Data Migration** option within that project, not a new migration.
3. **Check configuration hasn’t radically changed**
   * Verify entity selections and mappings are still compatible with the data structure.
   * Avoid changing core roles (e.g., mapping different fields to IDs) between full and Recent Data runs.
4. **Re-run Recent Data Migration**
   * If you confirm new source data and correct project usage, run another Recent Data Migration and re-check the target.

</details>

<details>

<summary><strong>Entity Points limit exceeded</strong></summary>

**Problem**\
You try to run a migration and see an **“Entity Points limit exceeded”** or need to change plans mid-process.

**What it usually means**

* Actual entity count is higher than roughly estimated.
* Source data grew (new orders, products, etc.) before you started the run.
* You chose a plan that’s too small for your needs.

**How to fix**

1. **Re-estimate entities**
   * Use the “check total entities” method for your store to get a precise estimate.
2. **Decide whether to split or upgrade**
   * Option A: **Split the migration** into multiple runs (e.g., products only, then orders/customers) if that fits your process.
   * Option B: **Upgrade the plan** so you can migrate everything in one run.
3. **Upgrade via your account**
   * Open **My Licenses / My Services**.
   * Select your migration and choose a higher **Entity Points plan**.
   * You only pay the **difference** between the previous and new plan.
4. **Re-run the migration**
   * Once the plan is upgraded, re-start the full migration or Recent Data Migration.

</details>

<details>

<summary>Duplicate products/orders appeared after testing</summary>

**Problem**\
Products or orders appear twice (or more) on the target store after multiple migrations or demos.

**What it usually means**

* You ran multiple **Full Migrations** to the same target without cleaning up test data.
* You imported the same file-based data multiple times.
* The target platform has no built-in deduplication for the entities you are migrating.

**How to fix**

1. **Identify test vs production data**
   * Use dates, naming conventions, or known IDs to distinguish demo/test entities from the latest production run.
2. **Clean up test data on the target store**
   * Remove test/demo products, customers, and orders from the target store before the final full migration (or use a staging store for testing).
3. **Avoid running full migration repeatedly on the same target**
   * Use:
     * **One full migration** for initial import.
     * **Recent Data Migration** for later syncs instead of full re-runs.
4. **Update internal deployment checklist**
   *   Document the sequence:

       1\) Demo → 2) Cleanup (if needed) → 3) Full migration → 4) Recent Data Migration → 5) Go-live.

</details>

<details>

<summary>Some data didn’t migrate (e.g., reviews, coupons)</summary>

**Problem**\
Migration completes, but certain entities (e.g., reviews, discount codes, custom app data) appear missing.

**What it usually means**

* Those entity types are **not supported** for your specific source → target combination.
* They were not selected in the **configuration**.
* They are stored in custom tables/extensions that require **Custom Migration** work.

**How to fix**

1. **Check supported entity list**
   * Review documentation for your specific source/target pair to confirm which entities are supported.
2. **Review migration configuration**
   * Confirm the missing entity type (e.g., Reviews, Coupons, CMS pages) was actually selected.
3. **Check source data structure**
   * Verify that the data exists in standard tables/fields and is not managed only by a third-party extension.
4. **Escalate as a custom requirement if needed**
   * If important data is stored in non-standard structures, note this for a potential **Custom Migration** scope, where custom logic or mapping is implemented.

</details>

<details>

<summary><strong>Images Missing or Broken After Migration</strong></summary>

**Problem**\
Products appear without images, or some images show as broken/missing on the Target Store.

**What it usually means**

One or more of the following:

* The **image file size** exceeds the maximum allowed by the Target Cart.
* A **CDN / security layer** on the Source Cart (e.g., Cloudflare) blocks remote downloading of images.
* The **image folder was moved** to a non-default/custom path, so KitConnect no longer “sees” it.
* The **image file format** is not supported by the Target Cart.
  * Common formats: `JPEG`, `JPG`, `PNG`, `WebP`, `GIF`, `BMP`, `SVG`.
  * `WebP`, `GIF`, `BMP`, and `SVG` are only supported on certain platforms.
* For open-source Target Carts, the PHP directive **`allow_url_fopen` is Off**, so the server refuses to read images over HTTP/HTTPS.

**How to fix**

1. **Check image size limits on the Target Cart**
   * Review the platform’s documentation or admin settings for **maximum image size** (per file).
   * If necessary, reduce the size of very large images and re-run image migration or re-upload those specific images.
2. **Verify CDN/firewall settings on the Source Cart**
   * If you use a CDN (Cloudflare or similar), check:
     * Are hotlink protections or download restrictions enabled?
     * Are there rules that block automated image downloads from external IPs?
   * Temporarily relax or whitelist image requests from the migration service, then re-test.
3. **Confirm image folder paths**
   * On the Source server, verify that product images are located in the **expected default directory** (e.g., the standard `media` or `uploads` path for your platform).
   * If you previously moved images into a **custom folder**, KitConnect may not detect them. Either:
     * Move them back into the default structure, or
     * Document this as a custom requirement for a tailored migration.
4. **Review supported image formats**
   * Check which formats your Target platform supports.
   * If it does not support certain formats (e.g., WebP or SVG), convert those images to a supported format (JPEG/PNG) and re-run image migration for the affected products.
5. **Enable `allow_url_fopen` for open-source Target Carts**
   * On the Target server, create or open a `php.ini` file in the main folder of your website.
   *   Add (or update) the following line:

       ```ini
       allow_url_fopen = On
       ```
   * Save the file and restart PHP / the web server if required by your hosting environment.
   * Re-run the migration or trigger an image re-fetch.
6. **Re-run images only if needed**
   * Once the root cause is fixed, you can run a **partial migration** that includes **Products (with images) only**, to avoid re-importing all other entities.

</details>

<details>

<summary><strong>Categories / Collections Look Wrong</strong></summary>

**Problem**\
After migration, the category structure appears flattened, products are in unexpected collections, or some categories seem missing.

**What it usually means**

* Source and target platforms use different concepts (e.g., categories vs collections), and the default mapping produced a different structure.
* Category entities were not selected or were filtered out in the migration configuration.
* Some categories exist but are hidden / disabled in the target theme.

**How to fix**

1. **Review the category tree on the target**
   * In the Target Store admin, open the category/collection management screen.
   * Confirm parent/child relationships and visibility (e.g., “hidden from navigation”).
2. **Check mapping and configuration**
   * Review category-related mapping in your migration project (e.g., how source categories map into Shopify collections).
   * Ensure category entities were selected in the configuration when you ran the migration.
3. **Verify demo vs full results**
   * If the demo looked correct but the full migration did not, compare configuration snapshots to see what changed between runs.
4. **Correct structure and, if needed, re-run specific entities**
   * If the issue is mostly structural (wrong parents), it may be easier to manually tweak a few key categories on the target.
   * For severe mismatches, adjust mapping and re-run migration for **Categories & Products** only.

</details>

<details>

<summary><strong>Customer Passwords Don’t Work on the New Store</strong></summary>

**Problem**\
Customers cannot log in to the new store using the same passwords they used on the old store.

**What it usually means**

* For **open-source → open-source** migrations, the **Customer Password Plugin** was not installed or configured, so the new store doesn’t know how to verify the old hashes.
* The source or target platform is **cloud-based**, where password hashes cannot be read or the login logic cannot be overridden.
* You are testing with accounts that were never migrated (or created only on the new store).

***

**A) When Password Migration&#x20;**_**Is**_**&#x20;Supported**

**Supported scenario**

* **From:** Any open-source platform
* **To:** One of the following open-source targets:
  * Magento
  * OpenCart
  * PrestaShop
  * WooCommerce / WordPress
  * Joomla / VirtueMart
  * Shopware

In this case, passwords are stored in the source database as **non-reversible hashes**. The migration tool **copies those hashes** to the new store. To make them usable, the Target Store must add the old verification method via the **Customer Password Plugin**.

**How it works**

* On login, the plugin:
  1. Takes the password entered by the customer on the Target Store.
  2. Applies the **same hashing algorithm** used by the Source Store.
  3. Compares the resulting hash with the migrated hash.
  4. If they match, the login succeeds and (optionally) the password may be re-hashed using the Target Store’s native method for future logins.

**How to fix (open-source → open-source)**

1. **Check that the Customer Password Plugin is included**
   * Confirm that your migration tool was purchased with the **Customer Password Plugin** option enabled (as shown in your Account Dashboard).
2. **Download the plugin from your Account Dashboard**
   * Go to **Account Dashboard → Migrations → Additional Modules**.
   * Download the **Customer Password Plugin** package for your Target Store.
3. **Install the plugin on the Target Store**
   * Follow the installation instructions for your specific platform (Magento, WooCommerce, etc.).
   * You can install the plugin **before or after** the data migration; it only needs to be active by the time customers start logging in.
4. **Test with a known customer account**
   * Pick a single test customer whose password you know from the old store.
   * Attempt to log in on the Target Store using their old credentials.
   * If login works for that account, the plugin is functioning as expected.
5. **If login still fails**
   * Re-check that:
     * The plugin is activated on the Target Store.
     * The correct source platform type is selected in the plugin (if it has configuration for hash types).
   * Once plugin configuration is verified, test again.

***

**B) When Password Migration Is&#x20;**_**Not**_**&#x20;Supported (Cloud-Based Targets)**

**Unsupported scenario**

* **Target** is a **cloud-based platform** (for example, most closed SaaS systems that do not expose password hashes or allow custom login logic).

In this case:

* The migration tool **cannot retrieve plain passwords** or sometimes even the hashed passwords.
* The Target platform often **does not allow overriding** the built-in login system.

**Expected behavior**

* Customers will need to **reset their password** when they first attempt to log in to the new site.
* The standard “Forgot your password?” flow sends them a reset link to create a new password under the Target platform’s security model.

**Recommended actions**

1. **Prepare a password reset plan**
   * Before go-live, plan to notify customers that:
     * Their account has been migrated.
     * They will need to **reset their password** the first time they log in.
2. **Optionally enable social login**
   * Where the Target platform supports it, consider enabling **Social Login** (Google, Facebook, etc.) to reduce friction for returning customers.
3. **Test the reset flow**
   * Verify that password reset emails are being sent correctly and that reset links work as expected.

</details>

<details>

<summary><strong>SEO URLs or 301 Redirects Not Working</strong></summary>

**Problem**\
Old product URLs from search engines or bookmarks do not redirect to the new product pages; some links result in 404 errors.

**What it usually means**

* 301 redirect generation/import was not enabled in the migration configuration.
* The target platform requires a separate app/module to activate redirects, and it was not installed.
* The domain cut-over changed paths, but redirects were configured with old assumptions.

**How to fix**

1. **Verify redirect configuration**
   * Check your migration configuration or add-on settings for **SEO URL Redirects** and confirm it was enabled.
   * On the target platform, confirm that redirects have been imported or created (via SEO app, redirect manager, or native tool).
2. **Test a few known old URLs**
   * Take old product URLs from Google search results or your own sitemap.
   * Paste them in a new browser session and verify if they redirect to the correct new pages.
3. **Check for conflicts with platform-level redirects**
   * Some platforms or apps may auto-generate redirects when slugs change.
   * Ensure custom redirects from migration do not conflict or overlap.
4. **Regenerate / import redirects if needed**
   * If redirects weren’t enabled originally, adjust configuration and re-run migration with SEO redirects enabled, or import a dedicated redirects file created by the migration tool.

</details>

<details>

<summary><strong>Entity Counts Don’t Match Between Source and Target</strong></summary>

**Problem**\
After migration, the number of products/customers/orders on the target does not exactly match the source.

**What it usually means**

* Only **active/visible** entities were migrated; drafts or archived records are excluded.
* Multi-store setups: you are counting entities across several stores on the source but migrated only one store’s data.
* Some entities (e.g., test or deleted records) are intentionally not included.

**How to fix**

1. **Align how you count entities**
   * On the source, count **active/live** products, customers, and orders (exclude drafts, disabled items, or test records).
   * On the target, use equivalent filters for a like-for-like comparison.
2. **Check platform and store scope**
   * For multi-store platforms, verify whether you migrated all stores or only a specific store view.
   * Adjust expectations accordingly if the migration was scoped to a subset.
3. **Review migration configuration**
   * Confirm all relevant entity types (e.g., products, variants, customers, orders) were selected in the configuration.
4. **Investigate specific gaps**
   * Instead of focusing only on total counts, identify a few missing examples and check if they share a pattern (e.g., specific status, date range, store view).
   * Use that pattern to adjust configuration or plan a targeted partial re-run.

</details>

