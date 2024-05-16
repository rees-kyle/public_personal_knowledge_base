---
id: ad89hctd66nh1kdq61rjwts
title: 2 - Babel
desc: ''
updated: 1715873614509
created: 1715592788735
---

Babel is a popular `JavaScript compiler` that **helps you** `write modern` **JavaScript** `code` `while maintaining compatibility` `with older` `browsers and environments`. It **allows you** `to use` **the** `latest features` **of the language** `without` `worrying about` `browser support`, **by transforming your modern code into a version that is widely supported**.

Here's a basic guide to getting started with Babel, including installation and setup:

### 1. Installation

First, you'll need to install Babel and its related packages. If you haven't already, `initialize` **your** `project` `with npm`:

```sh
# Initialize new Node.js project with default settings without asking for user input.
npm init -y
```

Then, `install` `Babel and` **its** `presets`:

```sh
# Install Babel core, CLI, and preset-env as development dependencies for the project.
npm install --save-dev @babel/core @babel/cli @babel/preset-env
```

### 2. Configuration

`Create` a `Babel `configuration file` **named** `.babelrc` `in` **the** `root of` **your** `project`:

```json
{
  // The "presets" key is used to specify an array of Babel presets
  "presets": [ // Presets are a set of plugins that determine what transformations Babel should apply to your code
    "@babel/preset-env" // Enables modern JavaScript features based on target environments
  ]
}
```

### 3. Usage

You can now use Babel `to transpile` **your** `JavaScript files`. For **example**, if you have a **file named 'src/app.js'**, you **can transpile it to the 'dist' directory with the following command**:

```sh
# Use npx to run the Babel CLI, 
# transpile JavaScript files in the 'src' directory,
# and output the transpiled files to the 'dist' directory.
npx babel src --out-dir dist
```

### 4. Integration with Build Tools

Babel can be integrated with various build tools **like** `Webpack`, `Gulp`, **or** `directly in` **your** `npm scripts`.

#### Using Webpack

**To use Babel with Webpack**, you'll need to `install` **the** `Babel loader for` `Webpack`:

```sh
# Use npm to install babel-loader package as development dependency
npm install --save-dev babel-loader
```

`Then`, `configure Webpack` to use Babel for JavaScript files. Here is a basic **example of a** `webpack.config.js` **file**:

```js
// Importing 'path' module from Node.js; to handle file paths
const path = require('path');

// Exporting webpack configuration object
module.exports = {
  // The entry point of application
  entry: './src/app.js',
  // Configuration; for output of bundled files
  output: {
    // The name of output bundle file
    filename: 'bundle.js',
    // The directory where bundled files will be output
    // Resolves absolute path to the 'dist' directory
    path: path.resolve(__dirname, 'dist')
  },
  // Configuration for modules
  module: {
    // Rules for transforming files
    rules: [
      {
        // Test for JavaScript files using a regular expression
        test: /\.js$/,
        // Exclude node_modules directory from processing
        exclude: /node_modules/,
        // Use Babel loader; to transpile JavaScript files
        use: {
          loader: 'babel-loader',
          // Options for Babel loader
          options: {
            // Preset to transpile modern JavaScript
            presets: ['@babel/preset-env']
          }
        }
      }
    ]
  }
};
```

### 5. Running the Build

**If you are using Webpack**, **you can** `add` **a** `script in` **your** '`package.json`' `to run` **the** `build`:

```json
{
  // Defines a set of scripts for npm commands
  "scripts": {
    // Defines a 'build' script for bundling the project
    "build": "webpack --mode production"
  }
}
```

Run the build with:

```sh
# Run the 'build' script defined in the 'package.json' file using npm
npm run build
```

This command `uses Webpack` `to bundle` **your** `application`, `transforming` **your** `modern JavaScript code into` **a** `format` **that is** `compatible with` `older browsers`.

### 6. Using Babel with npm Scripts

You can also use Babel directly in your npm scripts `without additional` `build tools`. **Add the following script to your** `'package.json'`:

```json
{
  // Defines a set of scripts for npm commands
  "scripts": {
    // Defines a 'build' script for transpiling JavaScript files in the 'src' directory
    "build": "babel src --out-dir dist" // and outputting them to the 'dist' directory using Babel
  }
}
```

Run the build with:

```sh
# Run the 'build' script defined in the package.json file using npm
npm run build
```

This setup **allows you** `to compile` **your** `JavaScript files` `with Babel` `using` **a** `simple` `npm command`.

### Conclusion

`Babel` is a powerful tool for modern JavaScript development, enabling you `to write` `code` `using` **the** `latest features` `while ensuring` `compatibility with` `older environments`. By integrating Babel with build tools like Webpack or using it directly in npm scripts, you can `streamline` **your** `development workflow` `and focus on` `writing high-quality`, **modern JavaScript** `code`.