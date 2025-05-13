---
id: 2ck61o7tvvm5tp6drd4xo5i
title: 2 - ScrollView, FlatList and SectionList
desc: ''
updated: 1747099936538
created: 1747097921474
---

Three core React Native components used `for displaying` `scrollable content`. Here's what makes each one unique and how they differ from typical web behavior:

---

### 📜 1. `ScrollView`

**What it is**:
A `generic` `scroll container`. Think of it **like a div with 'overflow: scroll'**, **but optimized for small lists or fixed content**.

```js
import { ScrollView, Text } from 'react-native';

<ScrollView>
  <Text>Item 1</Text>
  <Text>Item 2</Text>
  {/* ...more items */}
</ScrollView>
```

**Use when**:

* `Content` is `small or limited` `in size`.
* **You want** `vertical or horizontal` `scrolling`.

**Important**:

* `All content` is `rendered` `up front`, **so** `performance drops` `with large lists`.

---

### 📄 2. `FlatList`

**What it is**:
An `optimized`, `performant list` component `for large` `scrollable lists`. Think of it as a React Native replacement for '.map()'-generated elements in web React.

```js
import { FlatList, Text } from 'react-native';

const data = [{ id: '1', title: 'First' }, { id: '2', title: 'Second' }];

<FlatList
  data={data}
  keyExtractor={(item) => item.id}
  renderItem={({ item }) => <Text>{item.title}</Text>}
/>
```

**Use when**:

* You have a `long list` **of** `items`.
* **You need** `lazy-loading` `or performance optimization`.

**Key props**:

* **'data'** – your `array of` `items`
* **'renderItem'** – function `to render` `each item`
* **'keyExtractor'** – `unique key` `for each item`

---

### 📚 3. `SectionList`

**What it is**:
**Like 'FlatList'**, but `supports` `grouped sections` `with headers` (**like a contacts list sorted by letter**).

```js
import { SectionList, Text } from 'react-native';

const sections = [
  { title: 'A', data: ['Alice', 'Arnold'] },
  { title: 'B', data: ['Bob', 'Barbara'] },
];

<SectionList
  sections={sections}
  keyExtractor={(item, index) => item + index}
  renderItem={({ item }) => <Text>{item}</Text>}
  renderSectionHeader={({ section }) => <Text style={{ fontWeight: 'bold' }}>{section.title}</Text>}
/>
```

**Use when**:

* **You want a** `list` `grouped by` `categories or sections`.
* **You need settings menus or alphabetical lists for example**.

---

### 🧠 Summary

| Component     | Use Case                        | Optimized for Large Lists? | Supports Sections? |
| ------------- | ------------------------------- | -------------------------- | ------------------ |
| **ScrollView**  | `Short` `scrollable content`        | ❌                          | ❌                  |
| **FlatList**    | `Long`, `flat list` `of items`        | ✅                          | ❌                  |
| **SectionList** | `Long`, `grouped list` `with headers` | ✅                          | ✅                  |