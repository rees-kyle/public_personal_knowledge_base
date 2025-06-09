---
id: fdfv9mgskk46l25b083d1d5
title: 1 - HTTP Requests
desc: ''
updated: 1749504223682
created: 1749503902391
---

In React Native, you `use the same libraries and techniques` **for networking** `as` **in** `React`:

### `fetch` (built-in)

```js
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error(error));
```

### `Axios` (external library)

`Install`:

```bash
npm install axios
```

**Usage**:

```js
import axios from 'axios';

axios.get('https://api.example.com/data')
  .then(response => console.log(response.data))
  .catch(error => console.error(error));
```

---

### Summary

* **Works the** `same as` in `React` (web)
* `Supports` `all HTTP methods` (**GET**, **POST**, **PUT**, **DELETE**, etc.)
* **Can be used with** `async/await` too
* `Axios` **offers** `more features` **out of the box** (`interceptors`, `default headers`)