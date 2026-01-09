---
description: 'Last updated: January 8, 2026'
icon: signal
---

# Saturation

### Saturation

Adjusts the intensity of colors to make the image look more vivid or more muted.\
It’s commonly used to keep color tone consistent in product photos, food photos, and thumbnails.

***

### `saturation`



**Description**

Sets the saturation multiplier.\
`1.0` leaves the image unchanged. Values **greater than 1.0** increase saturation, and values **less than 1.0** decrease saturation.



**Format**

```
?saturation={factor}
```



**Supported range**

* `0.0` to `3.0` &#x20;



**Example**

| Request            | Result                       |
| ------------------ | ---------------------------- |
| `?saturation=1.25` | Slightly increase saturation |
| `?saturation=0.85` | Slightly decrease saturation |

***

### Using with other options

* You can combine saturation with other tone controls (e.g., `brightness`, `hue`) for finer adjustments.

```
?brightness=1.05&saturation=1.15
```

***

{% hint style="info" %}
* Pushing saturation too high can make skin tones look unnatural or cause color bleeding, so it’s best to adjust gradually—typically around **1.05–1.2**.
* Lowering saturation can create a more subdued mood, and unlike `grayscale`, it still preserves color information.
{% endhint %}

