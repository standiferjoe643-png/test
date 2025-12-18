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

# Cyberduck

#### **Prerequisites**

* Cyberduck installed from `cyberduck.io`.
* SFTP credentials: **Server (Host)**, **Username**, **Password**, **Port**.

#### How-to Connect and Upload Files

1. Open **Cyberduck**.
2. Click **Open Connection**.
3. In the connection window, set:
   * **Protocol:** **SFTP (SSH File Transfer Protocol)**
   * **Server:** your SFTP hostname (e.g., `sftp.yourstore.com`)
   * **Port:** `22`
   * **Username:** your SFTP username
   * **Password:** your SFTP password
4. Click **Connect**, and accept the host key the first time if prompted.
5. In the Cyberduck window, navigate to your web root (`public_html`, `www`, or `httpdocs`).
6. On your computer (Finder or File Explorer), locate `kitconnect.zip` or other files you want to upload.
7. **Drag and drop** the file from your desktop/file manager into the Cyberduck window.
8. Watch the **Transfers** window; when the upload is complete, the file is on your server.
