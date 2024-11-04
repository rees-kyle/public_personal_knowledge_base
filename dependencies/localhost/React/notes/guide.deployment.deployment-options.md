---
id: lh6vuggnw58ntplgkfhrg4e
title: 1 - Deployment Options
desc: ''
updated: 1730764447034
created: 1730761403496
---

`For deploying` `React applications`, **there are a few** `popular platforms` `to consider`, **each with its strengths**:

### 1. **Netlify**
   - **Strengths**: 
     - `Free hosting` `for static sites`, `easy` `to connect` **with** `GitHub repositories`.
     - `Built-in CI/CD`, **so** `deployments` **happen** `automatically` **with every push**.
     - `Environment variables`, `custom domains`, `HTTPS`, **and** `simple configuration` `for redirects`.
   - **Setup**:
     - `Push` **your** `project` `to GitHub`, `link` **it** `to Netlify`, `select` **the** `branch`, **and** `set` **the** `build command` (**'npm run build'**) **and** `publish` `directory` (**'build'**).

> CI/CD: `Continuous` `Integration` **and** `Continuous Deployment` (**or** `Continuous Delivery`)



<!-- start of 'continuous integration and continuous deployment' section -->
<details>
  <summary>Definition: continuous integration and continuous deployment (or continuous delivery)</summary>

#
**CI/CD is a** `process` `in software development` **where 'Continuous Integration (CI)' means** `automatically` `testing and merging` `code changes` `to keep` **the** `codebase` `functional`, **and 'Continuous Deployment/Delivery (CD)' means** `automatically` `releasing` **those** `changes` `to users` (**in deployment**) `or preparing` **them** `for release` (**in delivery**) `as soon as` **they’re** `ready`. This **helps teams** `quickly` **and** `reliably` `deliver updates`.

---
</details>
<!-- end of 'continuous integration and continuous deployment' section -->



### 2. **Vercel**
   - **Strengths**:
     - **Great** `for` **both** `static and serverless applications`.
     - `Optimized` `for Next.js` `but works` **smoothly** `with React`.
     - `Automatic builds` `and deploys with` `GitHub integration`, `supports` `custom domains` **and** `environment variables`.
   - **Setup**:
     - `Link` **your** `GitHub repository` **in Vercel**, `select` **the** `build output directory` **as 'build'**, and Vercel will handle the rest.
   
### 3. **GitHub Pages**
   - **Strengths**:
     - `Free hosting` `for static sites` **directly** `from GitHub`.
     - **Great** `for smaller projects` **or** `documentation sites`.
     - `Supports` `custom domains`.
   - **Setup**:
     - `Run` `'npm run build'` `to generate` **the** `'build' folder`.
     - `Use` **a** `deployment tool` **like** `'gh-pages'` `to publish` **the** `build folder` `to GitHub Pages`, `or manually push to` **a** `'gh-pages' branch`.

`Each platform` **has** `specific advantages`, **so the best** `choice` `will depend on` **your** `project's complexity` **and** `personal preference`.