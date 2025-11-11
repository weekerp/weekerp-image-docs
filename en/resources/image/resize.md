---
icon: arrow-down-left-and-arrow-up-right-to-center
---

# Size

**Size Options**

To change the size of an image, use the parameters **`size`**, **`width`**, and **`height`**.\
The `size` parameter allows you to set both dimensions at once for convenience,\
while `width` and `height` control each dimension independently.

***

#### `size`

**Description**\
A single parameter that sets both **width** and **height** simultaneously.\
Internally, it is expanded into `width` and `height` values.

**Format**

```
?size={width}x{height}
```

**Examples**

| Request         | Result                 |
| --------------- | ---------------------- |
| `?size=800x600` | Resized to **800×600** |

If `width` or `height` parameters are also provided,\
the `size` parameter will be **ignored**.

***

#### `width` (`w`)

**Description**\
Specifies the **width** (in pixels) of the output image.\
If no `height` value is given, the original aspect ratio is automatically preserved.

**Examples**

| Request               | Result                                       |
| --------------------- | -------------------------------------------- |
| `?w=800`              | Width 800px, height automatically calculated |
| `?size=600x600&w=400` | Overridden with `width=400`                  |

***

#### `height` (`h`)

**Description**\
Specifies the **height** (in pixels) of the output image.\
If no `width` value is given, the original aspect ratio is automatically preserved.

**Examples**

| Request               | Result                                       |
| --------------------- | -------------------------------------------- |
| `?h=400`              | Height 400px, width automatically calculated |
| `?size=800x600&h=300` | Overridden with `height=300`                 |
