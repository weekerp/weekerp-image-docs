---
description: 'Last updated: January 8, 2026'
icon: arrows-to-dot
---

# Gamma (Midtones)



### Gamma

Gamma adjusts the image’s tonal distribution (midtones), changing how it appears on screen.\
Unlike simply making an image “brighter” or “darker,” gamma mainly shifts the **midtones**, so it’s commonly used for photo and product-shot correction.

***

### `gamma`



**Description**\
Sets the gamma correction value. A common range in practice is around **1.8–2.2**.



**Format**

```
?gamma={value}
```



**Supported values**

* Range: `1.0` to `3.0` &#x20;



**Examples**

| Request      | Result                   |
| ------------ | ------------------------ |
| `?gamma=2.2` | Midtone tonal correction |

***

### Using with other options

`gamma` works well alongside optimization options such as `format`, `quality`, and `width`.

```
?width=1200&format=webp&quality=80&gamma=2.0
```

***

{% hint style="info" %}
Because gamma primarily affects **midtones** rather than overall brightness, it’s especially useful for natural-looking detail adjustments in product photos.\
It’s safest to tune it in small steps—e.g., **1.8 → 2.0 → 2.2**.
{% endhint %}
