# react-blueprint
## Init project
```bash
$ npm init -y
Wrote to ~/react-blueprint/package.json:

{
  "name": "react-blueprint",
  "version": "1.0.0",
  "description": "```bash $ npm init -y",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/clockworkorange/react-blueprint.git"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/clockworkorange/react-blueprint/issues"
  },
  "homepage": "https://github.com/clockworkorange/react-blueprint#readme"
}
```
## Add jest
```bash
npm install --save-dev jest@23.6.0
```
Added `"private": true`  and `"test": "test"` to *package.json*
```json
{
  "name": "react-blueprint",
  "version": "1.0.0",
  "private": true,
  "description": "```bash $ npm init -y",
  "main": "index.js",
  "scripts": {
    "test": "jest"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/clockworkorange/react-blueprint.git"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/clockworkorange/react-blueprint/issues"
  },
  "homepage": "https://github.com/clockworkorange/react-blueprint#readme",
  "devDependencies": {
    "jest": "^24.8.0"
  }
}
```
## Checking Code Quality with ESLint
```bash
$ npx install-peerdeps --dev eslint-config-airbnb@17.1.1
```
Create *.eslintrc.js*
```js
module.exports = {
  plugins: ['jest'],
  extends: "airbnb",
  parserOptions: {
    ecmaVersion: 6,
  },
  env: {
    node: true,
  },
};
```
```bash
 $ npx eslint palindromes.test.js
```
```bash
npm install --save-dev eslint-plugin-jest@22.13.6
```

## Beautifying Code with Prettier
```bash
npm install --save-dev prettier-eslint-cli
```

```
// .eslintrc.js
module.exports = {
...
  rules: {
    quotes: ['error', 'single', { avoidEscape: true }],
    'comma-dangle': ['error', 'always-multiline'],
  },
};
```

## Using Babel for JSX
```
npm install --save-dev @babel/core@7.2.0
npm install --save-dev @babel/preset-react@7.0.0 @babel/preset-env@7.2.0
```

Create file .babelrc.js
```js
module.exports = {
  presets: ['@babel/preset-react', '@babel/preset-env'],
};
```

## Bridging Jest and Babel
```bash
npm install --save-dev jest@24.8.0 babel-jest@24.8.0
npm install --save-dev babel-core@^7.0.0-bridge.0
```

```bash
npm install react@16.8.6
npm install --save-dev react-dom@16.8.6
```

# Configuring eslint
```bash
npm install --save-dev eslint-plugin-react@7.14.3
```
```bash
npm install --save-dev babel-eslint@10.0.2
```
File *.eslintrc.js*
```js
module.exports = {
  plugins: ['react', 'jest'],
  extends: ["airbnb", 'plugin:jest/recommended'],
  parser: "babel-eslint",
  parserOptions: {
    ecmaVersion: 6,
    sourceType: 'module',
    ecmaFeatures: {
      jsx: true,
    },
  },
  settings: {
    react: {
      version: '16.8.6',
    },
  },
  env: {
    node: true,
  },
  rules: {
    quotes: ['error', 'single', { avoidEscape: true }],
    'comma-dangle': ['error', 'always-multiline'],
  },
};
```
File *src/tests/.eslintrc.js*
```js
module.exports = {
  plugins: ['jest'],
  extends: ['airbnb', 'plugin:jest/recommended'],
};
```
File *src/.eslintrc.js*
```js
module.exports = {
  env: {
    browser: true,
  },
};
```

## Getting Started with Enzyme
```bash
npm install --save-dev enzyme@3.10.0 enzyme-adapter-react-16@1.14.0
```

## Adding a Jest Setup File
File *jest.config.js*
```js
module.exports = {
  setupTestFrameworkScriptFile: './src/tests/jestSetup.js',
};
```

File *src/tests/jestSetup.js*
```js
import Adapter from 'enzyme-adapter-react-16';
import { configure } from 'enzyme';
configure({ adapter: new Adapter() });
```