---
description: 'Last updated: January 8, 2026'
icon: copy
---

# Universal File API

#### File Endpoint

The **`/file`** endpoint allows you to reliably serve static files — such as **PDF**, **MP4**, or **ZIP** — through Weekerp CDN **without needing any custom API**.

This API applies universally to **all file types**, including images, videos, and documents.

```
https://cdn.weekerp.com/file/{source}/file.pdf
```

***

#### Examples

| Description         | Example URL                                      |
| ------------------- | ------------------------------------------------ |
| Serve a PDF file    | `https://cdn.weekerp.com/file/docs/guide.pdf`    |
| Serve an MP4 video  | `https://cdn.weekerp.com/file/media/example.mp4` |
| Serve a ZIP archive | `https://cdn.weekerp.com/file/backup/site.zip`   |

#### Need a specific feature?

{% hint style="info" %}
If you need support for special file types—such as **PDF, JSON, or CSS**—we can add it quickly.\
When you request a new feature, the Weekerp team will prioritize it and implement it as soon as possible.
{% endhint %}

Request new features here: [feature.md](../getting-started/feature.md "mention")&#x20;
