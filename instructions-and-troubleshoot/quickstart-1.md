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

# KitConnect Setup

Use these steps when your Source store is open-source / self-hosted and Next-Cart requires KitConnect for the connection.

#### **Prerequisites**

* A **KitConnect package (.zip)** downloaded from Next-Cart.
* **FTP/SFTP access** (via FileZilla, Cyberduck, WinSCP) **or** a hosting File Manager (e.g., cPanel).
* The **web root folder** for your store, usually named **public\_html**, **www**, or **httpdocs**.

#### **Install KitConnect on your server**

1. **Download and unzip KitConnect**

* Download the KitConnect package from your Next-Cart account for the current migration.
* Unzip the package on your local computer. This creates a folder such as **kitconnect\_xxx**.<br>

2. **Connect to your server**

* Open your FTP/SFTP client or hosting File Manager.
* Log in with your FTP/SFTP or hosting credentials.<br>

3. **Navigate to your web root**

* In your client or File Manager, go to the folder where your store is installed.
* This is typically **public\_html**, **www**, **httpdocs**, or a similar directory.<br>

4. **Upload the KitConnect folder**

* Upload the entire unzipped KitConnect folder (e.g., **kitconnect\_xxx**) into your web root.
* Do not rename the folder unless specifically instructed.<br>

5. **Set basic permissions (if needed)**

* Ensure directories under your web root are set to standard permissions (e.g., **755** for folders, **644** for PHP files), following your host’s security guidelines.

#### **Link KitConnect to your migration**

6. Form the KitConnect URL

* The KitConnect URL is usually:\
  **https://yourstore.com/kitconnect\_xxx**
* Replace **yourstore.com** and **kitconnect\_xxx** with your actual domain and folder name.<br>

7. **Enter the URL in the migration tool**

* In the Next-Cart setup screen, select your open-source platform as the **Source Cart**.
* Paste the **full KitConnect URL** into the **Source Store URL** (or equivalent) field.<br>

8. **Test the connection**

* Use the **connection test** in the migration wizard (or proceed to the demo).
* If the connection fails, verify:
  * The KitConnect folder is in the correct root directory.
  * The URL is correct and publicly accessible over HTTPS.
  * No security or firewall rules are blocking access to the script.

#### **After the migration**

9. **Disable / remove KitConnect when finished**

* Once your migration and Recent Data Migration runs are fully complete and verified, you can **delete the KitConnect** **folder** from your server.
* KitConnect does not modify your core store code; it acts as a temporary, read-only bridge that can safely be removed after use.
