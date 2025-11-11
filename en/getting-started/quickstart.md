---
icon: bullseye-arrow
---

# Quickstart

#### 1️⃣ Create an Account

Go to [**weekerp.com**](https://weekerp.com).

Select **Google Login** to sign up.

***

#### 2️⃣ Connect Your Storage

Your images must be stored in one of the following locations:

* **Cloud Storage**
* **Your Web Server**

The origin of your resources can be connected from one of the following sources:

| Type           | Description                          | Docs                      |
| -------------- | ------------------------------------ | ------------------------- |
| **AWS S3**     | Connect an existing S3 bucket.       | \[AWS Connection Guide]   |
| **GCP GCS**    | Connect a GCP Storage bucket.        | \[GCP Connection Guide]   |
| **Azure Blob** | Connect an Azure Blob container.     | \[Azure Connection Guide] |
| **Web Proxy**  | Cache external image URLs via proxy. | \[Web Proxy Guide]        |

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

