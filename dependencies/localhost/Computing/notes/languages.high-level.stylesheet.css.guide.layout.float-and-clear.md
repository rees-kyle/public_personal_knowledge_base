---
id: kswsfj68xjplnxqeb96nyo9
title: Float and Clear Properties
desc: ''
updated: 1706664655777
created: 1706386448473
---

The `float` **and** `clear` **properties** in CSS are **often** `used together` **to** `create` `layouts`, **especially in** `older` `codebases`. `However`, **with** the advent of `Flexbox` **and** `CSS Grid`, the usage of `float` **has** `diminished`. `Nevertheless`, it's **still** `useful` **to** `understand` how these properties work.

### `float` Property:

The float property is **used to** `push` **an** `element` **to** `one side` **of its** `containing element`, **allowing** `content` **to** `flow around` **it**. **Common values for float** are `left` **and** `right`.

Example:

```css
.float-left {
    float: left;
}

.float-right {
    float: right;
}
```

### `clear` Property:

The clear property is **used to** `specify` **which** `side` **of an** `element` `should not be` `adjacent` **to a** `floating element`. It's **often** `applied to` **an** `element` **that** `follows` **a** `floating element` **to** `prevent it` **from** `wrapping around` **the** `floated element`.



<!-- start of 'adjacent' section -->
<details>
    <summary>Definition: adjacent</summary>

#
"Adjacent" refers to `objects` **or** `elements` that are `positioned` `next` to **or** `close to` `each other`, typically sharing a common boundary or side.

---
</details>
<!-- end of 'adjacent' section -->



#
Example:

```css
.clearfix:after {
    content: "";
    display: table;
    clear: both;
}
```

Here, the `clearfix` **class** is **often** `added` **to a** `container` **that** `contains` `floated elements`. The `:after` **pseudo-element** `generates` **an** `empty block element` **that** `forces` **the** `container` **to** `clear` **its** `floated children`.

### Example of Float and Clear in Layout:

```css
.float-left {
    float: left;
    margin-right: 20px; /* Optional margin to create space between floated elements */
}

.float-right {
    float: right;
    margin-left: 20px;
}

.clearfix:after {
    content: "";
    display: table;
    clear: both;
}

/* Usage in HTML: */
<div class="float-left">Left Floated Content</div>
<div class="float-right">Right Floated Content</div>
<div class="clearfix"></div> <!-- Add clearfix to clear floats -->
```

Keep in mind that **using** `float` for layout purposes **has** some `drawbacks` **and** `limitations`, and it's generally `recommended` **to use** `modern` `layout techniques` **like** `Flexbox` **or** `Grid` **for** `more complex` `layouts`. `Floats` **are** `still used` **for** `wrapping text around` `images`, `but` for general page layout, `other options` are **often** `preferred`.