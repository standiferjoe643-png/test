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

# FileZilla

#### **Prerequisites**

* FileZilla **Client** installed from the [official site](https://filezilla-project.org).
* SFTP credentials from your hosting provider: **Host**, **Username**, **Password**, **Port** (usually 22 for SFTP).

#### How-to Connect and Upload Files

1. **Open FileZilla.**
2. In the **Quickconnect** bar, enter:
   * **Host:** `sftp://your-hostname` (e.g., `sftp://sftp.yourstore.com`)
   * **Username:** your SFTP username
   * **Password:** your SFTP password
   * **Port:** `22`
3. Click **Quickconnect**. Accept the host key warning the first time if prompted.
4. In the **left pane** (Local Site), navigate to the folder on your computer that contains `kitconnect.zip` or the files you need to upload.
5. In the **right pane** (Remote Site), navigate to your web root (`public_html`, `www`, or `httpdocs`).
6. **Drag and drop** the file(s) from the left pane to the right pane.
7. Wait until the **transfer status** shows as successful; the files are now on your server.

If you uploaded `kitconnect.zip`, proceed to the **cPanel File Manager** to extract it.
