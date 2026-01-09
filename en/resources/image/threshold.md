---
description: 'Last updated: January 8, 2026'
---

# Threshold (Binarize)

### Threshold (Binarize)

Threshold is a binarization effect that simplifies an image into two tones: **black and white**.\
It splits mid-gray areas by a cutoff (threshold): pixels brighter than the threshold become white, and pixels darker become black.\
This is useful for logo/icon styling, scan-like effects, and high-contrast looks.

***

### `threshold`



**Description**

Binarizes the image using a threshold value (black & white).

In general:

* A **higher** threshold tends to classify **more pixels as dark** (black),
* A **lower** threshold tends to classify **more pixels as bright** (white),

but the perceived result can vary depending on the image’s brightness distribution.



**Format**

```
?threshold={value}
```



**Supported range**

* `0` to `255`



**Examples**

| 요청               | 결과                                                   |
| ---------------- | ---------------------------------------------------- |
| `?threshold=180` | Binarize to black and white with a threshold of 180. |

***

#### Using with other options

* If you want a cleaner and more predictable black/white split, combine it with `grayscale=true`.

```
?grayscale=true&threshold=180
```

***

{% hint style="info" %}
* Threshold works much better for **logos, text, and line drawings** than for photos (portraits/landscapes).
* If you’re not getting the look you want, it’s efficient to tune `threshold` in steps of about **20–30**.
{% endhint %}
