---
description: 'Last updated: January 8, 2026'
icon: reflect-horizontal
---

# Flip & Flop

### Flip

You can flip an image vertically or horizontally. This is useful for mirror effects, selfie orientation fixes, and design variations.



#### `flip`

**Description**

Flips the image vertically (**top ↔ bottom**).



**Format**

```
?flip=true
```



**Supported values**

* `true | false`
* Applied only when `true` (not set or `false` → no effect)



**Examples**

| Request      | Result                       |
| ------------ | ---------------------------- |
| `?flip=true` | Vertical flip (top ↔ bottom) |



***

### Flop

You can flip an image horizontally (**left ↔ right**).

### `flop`



**Description**

Flips the image horizontally (**left ↔ right**).



**Format**

`?flop=true`



**Supported values**

* `true | false`
* Applied only when `true` (not set or `false` → no effect)



**Examples**

| Request      | Result                         |
| ------------ | ------------------------------ |
| `?flop=true` | Horizontal flip (left ↔ right) |

#### Using together

* `?flip=true&flop=true`
  * Applies both vertical and horizontal flips. This can produce an effect similar to a **180° rotation** (depending on the content).

{% hint style="info" %}
If your selfie looks mirrored left-to-right, `flop=true` fixes it.\
For thumbnail styling (mirror effects), `flip` and `flop` are handy options.
{% endhint %}
