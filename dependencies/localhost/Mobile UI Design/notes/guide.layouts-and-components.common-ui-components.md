---
id: umnru7c9bnhu0n2xpilgbk7
title: 1 - Common UI Components in Android UI Design
desc: ''
updated: 1769169823403
created: 1766801023687
---

Android UI components are `standardized` `building blocks` **defined by Material Design**. They **ensure** `consistency`, `usability`, `accessibility`, **and** `predictable behavior` across apps and devices.

---

### 1. Core Principle

UI components **should be**:

* `Familiar` — users recognize how they work instantly
* `Consistent` — same behavior across apps
* `Purposeful` — each component solves a specific interaction problem

**Choosing the right component matters more than visual customization**.

---

### 2. Action Components

#### **Buttons**

Used `to trigger` `actions`.

* **Primary (Filled):** Main action on a screen
* **Outlined:** Secondary actions
* **Text buttons:** Low-emphasis actions

Guidelines:

* `One` `primary action` **per screen**
* **Clear** `verb-based` `labels` (“Save”, “Continue”)
* `Visible states`: **default, pressed, disabled**

---

#### **Floating Action Button (FAB)**

Represents the single `most important` `action` on a screen.

* **Circular**, **elevated**, `visually prominent`
* **Appears** `above content`
* `Contextual`: **can change per screen**

Used sparingly—**never more than one at a time**.

---

### 3. Containment Components

#### **Cards**

`Group related` **content and actions**.

* `Elevated` surface
* `Rounded` corners
* Clear `internal spacing`

Used `for lists`, `previews`, `summaries`, **and** `dashboards`.

---

#### **Lists**

Display `collections of items`.

* **Single-line / multi-line**
* `Selectable` **or** `actionable`
* `Support` `scrolling` **and** `lazy loading`

Lists should feel `lightweight` **and** `easy to scan`.

---

### 4. Navigation Components

#### **Top App Bar**

Provides:

* `Screen title`
* `Navigation` (back, menu)
* `Primary actions`

It **anchors the user’s sense of place** within the app.

---

#### **Bottom Navigation Bar**

Used `for switching between` `3–5 top-level destinations`.

* `Persistent` **on compact screens**
* `Icons` **+** `short labels`
* **No deep hierarchy**

---

### 5. Input Components

#### **Text Fields**

`Collect` `user input`.

* Always include `labels`
* Support `helper text` **and** `error text`
* `Clear focus` **and** `validation states`

---

#### **Selection Controls**

* **Checkbox:** `Multiple selections`
* **Radio button:** `One choice` from many
* **Switch:** `On/off` **state**

Each control **communicates state clearly and immediately**.

---

### 6. Feedback Components

#### **Snackbar**

* `Temporary message` **at the** `bottom`
* `Non-blocking`
* `Optional` `action` (e.g., “Undo”)

Used `for low-priority` `feedback`.

---

#### **Dialogs**

* `Block interaction` `temporarily`
* Used `for confirmations` `or critical alerts`
* **Clear** `primary and secondary` `actions`

---

### 7. Disclosure Components

#### **Bottom Sheets**

Reveal `secondary` `content or actions`.

* `Slide up` `from bottom`
* `Dismissible` **via gesture**
* Can be `modal` **or** `persistent`

**Preferred over dialogs for non-critical tasks**.

---

#### **Chips**

`Compact elements` **representing**:

* `Filters`
* `Tags`
* `Actions`

They are `lightweight`, `interactive`, **and** `contextual`.

---

### 8. Visual Indicators

#### **Progress Indicators**

* **Linear:** `Page-level loading`
* **Circular:** `Ongoing` `or unknown duration`

Should `reassure users` **that the** `system is working`.

---

### 9. Accessibility Considerations

* `Touch targets` `≥ 48×48 dp`
* `High contrast` **and** `clear states`
* `Screen-reader-friendly` `labels`
* `Consistent` `placement` **and** `behavior`

`Material components` **are** `accessibility-aware` **by default**.

---

### 10. Key Takeaways

| Component Type      | Purpose                  |
| ------------------- | ------------------------ |
| **Buttons & FAB**       | `Trigger actions`          |
| **Cards & Lists**       | `Organize content`         |
| **App Bars & Nav**      | `Orientation` **and** `movement` |
| **Inputs & Selectors**  | `Collect data`             |
| **Snackbars & Dialogs** | `Feedback` **and** `alerts`      |
| **Bottom Sheets**       | `Progressive disclosure`   |

---

### Core Idea

**Android UI components are not just visuals** —
they are `behavioral contracts` **between the app and the user**.
Using them correctly `makes your app` **feel** `intuitive`, `reliable`, **and** `native`.