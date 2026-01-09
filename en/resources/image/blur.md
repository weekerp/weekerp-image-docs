---
description: 'Last updated: January 8, 2026'
icon: soundcloud
---

# Blur (Mosaic)

### Blur

You can apply a Gaussian blur effect to an image.\
It’s useful for placeholder previews, masking sensitive information, or softening backgrounds.

***

### `blur`



**Description**

Sets the Gaussian blur strength (`sigma`). Higher values produce a stronger blur.



**Format**

```
?blur={sigma}
```



**Supported values**

* Numeric value (`sigma`)
* Range: `0.3` to `20`



**Examples**

| Request                         | Result                    |
| ------------------------------- | ------------------------- |
| `?blur=1.5`                     | 약하게 블러 처리                 |
| `?width=800&format=webp&blur=2` | 800px 리사이즈 + WebP 변환 + 블러 |

***

#### Using with other options

* Combining `blur` with `width` is efficient for creating lightweight blurred thumbnails (previews).

```
?width=80&blur=8
```
