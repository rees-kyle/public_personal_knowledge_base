---
id: nm1vv8uzmhdpt9yk9qyh02t
title: 1 - Exporting Assets for Android
desc: ''
updated: 1777177265886
created: 1776730673968
---

Assets are `visual resources` (**icons, images, backgrounds**) used in an app. **Proper exporting ensures they appear** `sharp`, `scalable`, **and** `efficient` **across** `different` **screen** `sizes` **and densities**.

---

## 1. Core Principle

Assets **must be**:

* `Resolution-independent` where possible
* `Optimized` `for performance`
* `Adaptable` `across densities` (**mdpi → xxxhdpi**)

The **goal is to** `maintain visual quality` `without increasing` **app** `size or rendering cost`.

---

## 2. SVG (Vector Drawables)

SVG (`Scalable Vector Graphics`) **are** `resolution-independent images` `based on paths`, **not pixels**. In **Android**, these are used as **Vector Drawables**.

**Characteristics:**

* `Infinitely scalable` `without quality loss`
* `Small file size` **for simple graphics**
* Ideal `for icons` **and** `simple illustrations`

**Use when:**

* The **asset is** `geometric` (**icons, shapes, UI elements**)
* **You need** `sharp rendering` `on all screen densities`

**Limitations:**

* Not suitable for `complex images` (**photos, textures**)
* Some `advanced SVG features` `may not be supported`

---

## 3. PNG (Raster Images)

**PNG is a** `pixel-based` `image format`.

**Characteristics:**

* `High-quality`, `lossless compression`
* `Supports transparency`
* `Fixed resolution`

**Use when:**

* The `image is complex` (**photos, detailed graphics**)
* `Visual fidelity` `is critical`

**Density Handling:**
**PNG assets** `must be exported` `in multiple sizes`:

* `mdpi` (**1×**)
* `hdpi` (**1.5×**)
* `xhdpi` (**2×**)
* `xxhdpi` (**3×**)
* `xxxhdpi` (**4×**)

`Android` `automatically selects` **the** `correct version` **based on device density**.

---

## 4. 9-Patch Images

9-patch (**NinePatch**) images are **special PNG files that** `define` `stretchable areas`.

**Characteristics:**

* Allow parts of an image to `stretch while preserving` `corners` **and** `edges`
* Include `metadata` (**via 1-pixel borders**) `to define` `stretch regions` **and** `content padding`

**Use when:**

* `Creating` `scalable backgrounds` (**buttons, cards, bubbles**)
* `You need` `consistent borders` **regardless of size**

**Advantage:**
`Maintains visual integrity` **while adapting** `to different content sizes`.

---

## 5. Choosing the Right Format

| Format           | Best For                | Key Benefit                  |
| ---------------- | ----------------------- | ---------------------------- |
| **SVG / Vector** | `Icons`, `simple graphics`  | `Scales perfectly`, `small size` |
| **PNG**          | `Photos`, `complex visuals` | `High fidelity`                |
| **9-patch PNG**  | `Stretchable` `UI elements` | `Flexible resizing`            |

---

## 6. Optimization Guidelines

* `Avoid exporting` **unnecessarily** `large images`
* `Use vectors` **whenever possible**
* `Compress PNGs` **to reduce file size**
* `Remove` `unused assets`
* Keep `asset naming` `consistent` **and** `meaningful`

**Efficient assets improve both performance and maintainability.**

---

## 7. Design Considerations

* Ensure assets work in both `light and dark` `themes`
* `Maintain` proper `contrast` **and** `visibility`
* `Align assets` `to pixel grids` **to avoid blurriness**
* `Test across` `different screen densities`

---

## 8. Key Takeaways

| Principle            | Purpose                    |
| -------------------- | -------------------------- |
| **Vector first**         | `Scalability` **and** `efficiency` |
| **Multiple densities**   | `Visual consistency`         |
| **9-patch usage**        | `Flexible` `UI elements`       |
| **Optimization**         | `Better performance`         |
| **Proper format choice** | `Correct` `use of resources`   |

---

## Core Idea

**The right** `asset format` `ensures` **your** `UI` **stays** `sharp`, `flexible`, **and** `efficient`—**no matter the screen size or device**.