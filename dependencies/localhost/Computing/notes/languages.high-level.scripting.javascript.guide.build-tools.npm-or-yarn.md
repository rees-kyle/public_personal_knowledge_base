---
id: fzk98vbajg3abqgovu1up9d
title: 3 - npm or yarn
desc: ''
updated: 1715696738873
created: 1715593117988
---

> npm: Node Package Manager

Both npm and Yarn are popular JavaScript `package managers` **and** `build tools`, commonly used `for managing dependencies` `and running` **various** `scripts` **in JavaScript projects**. Here's a brief comparison:



<!-- start of 'dependency' section -->
<details>
  <summary>Definition: dependency</summary>

#
Dependency **refers to the** `reliance` `or need for` `something or someone` `to fulfill` **a particular** `function` `or provide support`. It **implies a relationship where** `one` `thing or person is` `dependent on` `another for` `its existence`, `operation`, `or well-being`.

---
</details>
<!-- end of 'dependency' section -->



- **npm:**
  - npm comes `bundled with` `Node.js`, so you **don't need to install anything extra**.
  - It has a `huge registry of` `packages`.
  - It has a `flat dependency tree`, **meaning it installs dependencies in a flat file structure**, which `can sometimes` `lead to` `dependency conflicts`.
  - npm `version 5` **introduced a** `lock file` (**package-lock.json**) `to help with` `deterministic dependency resolution`, **ensuring** `consistent installs` `across different` `environments`.



<!-- start of 'deterministic' section -->
<details>
  <summary>Definition: deterministic</summary>

#
Deterministic **refers to a** `system or process` **where the** `outcome is` **entirely** `predictable` `based on` **the** `initial conditions and` **the** `rules governing` **the** `system`. **In other words**, **in a deterministic system**, **given the same starting conditions**, **the** `result` **will** `always` **be** `the same`, `without` `any` `randomness or uncertainty`.

---
</details>
<!-- end of 'deterministic' section -->



- **Yarn:**
  - Yarn was `developed by` `Facebook` **and other members of the JavaScript community** `to address` `some of` **the** `shortcomings of` `npm`.



<!-- start of 'shortcomings' section -->
<details>
  <summary>Definition: shortcomings</summary>

#
Shortcomings **are** `weaknesses`, `limitations`, `or deficiencies in` `something`, **such as a** `system`, `process`, `idea`, `or product`. They represent areas **where** `improvements or adjustments` `are needed to` `enhance` `effectiveness`, `efficiency`, **or overall** `performance`.

---
</details>
<!-- end of 'shortcomings' section -->



  - It was **designed** `to be faster` `and more reliable than` `npm`.
  - Yarn uses a `lock file` (**yarn.lock**) `by default`, **ensuring** `deterministic installs`, which **can help** `avoid` **some of the** `dependency issues` `npm faced`.
  - Yarn's caching mechanism makes installing packages faster, especially when multiple projects depend on the same packages.



<!-- start of 'caching' section -->
<details>
  <summary>Definition: caching</summary>

#
Caching **is a** `technique` **used in computing** `to store` `copies of` `frequently accessed` `or recently used` `data in` `a location` **that is** `easily accessible`. This helps **to improve the speed and efficiency of data retrieval**, as the `data` **can be** `quickly retrieved from` **the** `cache` `instead of` **having to be reloaded from the** `original source`. Caching is **commonly** `used in` `web browsers`, `databases`, **and** `operating systems` `to optimize performance`.

---
</details>
<!-- end of 'caching' section -->



Which one to use depends on your specific needs and preferences. `Both` **are** `capable tools`, and the choice between them often comes down to factors like speed, reliability, and familiarity. **Many developers** `use` `Yarn` **due to its perceived** `performance benefits`, **while others stick with** `npm for` **its** `simplicity and` **built-in nature with** `Node.js`.

`Job requirements` in the JavaScript development field **often** `mention` familiarity with `both` **Yarn and npm**. `However`, since `npm` has been around longer and is more deeply integrated into the Node.js ecosystem, it **tends to be** `mentioned` `more frequently in` `job postings`.



<!-- start of 'perceived' section -->
<details>
  <summary>Definition: perceived</summary>

#
"Perceived" **relates to** `how` `something is` `understood`, `interpreted`, `or experienced` `by` **an** `individual or` **a** `group`. It refers to the subjective understanding or impression of a situation, object, or concept, influenced by factors such as personal beliefs, past experiences, cultural background, and context. Perceptions can vary widely among different people and can be influenced by biases, emotions, and external influences.

---
</details>
<!-- end of 'perceived' section -->