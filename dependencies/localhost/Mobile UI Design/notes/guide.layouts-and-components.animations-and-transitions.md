---
id: ah5dyumohm5kcj6hksjii4f
title: 5 - Animations and Transitions (motion design) in Android UI
desc: ''
updated: 1769709311357
created: 1769707691204
---

Motion design in Android UI uses animation `to communicate change`, `provide feedback`, **and** `preserve user context`. It is **not decorative**; it exists `to help users understand` `what just happened` `and what will happen` **next**.

---

### 1. Core Principle

**Motion should** `explain`, `not entertain`.
`Every animation` `must answer` **at least one** `question`:

* `What changed?`
* `Where did it come from?`
* `Where did it go?`
* `What action caused this?`

**If motion doesn’t add clarity, it should not exist**.

---

### 2. Animations vs Transitions

* **Animations** `affect` `a single element` (e.g., a **button press ripple**, **loading spinner**).
* **Transitions** `describe movement` `between UI states` **or** `screens` (e.g., **navigating forward**, **opening a modal**).

`Both` **work together** `to create continuity`.

---

### 3. Types of Motion in Android UI

#### **Feedback Motion**

* `Confirms` `user input` (**tap, drag, swipe**)
* **Examples**: `ripple effects`, `pressed states`, `micro-shifts`
* **Must be** `instant` **and** `subtle`

---

#### **State Change Motion**

* `Shows changes` `in UI state`
* **Examples**: `expanding cards`, `toggles switching`, `loading to success`
* **Helps users** `understand` `cause` **and** `effect`

---

#### **Navigation Motion**

* `Connects` `screens` **or** `sections`
* `Forward navigation` `feels directional`
* `Back navigation` `reverses` `the motion`
* **Maintains** `spatial awareness`

---

### 4. Material Motion Principles

Android’s motion system follows consistent rules:

* `Continuity`: **Elements feel like they exist in a shared space**
* `Hierarchy`: **Important elements move more noticeably**
* `Timing`: **Short and responsive (typically under 300ms)**
* `Easing`: **Natural acceleration and deceleration (ease-in-out)**

Motion **should feel** `physical` **and** `intentional`.

---

### 5. Shared Element Transitions

Shared elements `visually` `connect two screens` `by animating` `a common component` **between them**.

Purpose:

* `Preserve context`
* `Reduce` `cognitive load`
* `Reinforce relationships` **between content**

**They make** `navigation` **feel** `fluid` **instead of abrupt**.

---

### 6. Motion and Performance

* Motion **must remain** `smooth` (**no frame drops**)
* `Avoid animating` `layout-heavy properties` `during scroll`
* **Prefer** `transform-based motion` (**position, scale, opacity**)
* `Reduce motion complexity` `in lists`

`Performance issues` `break trust` **instantly**.

---

### 7. Accessibility Considerations

* `Respect system settings` `for reduced motion`
* `Avoid` `fast, looping, or distracting` `animations`
* `Never rely on motion alone` `to convey information`
* `Ensure screen readers` `announce state changes`

**Motion should** `support`, `not exclude`.

---

### 8. When *Not* to Animate

* `For` **purely** `decorative effects`
* `When it delays` `task completion`
* `When multiple animations` `compete for attention`
* `For critical error states` `that require immediate clarity`

`Stillness` `is sometimes better` **than motion**.

---

### 9. Key Takeaways

| Aspect        | Guideline                  |
| ------------- | -------------------------- |
| **Purpose**       | `Explain` `change`             |
| **Duration**      | `Fast` **and** `subtle`            |
| **Direction**     | `Consistent` `with navigation` |
| **Performance**   | **Always** `smooth`              |
| **Accessibility** | `Motion` **is** `optional`         |

---

### Core Idea

Good motion **makes** `interfaces` `feel alive` `but calm`—`guiding users through change` `without demanding attention`.