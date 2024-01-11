---
id: ii51jid28jcepimae4jcfxe
title: 008 - Tables
desc: ''
updated: 1704991729682
created: 1704246578014
---

Tables are **used to** `organize` **and** `display` `data` **in** `rows` **and** `columns`.


## Example 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Table Example</title>
</head>
<body>

<table border="1">
    <thead>
        <tr>
            <th>Header 1</th>
            <th>Header 2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Row 1, Cell 1</td>
            <td>Row 1, Cell 2</td>
        </tr>
        <tr>
            <td>Row 2, Cell 1</td>
            <td>Row 2, Cell 2</td>
        </tr>
    </tbody>
</table>

</body>
</html>
```


## Elements

| Element    | Description                              |
|------------|------------------------------------------|
| `<table>`  | **Defines** the `beginning` **of a** `table`.    |
| `<tr>`     | **Defines** a `table row`.                   |
| `<th>`     | **Defines** a `table header` **cell**.             |
| `<td>`     | **Defines** a `table data` **cell**.               |
| `<thead>`  | **Groups** the `header content` in a table.    |
| `<tbody>`  | **Groups** the `body content` in a table.      |

#
The `border="1"` **attribute on** the `<table>` **element** `adds` **a** `border` to the table for better visualization, **but** it's `not required`. You **can** `customize` the `appearance` **of** the `table` **using** `CSS` for styling.

You **can use** `additional` `attributes` **and** `elements` **for more** `complex tables`.