---
description: Use this when you prefer a browser-based method instead of an FTP client.
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

# cPanel File Manager

#### **Prerequisites**

* Access to your hosting control panel (cPanel or equivalent).

#### **How-to** Upload and Extract Files

1. **Open File Manager**
   * Log in to your hosting account’s control panel.
   * Open **cPanel** (or equivalent) and click **File Manager** under the “Files” section.
2. **Go to your web root**
   * In the left folder tree, navigate to your site’s web root, usually:
     * `public_html`
     * `httpdocs`
     * `www` or `wwwroot`
3. **Upload the ZIP file**
   * With the web root selected, click the **Upload** button in the toolbar.
   * In the upload screen, choose the `.zip` file from your computer (e.g., `kitconnect.zip`).
   * Wait for the upload to reach 100%, then close the upload tab.
4. **Extract the ZIP file**
   * Back in File Manager, click **Reload** if necessary; you should see the uploaded `.zip` file.
   * Right-click the `.zip` file and select **Extract** (or **Unzip**).
   * Confirm the extraction path (your web root), and complete the extraction.

At this point, the KitConnect folder or other required files are fully deployed in your web root and ready for use by the migration tool.
