---
icon: arrows-rotate-reverse
---

# Fit & Position

#### Fit & Position

**Resize Strategy and Crop Alignment**

When specifying image dimensions, you can use the **`fit`** and **`position`** options together to precisely control how the image maintains its aspect ratio and where it is cropped.

***

#### `fit`

**Description**\
Defines how the image is placed within the requested `width` and `height`.\
In other words, it determines _how the image fits inside the target area._

**Format**

```
?fit={type}
```

**Supported Values**

| Value     | Description                                                                | Use Case                        |
| --------- | -------------------------------------------------------------------------- | ------------------------------- |
| `cover`   | Fills the area completely, cropping any overflow.                          | Ideal for thumbnails or banners |
| `contain` | Shrinks the image to fit entirely within the area (allows padding).        | Maintains original aspect ratio |
| `fill`    | Ignores aspect ratio and stretches to fill the exact dimensions.           | May cause distortion            |
| `inside`  | Scales to the largest size that fits _inside_ the target area.             | Prevents upscaling              |
| `outside` | Scales large enough to _cover_ the target area, possibly exceeding bounds. | Prevents downscaling            |

**Examples**

| Request                    | Result                                               |
| -------------------------- | ---------------------------------------------------- |
| `?w=400&h=400&fit=cover`   | Cropped to a perfect square                          |
| `?w=400&h=400&fit=contain` | Fits entirely with padding shown                     |
| `?w=800&h=400&fit=fill`    | Stretched to match dimensions, ignoring aspect ratio |

***

#### `position`

**Description**\
When the image is cropped (e.g., using `fit=cover`),\
this option determines **which part of the image is kept as the anchor point.**

**Format**

```
?position={direction}
```

**Supported Values**

| Value    | Description                 |
| -------- | --------------------------- |
| `centre` | Centers the image (default) |
| `top`    | Anchors to the top          |
| `bottom` | Anchors to the bottom       |
| `left`   | Anchors to the left         |
| `right`  | Anchors to the right        |

**Examples**

| Request                                  | Result                  |
| ---------------------------------------- | ----------------------- |
| `?w=400&h=400&fit=cover&position=top`    | Cropped from the top    |
| `?w=400&h=400&fit=cover&position=bottom` | Cropped from the bottom |

***

#### Using Together

The `fit` and `position` options are most powerful when used together:

```
?w=400&h=400&fit=cover&position=top
```

* `fit=cover`: Fills the square area completely
* `position=top`: Crops from the top

> 💡 **Tip:**
>
> * If `fit` is not specified, the default (usually `cover`) is applied.
> * `position` only has an effect when `fit=cover` is used.

