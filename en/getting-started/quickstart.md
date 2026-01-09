---
icon: bullseye-arrow
---

# Quickstart

#### 1️⃣ Create an Account

1. Go to [**weekerp.com**](https://weekerp.com).
2. Select **Google Login** to sign up.

***

#### 2️⃣ Connect Your Storage

Your images must be stored in one of the following locations:

* **Cloud Storage**
* **Your Web Server**

The origin of your resources can be connected from one of the following sources:

<table><thead><tr><th width="139.85711669921875">Type</th><th width="401.142822265625">Description</th><th>Docs</th></tr></thead><tbody><tr><td>AWS S3</td><td>Connect an existing S3 bucket.</td><td><a data-mention href="../storage/connect/aws.md">aws.md</a></td></tr><tr><td>GCP GCS</td><td>Connect a GCP Storage bucket.</td><td><a data-mention href="../storage/connect/gcp.md">gcp.md</a></td></tr><tr><td>Azure Blob</td><td>Connect an Azure Blob container.</td><td><a data-mention href="../storage/connect/azure.md">azure.md</a></td></tr><tr><td>Web Proxy</td><td>Cache external image URLs via proxy.</td><td><a data-mention href="../storage/connect/web.md">web.md</a></td></tr></tbody></table>



You can create multiple storage sources, and modify or delete them anytime.

***

#### 3️⃣ Apply Image CDN

Once connected, you can load images through Weekerp CDN as follows:

```html
<img src="https://cdn.weekerp.com/image/{workspace}/example.jpg?w=800&q=80" />
```

| Parameter | Description                             |
| --------- | --------------------------------------- |
| `source`  | Unique data source name                 |
| `w`       | Image width to resize                   |
| `q`       | Quality (1–100)                         |
| `f`       | Format conversion (`jpg`, `webp`, etc.) |

After the first resizing, all images are cached and served globally for ultra-fast response.

***

#### 4️⃣ Billing & Subscription

Weekerp uses a **usage-based billing model**.\
You can find detailed information here:

