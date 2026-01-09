---
description: 'Last updated: January 8, 2026'
icon: sparkles
---

# Sharpen

### Sharpen

Sharpen increases perceived sharpness by enhancing edges (high-frequency details).\
It’s useful for correcting images that look soft after resizing, or making text/logos look crisper.

***

### `sharpen`

**Description**

Sets the sharpening strength (`sigma`).\
Higher values produce a stronger sharpening effect, but depending on the image, it may also increase noise/grain.



**Format**

```
?sharpen={sigma}
```



**Supported range**

* `0.3 ~ 20`&#x20;



**Examples**

| 요청             | 결과                                                 |
| -------------- | -------------------------------------------------- |
| `?sharpen=1.2` | Apply **light sharpening**                         |
| `?sharpen=3`   | Apply **stronger sharpening** (may increase noise) |

***

#### Using with other options

* Applying `sharpen` after downscaling with `width` often helps reduce the slight softness introduced during resizing.

```
?width=800&sharpen=1.0
```

***

{% hint style="info" %}
**Recommended starting points**

* A good starting range is **1.0–1.5**.
* For **logos/text**, you’ll often notice a clear difference around **\~2.0**.
* For photos with lots of smooth areas (skin, gradients), higher sharpening can look harsh or noisy—start low and increase gradually.
{% endhint %}
