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

# Technical Errors

<details>

<summary><strong>API 401 / 403 / 404 / 500 errors</strong></summary>

**Problem**\
The migration tool shows HTTP error codes like **401**, **403**, **404**, or **500** when testing or using an API connection.

**What it usually means**

* **401 Unauthorized** → wrong or expired credentials.
* **403 Forbidden** → credentials exist but lack permissions, or IP is blocked.
* **404 Not Found** → wrong API endpoint or URL path.
* **500 Server Error** → problem on the platform or hosting side (not the migration tool).

**How to fix**

1. **Re-check credentials and scopes**
   * For **401**: re-copy the API key/token/secret and paste again. Make sure the app is active and not revoked.
   * For **403**: check **scopes/permissions** and IP allowlists; ensure read (and write on target) is granted.
2. **Verify URL / endpoint**
   * For **404**: confirm you are using the correct base URL and path (e.g., some systems require `/api` or a specific subdomain).
3. **Check platform status or logs**
   * For **500**: check platform status pages or hosting error logs for server-side issues; re-test once the platform is stable.
4. **Retry and monitor**
   * After changes, re-run the connection test and look for changes in the error code.

</details>

<details>

<summary><strong>API rate limiting / 429 Too Many Requests</strong></summary>

**Problem**\
You see **429 Too Many Requests** or a rate-limit warning from the platform while running a migration.

**What it usually means**

* The migration is sending requests faster than the platform allows (especially on SaaS platforms with strict per-second/minute limits).

**How to fix**

1. **Pause and retry later**
   * Stop the migration if possible and re-run it during **off-peak hours** when rate limits are less likely to be hit.
2. **Reduce concurrency if configurable**
   * If there are advanced settings for request concurrency, lower them so the migration sends fewer parallel requests.
3. **Check platform-specific rate limits**
   * Some platforms document safe request rates; align your migration schedule with these limits to avoid further throttling.

</details>

<details>

<summary><strong>KitConnect: “Bridge not found / cannot connect database”</strong></summary>

**Problem**\
Connecting via KitConnect returns errors such as **“bridge not found”**, **“cannot connect to database”**, or a blank/403 page.

**What it usually means**

* KitConnect was uploaded to the wrong directory or URL doesn’t match.
* Web server lacks permission to run the KitConnect script.
* Database credentials inside KitConnect config are wrong, or database server is not reachable.

**How to fix**

1. **Check folder location and URL**
   * Confirm the KitConnect folder is inside the **web root** (e.g., `public_html`, `www`, `httpdocs`).
   * Visit `https://yourstore.com/<kitconnect_folder>` in a browser. If you get a 404, move the folder to the correct root or update the URL.
2. **Check file permissions**
   * Ensure directories are typically `755` and files are `644`.
   * Correct any misconfigured permissions that block PHP execution.
3. **Verify database credentials in KitConnect config**
   * Open the KitConnect config file via File Manager/FTP and verify database host, username, password, and database name.
   * Ensure the database user has read access to the store’s tables.
4. **Review security / firewall rules**
   * Look for 403 or security pages when opening the KitConnect URL.
   * Temporarily whitelist the KitConnect path or adjust WAF/security plugin rules as needed.

</details>

<details>

<summary><strong>FTP/SFTP errors (530 / 421 / 425)</strong></summary>

**Problem**\
Your FTP/SFTP client logs errors such as **530 Login incorrect**, **421 Too many connections**, or **425 Can’t open data connection** when you try to upload KitConnect or export files.

**What it usually means**

* Wrong username/password or protocol.
* Too many parallel connections from your IP.
* Firewall/NAT issues interfering with FTP data channels.

**How to fix**

1. **Confirm credentials and protocol**
   * Re-check hostname, username, password, and port from your hosting panel.
   * Use **SFTP** (port 22) if available; many hosts disable plain FTP.
2. **Enable passive mode (FTP only)**
   * In your FTP client settings, turn **Passive mode** ON to avoid firewall/NAT issues.
3. **Reduce simultaneous connections**
   * Lower the maximum concurrent connections to 2–3 to avoid **421 Too many connections** on shared hosting.
4. **Try hosting File Manager if issues persist**
   * Use cPanel File Manager (or equivalent) to upload a `.zip` and extract it directly on the server

</details>

<details>

<summary><strong>Timeouts or very slow migrations</strong></summary>

**Problem**\
Migrations take much longer than expected or appear to stall.

**What it usually means**

* Very large data volume relative to plan and platform performance.
* Source/target platform is slow or overloaded.
* Strict API rate limits force the migration to throttle requests.
* Network latency between the migration server and your store’s hosting is high.

**How to fix**

1. **Check platform performance**
   * Confirm your Source and Target stores are responsive via browser and that your hosting provider is not reporting performance incidents.
2. **Avoid peak hours**
   * Schedule full migrations and Recent Data runs during **off-peak times** to reduce contention and rate limiting.
3. **Split migrations if necessary**
   * For extremely large datasets, consider splitting the job:
     * Products in one run
     * Customers & orders in another
4. **Monitor for partial progress**
   * Verify that new data continues appearing in the target, even if the total runtime is large.
   * If progress completely stops (no new entities imported over time), collect logs and escalate.

</details>

<details>

<summary><strong>SSL / HTTPS and mixed-content issues</strong></summary>

**Problem**\
The migration tool or browser warns about SSL problems, or the store is accessible only via HTTP while the migration requires HTTPS.

**What it usually means**

* SSL certificate is missing, expired, or misconfigured.
* Redirect loops or mixed HTTP/HTTPS content interfere with API calls or KitConnect access.

**How to fix**

1. **Check HTTPS manually**
   * Visit `https://yourstore.com` in a browser and confirm:
     * The certificate is valid (no warnings).
     * The site loads without redirect loops.
2. **Update URLs in the migration configuration**
   * Use the **HTTPS** version of your store URL and KitConnect URL where supported.
3. **Work with your hosting provider**
   * If there are certificate or redirect issues, fix them at hosting level before re-running the migration.

</details>

<details>

<summary><strong>Database Connection / SQL Errors</strong></summary>

**Problem**\
You see errors mentioning database connection or SQL problems (e.g., “SQLSTATE\[HY000]”, “could not connect to database”, “access denied for user…”).

**What it usually means**

* Database credentials in KitConnect or platform config are incorrect.
* The database user does not have rights to read the store’s tables.
* The database server is unavailable, overloaded, or blocked by firewall rules.

**How to fix**

1. **Verify DB credentials**
   * Compare the host, database name, username, and password in KitConnect or platform settings with the values from your hosting control panel.
   * Correct any discrepancies and save.
2. **Test access via phpMyAdmin or equivalent**
   * Log in to phpMyAdmin (or another DB tool) using the same credentials.
   * If login fails there as well, update the credentials or contact hosting support.
3. **Check permissions**
   * Ensure the database user has **SELECT** (read) permissions on all relevant tables.
   * For some operations, additional permissions may be required (though migration is read-focused).
4. **Monitor DB server health**
   * Ask your hosting provider if there are resource limits or errors on the database server (connection limits, CPU spikes, etc.).
   * Retry the migration once stability is confirmed.

</details>

<details>

<summary><strong>PHP Memory / Timeout / File-Size Limits</strong></summary>

**Problem**\
You encounter white screens, generic 500 errors, or logs mentioning `memory_limit`, `max_execution_time`, `post_max_size`, or `upload_max_filesize` while running migrations, KitConnect, or large exports.

**What it usually means**

* The server is hitting its PHP **memory** or **execution time** limit.
* Uploaded files are larger than the allowed **upload\_max\_filesize** or **post\_max\_size**.

**How to fix**

1. **Identify the limit in error logs**
   * Check your hosting error logs (or ask your host) for messages about memory exhaustion or timeouts.
2. **Request increased limits from your host**
   * Typical adjustments:
     * `memory_limit` (e.g., 256M or higher, depending on store size)
     * `max_execution_time` and `max_input_time`
     * `upload_max_filesize` and `post_max_size` (for file imports)
3. **Reduce workload per operation if possible**
   * For file exports/imports, split large datasets into smaller files.
   * For extremely large migrations, consider splitting runs by entity type.
4. **Re-run migration after changes**
   * Once limits are increased, repeat the operation that previously failed.

</details>

<details>

<summary><strong>Disk Space / Storage Limit Reached</strong></summary>

**Problem**\
Exports fail or the server reports errors like “no space left on device”, “disk quota exceeded”, or backup creation fails.

**What it usually means**

* Your hosting account or server has reached its storage quota.
* Large backups, logs, or old media files are filling the disk.

**How to fix**

1. **Check disk usage in hosting panel**
   * Review total disk usage and per-directory usage (if available).
2. **Clean up non-essential files**
   * Remove old backups, unused media, temporary files, or logs.
   * Empty trash/recycle bins within the control panel if applicable.
3. **Retry exports or KitConnect operations**
   * Once disk space has been freed, re-run the export or migration step.
4. **Consider upgrading storage**
   * For very large stores, you may need a higher hosting plan or dedicated storage for media.

</details>

<details>

<summary><strong>File Permission / 403 Errors on Key Scripts or Folders</strong></summary>

**Problem**\
Accessing certain URLs (KitConnect, admin scripts, export endpoints) returns 403 Forbidden or “permission denied”, even though credentials are correct.

**What it usually means**

* File or folder permissions prevent the web server from reading/executing code.
* Security modules or .htaccess rules are blocking direct access to those paths.

**How to fix**

1. **Review permissions on critical folders**
   * Typical values:
     * Folders: `755`
     * Files: `644`
   * Avoid `777` except as a very short-lived test under guidance from your host.
2. **Check .htaccess or platform security rules**
   * Look for rules that deny access to certain directories (e.g., `Deny from all`).
   * Temporarily comment out or relax rules for the affected path, then re-test.
3. **Inspect security plugins / WAF**
   * For CMS/shops with security plugins, whitelist the specific URL (KitConnect, API endpoint, export script).
   * In server-level WAF, ask your host to allow those requests.
4. **Confirm access from a browser**
   * Visit the specific URL in incognito mode and verify you no longer get a 403.
   * Then re-run the migration connection test.

</details>
