---
id: bv0vqxq9b819hcknthk566o
title: 3 - Testing
desc: ''
updated: 1749741611913
created: 1749739643312
---

## Testing using Jest, Detox, and React Native Testing Library

### 1. Jest (Unit & Snapshot Testing)

Jest is the `default` `testing framework` **that comes with React Native**.

**What it’s used for:**

* `Unit testing` `functions and components`
* `Snapshot testing` `to detect UI regressions`



<!-- start of 'regressions' section -->
<details>
    <summary>Definition: regressions</summary>

#
Regressions **are** `unintended` `problems or bugs` `that appear in software` `after making changes`, **such as updates or new features**, `causing previously working functionality` `to break or behave incorrectly`.

---
</details>
<!-- end of 'regressions' section -->



####
**Basic example:**

```js
import { add } from './utils';

test('adds numbers', () => {
  expect(add(2, 3)).toBe(5);
});
```

**Snapshot test:**

```js
import React from 'react';
import renderer from 'react-test-renderer';
import MyComponent from './MyComponent';

test('renders correctly', () => {
  const tree = renderer.create(<MyComponent />).toJSON();
  expect(tree).toMatchSnapshot();
});
```

---

### 2. React Native Testing Library (`Component Testing`)

`Built on top of 'react-test-renderer'` and focused on testing components like users interact with them.

**What it’s used for:**

* `Testing` `component behavior` **and** `UI output`
* `Simulating` `user interactions`

**`Install`:**

```bash
npm install --save-dev @testing-library/react-native
```

**Example:**

```js
import { render, fireEvent } from '@testing-library/react-native';
import Counter from './Counter';

test('increments counter on press', () => {
  const { getByText } = render(<Counter />);
  fireEvent.press(getByText('Increment'));
  expect(getByText('Count: 1')).toBeTruthy();
});
```

---

### 3. Detox (`End-to-End Testing`)

Detox is used `for testing` `real interactions` `on devices or emulators`.

**What it’s used for:**

* `Full` **app** `automation`: **button taps**, **screen transitions**, **async waits**
* `Testing on` `real devices/emulators`

**Install:**

```bash
npm install --save-dev detox
```

You **also need to** `configure` **your** '`package.json`' `and build` **your** `app for testing`.

**Example:**

```js
describe('Login flow', () => {
  beforeAll(async () => {
    await device.launchApp();
  });

  it('should show login screen', async () => {
    await expect(element(by.id('login-screen'))).toBeVisible();
  });

  it('should log in successfully', async () => {
    await element(by.id('username')).typeText('testuser');
    await element(by.id('password')).typeText('password');
    await element(by.id('login-button')).tap();
    await expect(element(by.id('home-screen'))).toBeVisible();
  });
});
```