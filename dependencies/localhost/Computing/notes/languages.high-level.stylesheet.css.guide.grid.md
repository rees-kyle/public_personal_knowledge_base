---
id: i4qb573qzyc5qdkl9ijk8i9
title: 8 - Grid
desc: ''
updated: 1711444000850
created: 1711443057248
---

CSS Grid is **a powerful layout system** that allows web developers to **create complex web designs with ease**. It **provides a** `two-dimensional` `grid-based` `layout system`, making it perfect for creating both `simple` **and** `intricate designs`. Here's an overview of some key concepts and properties in CSS Grid:

### Introduction to CSS Grid:

CSS Grid introduces a new way of creating layouts on the web. It **allows you to** `divide` **a** `web page` **into** `rows` **and** `columns`, forming a grid-like structure. `Items` **can then be** `placed` anywhere `within` **this** `grid`, **giving you** `precise control` **over the layout**.

### Properties:

#### 1. `grid-template-columns` and `grid-template-rows`:

These properties `define` **the** `number` **and** `size` **of** `columns` **and** `rows` in the grid, respectively. You `can specify` the size of each column and row `individually`, using `values` **like** `pixels`, `percentages`, **or the** `fr` **unit** (**which** `represents` **a** `fraction` **of the** `available space`).

```css
.grid-container {
  display: grid;
  grid-template-columns: 100px 200px 1fr; /* Three columns: 100px, 200px, and the rest of the available space */
  grid-template-rows: 50px auto; /* Two rows: 50px tall, and the rest of the available space */
}
```

#### 2. `grid-gap`:

This property `sets` **the** `gap` `between` `grid columns` **and** `rows`. You `can specify` `separate values` for row and column gaps, **or a** `single value` **for both**.

```css
.grid-container {
  display: grid;
  grid-gap: 10px; /* 10px gap between rows and columns */
}
```

#### 3. `grid-column` and `grid-row`:

These properties `determine` **the** `starting` **and** `ending positions` **of** `grid items` within the grid. They **allow you to** `place items` **in** `specific` `cells` **or** `spans` **of cells**.



<!-- start of 'span' section -->
<details>
    <summary>Definition: span</summary>

#
In the context of CSS Grid, a "span" **refers to the** `number` **of** `grid tracks` (`columns` **or** `rows`) **that an** `item occupies` **within the grid**.

---
</details>
<!-- end of 'span' section -->



```css
.grid-item {
  grid-column: 2 / 4; /* Item starts at the second column and ends at the fourth column */
  grid-row: 1; /* Item occupies the first row */
}
```

### Conclusion:

CSS Grid **provides a** `flexible` **and** `powerful way` **to** `create layouts` on the web. **By using properties like** `grid-template-columns`, `grid-template-rows`, `grid-gap`, `grid-column`, **and** `grid-row`, **you can create complex layouts that** `adapt` **to** `different` `screen sizes` **and** `content requirements`. With practice, CSS Grid can become **an** `essential tool` in your web development toolkit.