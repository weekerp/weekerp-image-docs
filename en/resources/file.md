---
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
