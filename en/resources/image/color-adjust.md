---
description: 'Last updated: January 8, 2026'
icon: palette
---

# Hue

### Hue

Adjusts the overall color tone by rotating the image hue on a color wheel by a specified angle (degrees). It’s useful for creating a consistent mood, correcting color tone, or nudging the image toward a warmer/cooler look.

***

### `hue`

**Description**

Rotates the hue by the specified angle (degrees). Positive (`+`) values rotate the color wheel **clockwise.**

{% hint style="info" %}
Hue operates on a **color wheel**, where colors wrap around in a cycle. Roughly:

* Red → Yellow → Green → Cyan/Teal → Blue → Purple → (back to) Red
{% endhint %}

The `hue` value moves colors along this wheel by **the given number of degrees.**



For example, `hue=30` can be understood as “shift the current colors 30° forward on the color wheel.”\
As a result, green grass may lean more yellowish, and a blue sky may shift toward cyan/teal.



**Format**

```
?hue={degrees}
```



**Supported range**

* `-360` to `360`



**Example**

| Request    | Result                 |
| ---------- | ---------------------- |
| `?hue=30`  | Rotate hue by **30°**  |
| `?hue=-45` | Rotate hue by **-45°** |

***

### Using with other options

* Combining `hue` with `saturation` and `brightness` lets you adjust both the hue shift and overall vividness/brightness.

```
?brightness=1.05&saturation=1.1&hue=10
```

***

{% hint style="info" %}
* Because hue shifts can be quite strong, start by testing small values such as **5–15**.
* For portraits, large hue shifts can make skin tones look unnatural—using `saturation`/`brightness` first is usually safer than rotating hue aggressively.
{% endhint %}
