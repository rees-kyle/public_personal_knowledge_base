---
id: 6e6scg060ir5jrsjg0b3fin
title: 2 - RecyclerView / ListView Design Patterns (Android UI)
desc: ''
updated: 1769258605841
created: 1769255678778
---

Scrollable lists are one of the most common UI structures in Android apps—used `for feeds`, `messages`, `settings`, `catalogs`, **and** `dashboards`. Android list design **focuses on** `performance`, `clarity`, **and** `predictable interaction`.

---

### 1. Core Principle

**Lists should be**:

* `Scannable` at a glance
* `Efficient` **to scroll through**
* `Consistent` **in structure and behavior**

`RecyclerView` is designed `to handle` `large or dynamic data sets` **while keeping scrolling smooth and interactions responsive**.

---

### 2. List Structures

#### **Vertical Lists**

* Items stacked in a `single column`
* **Most common** pattern
* Best `for text-heavy or mixed` `content`

**Typical uses**: `messages`, `activity feeds`, `settings`

---

#### **Grids**

* `Items` arranged `in rows and columns`
* **Works** `best when` `items` **are** `visually uniform`

**Typical uses**: `photo galleries`, `product catalogs`, `media thumbnails`

---

### 3. Common List Item Patterns

* **Single-line items:** `One primary` **piece of** `information`
* **Two-line items:** `Primary content with` **supporting** `secondary text`
* **Three-line items:** `Primary`, `secondary`, **and** `metadata` **content**
* **Card-based items:** `Content grouped` `in elevated containers` **for emphasis**

`Choose the simplest pattern` `that communicates` `the necessary information`.

---

### 4. List Item Hierarchy

Every list item **should have a clear internal hierarchy**:

1. **Primary content** – the `main reason` **the item exists**
2. **Secondary content** – `supporting context`
3. **Tertiary actions** – `optional` `icons or menus`

This hierarchy **allows users** `to scan lists quickly` `without cognitive overload`.

---

### 5. Interaction Patterns

* **Tap:** `Opens or activates` **the** `primary action`
* **Long-press:** `Enables` `selection mode` **or** `contextual actions`
* **Swipe:** `Triggers` `quick actions` **such as** `delete` **or** `archive`

`Swipe actions` **should be** `reversible` **and** `accompanied by` `feedback` (**e.g., undo**).

---

### 6. Selection Patterns

* **Single selection:** `Navigates to` **a** `detail view`
* **Multi-selection:** `Enables` `batch actions` **via a** `contextual action bar`
* **Persistent selection:** Used in `preference or filter` `lists`

**Selected items must be visually distinct** from unselected ones.

---

### 7. States in Lists

Lists must clearly **represent system states**:

* **Loading state:** `Shows` `progress` **or** `placeholder content`
* **Empty state:** `Explains` **why the** `list is empty` `and what to do next`
* **Error state:** `Communicates failure` **and** `offers recovery`

**Never leave a list area blank without explanation**.

---

### 8. Performance and Usability Considerations

* **Maintain** `consistent` `spacing and alignment` across items
* `Avoid` `excessive nesting` **or** `complex layouts`
* Ensure `touch targets` are **at least** `48×48 dp`
* `Avoid animations` `that disrupt scrolling performance`

**Design should respect RecyclerView’s recycling behavior by keeping item layouts lightweight**.

---

### 9. Key Takeaways

| Pattern        | Purpose                 |
| -------------- | ----------------------- |
| **Vertical list**  | `General content` display |
| **Grid**           | `Visual content`          |
| **Cards**          | `Rich or grouped` `content` |
| **Swipe actions**  | `Quick, reversible` `tasks` |
| **Selection mode** | `Batch operations`        |

---

### Core Idea

`A well-designed list` `disappears into the background`, letting `users focus entirely on content and actions`—**not on how the list works**.