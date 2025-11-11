---
icon: tickets-perforated
---

# format

#### Format Conversion

**Format & Quality**

Weekerp CDN allows you to change the **output format** and adjust **compression quality** at request time.\
This helps reduce bandwidth usage, improve page loading speed, and ensure browser compatibility.

***

#### `format`

**Description**\
Specifies the output format of the image.\
If not specified, the original format is returned as-is.

**Format**

```
?format={type}
```

**Aliases**

* `f` (short form)
* `format` (full form)

***

#### Supported Formats

| Format        | Description                            | Feature                            |
| ------------- | -------------------------------------- | ---------------------------------- |
| **webp**      | High-efficiency compression format     | Supported by most modern browsers  |
| **avif**      | Next-generation high-efficiency format | Higher compression ratio than WebP |
| **jpeg, jpg** | Common lossy format                    | Balanced compatibility             |
| **png**       | Lossless compression format            | Supports transparency              |
| **gif**       | Animated image format                  | Suitable for simple animations     |
| **tiff**      | High-quality format                    | Used for printing or archiving     |
| **svg**       | Vector format                          | Ideal for logos and icons          |

***

#### Examples

| Request        | Result            |
| -------------- | ----------------- |
| `?format=webp` | Converted to WebP |
| `?format=avif` | Converted to AVIF |
| `?f=png`       | Converted to PNG  |

***

#### `quality`

**Description**\
Adjusts the quality of **lossy** image formats.\
Lower values reduce file size but decrease image detail.

**Format**

```
?quality={1~100}
```

**Alias**

* `q`

***

#### Examples

| Request | Result                         |
| ------- | ------------------------------ |
| `?q=90` | High quality (larger size)     |
| `?q=60` | Medium quality (default level) |
| `?q=30` | Low quality (smaller size)     |

***

#### Using Together

```
?format=webp&q=75
```

* Applies to **AVIF**, **WebP**, **JPEG**, and other lossy formats.
* For **PNG** and **SVG** (lossless formats), the `quality` parameter is ignored.

***

#### MIME Auto Conversion

When a format is specified, the response header `Content-Type` automatically changes based on the requested format.

| Format       | Content-Type    |
| ------------ | --------------- |
| `webp`       | `image/webp`    |
| `avif`       | `image/avif`    |
| `jpeg / jpg` | `image/jpeg`    |
| `png`        | `image/png`     |
| `svg`        | `image/svg+xml` |

***

💡 **Tip:**

* **WebP** is supported by most modern browsers and can reduce file size by **25–35%** compared to JPEG.
* **AVIF** offers even greater compression efficiency but may not be compatible with older browsers.
