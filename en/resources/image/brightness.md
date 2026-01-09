---
description: 'Last updated: January 8, 2026'
icon: brightness-low
---

# Brightness

### Brightness

Adjusts the overall brightness of an image to make it look lighter or darker.\
It’s commonly used to fine-tune exposure for product photos, banners, and thumbnails.

***

### `brightness`



**Description**

Sets the brightness multiplier. `1.0` leaves the image unchanged. Values **greater than 1.0** make the image brighter, and values **less than 1.0** make it darker.



**Format**

```
?brightness={factor}
```



**Supported range**

* `0.5` to `2.0`



**Examples**

| 요청                 | 결과                               |
| ------------------ | -------------------------------- |
| `?brightness=1.15` | Slightly **increase** brightness |
| `?brightness=0.85` | Slightly **decrease** brightness |

***

#### Using with other options

* You can combine brightness with other tone controls (e.g., `hue`, `saturation`) for more precise adjustments.

```
?brightness=1.05&saturation=1.15
```

***

{% hint style="info" %}
Small changes (e.g., **1.05–1.15**) are often enough to make a noticeable difference.\
Very high or low values may blow out highlights (too bright) or crush/lose detail, so it’s best to adjust gradually.
{% endhint %}
