---
id: g870g7waa6tl0x8o0eentws
title: 1 - Material Design Fundamentals
desc: ''
updated: 1762468663247
created: 1762200823432
---

### 1.1 What Material Design Is

`Material Design` is **Google’s** `design system`, **used across** `Android and` **other** `Google platforms`.
It provides **a unified** `visual language` that **makes apps feel** `coherent` **and** `intuitive`.
Think of it as **the “grammar and syntax” of Android interface design**.

It’s **based on the idea that** `digital elements` `behave like` `physical materials` — **they have** `depth`, `texture`, `and rules` **about how they move and interact**.



<!-- start of 'unified' section -->
<details>
    <summary>Definition: unified</summary>

#
Unified **means** `joined together` `or combined into a single whole`.

---
</details>
<!-- end of 'unified' section -->



#### The three core principles:

1. **Material is metaphor**
   `Visual elements act like` `real materials` — **they can** `cast shadows`, `move`, `stack`, **and** `overlap`.
   This gives users **a sense of** `physical` `space and hierarchy`.

2. **Bold, graphic, intentional**
   Android design **emphasizes** `clarity and hierarchy` **through deliberate** `use of` `color`, `typography`, **and** `imagery`. **Nothing is random**.

3. **Motion provides meaning**
   `Transitions and animations` **aren’t decorative**; they `explain` `what’s happening` — **like which element is changing or where a new view came from**.



<!-- start of 'hierarchy' section -->
<details>
    <summary>Definition: hierarchy</summary>

#
Hierarchy **means** `a system of` `ranking or organizing` `people or things` `by levels of` `importance or authority`.

---
</details>
<!-- end of 'hierarchy' section -->



<!-- start of 'typography' section -->
<details>
    <summary>Definition: typography</summary>

#
Typography **means** `the art and technique of` `arranging text` — **including the choice of** `fonts`, `sizes`, `spacing`, `and layout` — **to make written language** `look good` **and** `easy to read`.

---
</details>
<!-- end of 'typography' section -->



<!-- start of 'imagery' section -->
<details>
    <summary>Definition: imagery</summary>

#
Imagery **means** `descriptive language` `that creates pictures in the reader’s mind` `by appealing to the senses` (**sight**, **sound**, **smell**, **taste**, **touch**).

---
</details>
<!-- end of 'imagery' section -->



<!-- start of 'animation' section -->
<details>
    <summary>Definition: animation</summary>

#
Animation **means** `the process of` `making drawings`, `images`, `or objects` `appear to move`.

---
</details>
<!-- end of 'animation' section -->



---

### 1.2 The Material 3 (Material You) Evolution

**Material 3, also known as *Material You***, is the `latest generation` **of Material Design**.
Its **central idea is** `personalization`: the `user’s device theme` (wallpaper, system colors, etc.) `can influence` `app color palettes` **dynamically**.

Material 3 **expands on the older system by**:

* **Introducing** `dynamic color extraction`, **where** `UI colors` `adapt to` **the** `user’s` chosen `wallpaper`.
* `Simplifying` `component design` — **flatter**, **softer**, **more adaptable**.
* `Emphasizing` `accessibility and adaptability` `to different screen sizes` (**phones**, **foldables**, **tablets**).

This **means that while Material Design** `provides structure`, **it now also** `allows for individual` `expression and adaptability`.

---

### 1.3 Color System

The color system in Material Design **defines a** `semantic palette` — `each color` **has a** `specific role` **rather than being chosen arbitrarily**.



<!-- start of 'semantic' section -->
<details>
    <summary>Definition: semantic</summary>

#
Semantic **means** `related to` `meaning`, **especially** the meaning of `words`, `symbols`, **or** `signs`.

---
</details>
<!-- end of 'semantic' section -->



<!-- start of 'arbitrarily' section -->
<details>
    <summary>Definition: arbitrarily</summary>

#
Arbitrarily **means** `done without` `a clear` `reason`, `plan`, `or system`; **based on** `random choice` **or** `personal whim`.

---
</details>
<!-- end of 'arbitrarily' section -->



<!-- start of 'whim' section -->
<details>
    <summary>Definition: whim</summary>

#
A whim is `a sudden`, `impulsive` `idea or desire` — **something you want to do** `without` `planning or reason`.

---
</details>
<!-- end of 'whim' section -->



#### The main color roles:

* **Primary** – The `main` `brand color`. Used **for** `prominent elements` **like** `top app bars`, `active buttons`, **and** `highlights`.
* **Secondary** – A `supporting` `accent color`. It `complements the primary` **and** `provides variation`.
* **Tertiary** – An `optional additional` `accent color`, often **used** `for expressive` `touches or illustrations`.
* **Surface** – `Backgrounds of components` **such as** `cards`, `sheets`, **or** `dialogs`.
* **Background** – The `base canvas color` `behind all content`.
* **Error** – **Colors used for** `error` `states and alerts`.



<!-- start of 'accent' section -->
<details>
    <summary>Definition: accent (design)</summary>

#
Accent **means** `something that` `stands out` `or draws attention`.

---
</details>
<!-- end of 'accent' section -->



<!-- start of 'tertiary' section -->
<details>
    <summary>Definition: tertiary</summary>

#
Tertiary **means** `third` `in order or level`.

---
</details>
<!-- end of 'tertiary' section -->



<!-- start of 'expressive' section -->
<details>
    <summary>Definition: expressive</summary>

#
Expressive **means** `showing or conveying` `emotions, thoughts, or ideas` `clearly`.

---
</details>
<!-- end of 'expressive' section -->



<!-- start of 'illustrations' section -->
<details>
    <summary>Definition: illustrations</summary>

#
Illustrations **are** `pictures or images` `created` `to explain, decorate, or clarify` `something`.

---
</details>
<!-- end of 'illustrations' section -->



<!-- start of 'state' section -->
<details>
    <summary>Definition: state</summary>

#
State **refers to** `how something` `exists or functions` `at a particular moment`.

---
</details>
<!-- end of 'state' section -->



<!-- start of 'alert' section -->
<details>
    <summary>Definition: alert (UI/UX)</summary>

#
Alert **means** `a warning or message` `that tells you to` `pay attention`.

---
</details>
<!-- end of 'alert' section -->



Each color role also has a corresponding `**"on-"** color` (e.g., *on-primary*, *on-surface*), which `defines the color of text or icons` `that appear on top of it`.

This structured approach **ensures** `readability and accessibility` `by maintaining` **proper** `contrast ratios` **automatically**.



<!-- start of 'contrast ratios' section -->
<details>
    <summary>Definition: contrast ratios</summary>

#
Contrast ratio **is** `the difference in brightness` `between the lightest and darkest parts of` `a screen or design`.

---
</details>
<!-- end of 'contrast ratios' section -->



---

### 1.4 Typography System

Typography in Android design is `structured around` `scale and hierarchy`.
**Rather than manually selecting font sizes**, `Material defines` `a type scale` **that covers every possible use case**.

#### The main categories:

* **Display** – `Very large text` **used** `for hero elements`.
* **Headline** – `Section` **and** `screen titles`.
* **Title** – `Subheadings` **and** `contextual headers`.
* **Body** – `Standard` `text content`.
* **Label** – `Buttons`, `captions`, **and** `smaller text`.



<!-- start of 'hero element' section -->
<details>
    <summary>Definition: hero element or hero section (design)</summary>

#
In design, a hero element or hero section **is** `the main, prominent` `part of` `a webpage or app screen` `that grabs attention`.

---
</details>
<!-- end of 'hero element' section -->



<!-- start of 'section' section -->
<details>
    <summary>Definition: section</summary>

#
Section **means** `a distinct` `part or division of` `something`.

---
</details>
<!-- end of 'section' section -->



<!-- start of 'contextual' section -->
<details>
    <summary>Definition: contextual</summary>

#
Contextual **means** `related to` `the situation, environment, or context` `in which something` `occurs`.

---
</details>
<!-- end of 'contextual' section -->



<!-- start of 'label' section -->
<details>
    <summary>Definition: label</summary>

#
A label **is** `a name or tag` `that identifies or describes` `something`.

---
</details>
<!-- end of 'label' section -->



<!-- start of 'caption' section -->
<details>
    <summary>Definition: caption</summary>

#
A caption **is** `a short piece of text` `that explains or describes` `an image, video, or illustration`.

---
</details>
<!-- end of 'caption' section -->



**Each of these categories has** `multiple levels` (e.g., *headline large, headline small*) `with standardized` `font weights and sizes`.

This **hierarchy ensures**:

* `Consistent` `rhythm and proportion` **across screens**.
* `Clear` `visual differentiation between` **types of** `information`.
* `Accessibility through legibility` `and predictable patterns`.



<!-- start of 'consistent' section -->
<details>
    <summary>Definition: consistent</summary>

#
Consistent **means** `always` `behaving, happening, or looking` `the same way` `over time`.

---
</details>
<!-- end of 'consistent' section -->



<!-- start of 'rhythm' section -->
<details>
    <summary>Definition: rhythm</summary>

#
Rhythm **means** `a regular, repeated` `pattern of` `movement, sound, or design`.

---
</details>
<!-- end of 'rhythm' section -->



<!-- start of 'proportion' section -->
<details>
    <summary>Definition: proportion</summary>

#
Proportion **means** `the relationship in` `size, amount, or degree` `between` `parts of a whole`.

---
</details>
<!-- end of 'proportion' section -->



<!-- start of 'differentiation' section -->
<details>
    <summary>Definition: differentiation</summary>

#
Differentiation **means** `the act of` `making something` `different or distinct from` `others`.

---
</details>
<!-- end of 'differentiation' section -->



<!-- start of 'legibility' section -->
<details>
    <summary>Definition: legibility</summary>

#
Legibility **means** `how easy it is` `to read` `letters or text`.

---
</details>
<!-- end of 'legibility' section -->



<!-- start of 'predictable' section -->
<details>
    <summary>Definition: predictable</summary>

#
Predictable **means** `something` `that can be expected or guessed` `because it follows a usual` `pattern or behavior`.

---
</details>
<!-- end of 'predictable' section -->



In `Material 3`, the `default typeface is` `Roboto or Noto`, **but** `custom fonts are allowed` **as long as hierarchy and readability remain consistent**.

---

### 1.5 Shape, Elevation, and Depth

**Material Design uses** `depth` **as a metaphor** `for structure`.
`Each UI element` **exists on** `a different layer` in a three-dimensional “space,” and `its elevation` `determines` **its** `shadow and importance`.

#### Elevation (measured in dp)

* A `surface` (like the **background**) has `0 dp` (**density-independent pixel**) `elevation`.
* A `card` might have `1–4 dp`.
* A `floating action button` (**FAB**) might have `6 dp or more`.
* A `dialog or modal sheet` appears at a **much higher elevation**, **such as** `24 dp`.

**This consistent use of elevation helps users instinctively understand which elements are interactive or currently in focus**.

`Shape` `complements elevation` — it defines the character of components (**rounded corners, cut edges, etc.**). **Material 3 uses a** `corner radius system` (**small, medium, large**) to create visual coherence across elements.

---

### 1.6 Motion and Transitions

Motion in Android UI design has a purpose: to maintain continuity, indicate hierarchy, and provide feedback.

It follows a few **key principles**:

* `Ease-in-out curves` create natural acceleration and deceleration.
* `Shared element transitions` visually connect elements between screens.
* `Transformations` (**expanding, fading, translating**) communicate the relationship between actions.

`Animations` are short and subtle — typically `under 300ms` — and they never occur without reason. Their **goal is to** `explain`, `not` **to** `distract`.

For example, when a floating action button morphs into a form sheet, the animation clarifies that these two UI states are related.

---

### 1.7 Accessibility and Inclusivity

Android design emphasizes inclusivity through **built-in accessibility considerations**:

* `Contrast ratios` must meet at least `4.5:1` **for readability**.
* `Touch targets` must be at least `48 dp × 48 dp` **for easy interaction**.
* `Typography scales` **use `sp` (scale-independent pixels)** **to respect user font-size preferences**.
* `Color contrast and motion settings` adjust `automatic`ally for accessibility features (e.g., **high contrast mode, reduced motion**).

This **ensures that the UI remains usable for everyone, regardless of visual or motor limitations**.

---

### 1.8 Summary

At its core, Android UI design — through Material Design — is about `clarity, coherence, and meaning`.
Every aspect of the system serves these **goals**:

| Concept               | Purpose                                  |
| --------------------- | ---------------------------------------- |
| `Material metaphor` | Establishes `depth` **and** `realism`            |
| `Color roles`       | Ensure `harmony` **and** `contrast`              |
| `Typography scale`  | Creates `structure` **and** `readability`        |
| `Elevation`         | Communicates `hierarchy` **and** `interactivity` |
| `Motion`            | Explains `change` **and** guides `focus`         |
| `Accessibility`     | Guarantees `inclusivity` **and** `comfort`       |