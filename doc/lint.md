<!--
 * @LastEditors: Tao Yang
 * @Description: 暂无描述
 * @FilePath: /front-end-project-standards/doc/lint.md
 * @Date: 2022-08-29 21:49:53
 * @LastEditTime: 2022-08-31 18:59:36
 * @Author: Tao Yang
-->
[TOC]
### ESLint

#### 安装
`yarn add -D eslint`

#### 生成配置
```
  npx eslint --init

  ? How would you like to use ESLint?
  ❯ To check syntax, find problems, and enforce code style

  ? What type of modules does your project use? …
  ❯ JavaScript modules (import/export)

  ? Which framework does your project use? …
  ❯ React

  ? Does your project use TypeScript?
  › Yes

  ? Where does your code run? …  (Press <space> to select, <a> to toggle all, <i> to invert selection)
  > Node

  ? How would you like to define a style for your project? …
  ❯ Answer questions about your style

  ? What format do you want your config file to be in? …
  ❯ JavaScript

  ? What style of indentation do you use? …
  ❯ Spaces

  ? What quotes do you use for strings? …
  ❯ Single

  ? What line endings do you use? …
  ❯ Unix

  ? Do you require semicolons?
  › Yes

  ? Would you like to install them now?
  › Yes

  ? Which package manager do you want to use? …
  ❯ yarn
```

#### 详细配置
`eslint-plugin-react @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-plugin-react-hooks`

`修改 .eslintrc.js`


#### 配置脚本
```json
  // package.json 添加脚本命令
  "lint": "eslint --ext .tsx --ext .ts src/",
```
#### 执行
`npm run lint`

#### 修复
`npx eslint ./src/**/*.tsx --fix`

#### 安装VSCode插件
`ESLint`

#### 修改VSCode配置文件
```json
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
```

### Prettier

#### 安装
`yarn add -D prettier eslint-plugin-prettier`

#### 生成配置
```js
  module.exports = {
    singleQuote: true,
    trailingComma: 'all',
    printWidth: 100,
  };
```

#### 在 ESLint 上配置 Prettier
```js
module.exports = {
  ...
  plugins: [..., 'prettier'],
  rules: {
    ...
    'prettier/prettier': 'error',
  },
  ...
};
```

#### 配置脚本
```json
  // package.json 添加脚本命令
  "format": "prettier --check ./src",
```
#### 执行
`yarn format`

#### 修复
`npx prettier --write ./src`

#### 安装VSCode插件
`prettier`

#### 修改VSCode配置文件
```json
  "editor.formatOnSave": true,
```

---

### husky && lint-staged

#### 安装
`yarn add -D husky`
`yarn add -D lint-staged`

#### 配置脚本
```json
  "lint-staged": {
    "src/**/*.{ts,tsx}": [
      "eslint --ext .tsx --ext .ts src/ --fix"
    ],
    "./src/**": [
      "prettier --write ."
    ]
  },
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
```

### 参考
[Use ESLint, Prettier like Pro on React Native](https://dev-yakuza.posstree.com/en/react-native/eslint-prettier-husky-lint-staged/?utm_source=pocket_mylist)
