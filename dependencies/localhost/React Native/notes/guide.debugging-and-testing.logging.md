---
id: qd88mmzy98wszctsy53zcah
title: 2 - Logging
desc: ''
updated: 1749739634273
created: 1749738656168
---

## Logging via Metro Bundler

Metro Bundler is the `JavaScript bundler` used by React Native. It also **acts as a central place** `for viewing logs` `during development`.

#### How logging works

You can `log information` **in your React Native app** `using`:

```js
console.log('Message');
console.warn('Warning');
console.error('Error');
```

**These logs** `appear in the terminal window running Metro` (**the one started by 'npx react-native start' or automatically opened when running the app**).

#### What you can do with it:

* `View` `real-time 'console.log()' output`
* `See` `JavaScript errors` `or stack traces`
* `Log` `object values` `for debugging` `state or props`
* `Track` `lifecycle events` **and** `function calls`

---

#### Tips

* `Use 'console.table()'` `for readable object/array output`
* `For focused debugging`, `temporarily disable` `noisy logs`
* `Combine with breakpoints` `for deeper inspection` (**using Chrome DevTools or React Native Debugger**)