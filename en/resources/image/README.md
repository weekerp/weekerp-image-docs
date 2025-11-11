---
icon: image-landscape
---

# Image API

### **Image Processing**

The **Weekerp Image API** allows you to perform image transformations simply through URL parameters, including:

* **Resize** (width / height / size)
* **Format conversion** (JPEG, PNG, WebP, AVIF, etc.)
* **Quality adjustment** (quality)
* **Resize strategy** (fit)
* **Crop position** (position)

All processing is performed **on demand** at request time.\
The transformed result is cached at the CDN edge upon the first request,\
and all subsequent requests with the same parameters are served instantly from cache.

When the same image is requested again with identical parameters,\
the cached version is returned immediately — ensuring zero delay.

For more details, see the **Cache** documentation.

***

#### Base Request Format

```
https://cdn.weekerp.com/image/{source}/{path/to/image}.{ext}?{options}
```

***

#### Examples

| Description                        | Request URL                                                          |
| ---------------------------------- | -------------------------------------------------------------------- |
| Resize to 800px width, auto height | `https://cdn.weekerp.com/image/demo/photo.jpg?w=800`                 |
| Resize to 400×400 square           | `https://cdn.weekerp.com/image/demo/photo.jpg?w=400&h=400&fit=cover` |
| Compress to 70% quality            | `https://cdn.weekerp.com/image/demo/photo.jpg?w=1200&q=70`           |

***

#### Parameters

| Option     | Alias           | Description                   | Example                                                          |
| ---------- | --------------- | ----------------------------- | ---------------------------------------------------------------- |
| `size`     | `size`, `s`     | Set width and height together | `"800x600"`                                                      |
| `width`    | `width`, `w`    | Specify width in pixels       | `800`                                                            |
| `height`   | `height`, `h`   | Specify height in pixels      | `600`                                                            |
| `format`   | `format`, `f`   | Output format                 | `'webp'`, `'avif'`, `'jpg'`, `'png'`, `'gif'`, `'tiff'`, `'svg'` |
| `quality`  | `quality`, `q`  | Compression quality (1–100)   | `80`                                                             |
| `fit`      | `fit`           | Resize strategy               | `'cover'`, `'contain'`, `'fill'`, `'inside'`, `'outside'`        |
| `position` | `position`, `p` | Crop anchor position          | `'centre'`, `'top'`, `'bottom'`, `'left'`, `'right'`             |

***

#### Notes

* The **original image is never modified**.
* Transformed images are cached at the CDN edge and instantly served for identical requests.
* The default output format follows the original file’s extension,\
  but you can use the `f` parameter to convert formats (e.g., WebP, AVIF).\
  \<br>**Example:**\
  `https://cdn.weekerp.com/image/demo/photo.jpg?w=800&f=webp`

***

#### Recommendations

* The **maximum recommended response size** is **1MB** (current beta limitation).\
  For immediate processing needs, contact **help@weekerp.com**.
* Very large source images may fail during CDN processing.
* For high-capacity files, it’s recommended to serve them directly via the `/file` endpoint.
