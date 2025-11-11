---
icon: slash-forward
---

# BasePath

**BasePath** is an option that defines the root directory path within a bucket from which resources are served. In other words, it specifies the **top-level directory** that the CDN will use as the base when fetching files.

***

#### Example

Assume the following files are stored in your bucket:

```
/dog.jpg
/assets/cat.png
```

In this case, **BasePath** can be configured in the following :

<table><thead><tr><th width="96.999755859375">Setting</th><th width="294.7144775390625">Description</th><th>Example (Weekerp)</th></tr></thead><tbody><tr><td><code>/</code></td><td>Access all files from the root directory of the bucket.</td><td><code>https://cdn.weekerp.com/image/mysource/dog.jpg</code></td></tr><tr><td><code>/assets</code></td><td>Set the <code>assets</code> folder as the root directory.</td><td><code>https://cdn.weekerp.com/image/mysource/cat.jpg</code></td></tr><tr><td><code>/</code> </td><td>When the <code>assets</code> folder is <strong>not</strong> defined as BasePath, the folder name remains part of the path.</td><td><code>https://cdn.weekerp.com/image/mysource/assets/cat.jpg</code></td></tr></tbody></table>



***

#### Notes

* **BasePath** can be set individually for each **Source** (bucket).
*   The configured BasePath is automatically appended to the path during CDN requests.

    ```
    https://cdn.weekerp.com/image/{source}/{basePath}/cat.png
    ```
* When set to the root (`/`), all paths are served as-is.
