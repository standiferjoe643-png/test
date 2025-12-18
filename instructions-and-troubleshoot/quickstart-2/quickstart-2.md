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

# WinSCP

#### **Prerequisites**

* WinSCP installed from `winscp.net`.
* SFTP credentials: **Host**, **Username**, **Password**, **Port**.

#### How-to Connect and Upload Files

1. Open **WinSCP**. In the **Login** window:
   * **File protocol:** **SFTP (SSH File Transfer Protocol)**
   * **Host name:** your SFTP hostname (e.g., `sftp.yourstore.com`)
   * **Port number:** `22`
   * **User name:** your SFTP username
   * **Password:** your SFTP password
2. (Optional) Click **Save** if you want WinSCP to remember this connection profile.
3. Click **Login** and accept the host key on first connection.
4. In **Commander view** (recommended), the **left pane** shows your local files and the **right pane** shows the server.
5. In the right pane, navigate to your web root (`public_html`, `www`, or `httpdocs`).
6. In the left pane, navigate to the folder that contains `kitconnect.zip` or the file you want to upload.
7. **Drag and drop** the file from the left pane to the right pane.
8. Confirm the transfer when prompted; wait until the transfer dialog shows success.

If you uploaded `kitconnect.zip`, extract it using your hosting **File Manager**.
