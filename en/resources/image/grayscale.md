---
description: 'Last updated: January 8, 2026'
icon: cloud-showers-heavy
---

# Grayscale

#### Grayscale <a href="#grayscale" id="grayscale"></a>

You can convert an image to grayscale **(black and white)**. This is useful for consistent thumbnail styling, setting a specific mood, or emphasizing content through color contrast.

#### `grayscale` <a href="#grayscale-1" id="grayscale-1"></a>



**Description**

Converts the image to grayscale (black and white).



**Format**

```
?grayscale=true
```



**Supported values**

* `true | false`
* Applied only when `true` (not set or `false` → no effect)



Examples

| `?grayscale=true`                       | 흑백으로 변환                   |
| --------------------------------------- | ------------------------- |
| `?width=600&format=webp&grayscale=true` | 600px 리사이즈 + WebP 변환 + 흑백 |

***



#### Using with other options <a href="#undefined" id="undefined"></a>

* `grayscale` works seamlessly with other transformation options such as `format` and `width`.

```
?width=600&format=webp&grayscale=true
```

Mixing the color and grayscale versions can help create an effect where **only the content you want to highlight remains in color**.

