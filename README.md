# use husky

## pre-commit git hook

### step 1

```sh
npm install husky -D
```

### step 2

add npm-script prepare

```json
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview --port 5050",
    "lint": "eslint . --ext .vue,.js,.jsx,.cjs,.mjs --fix --ignore-path .gitignore",
    "prepare": "husky install"
  },
```

### step 3

```sh
# generate .husky folder in current project
npm run prepare
```

### step 4

```sh
npx husky add .husky/pre-commit "npm run lint"
```

Windows下执行报错：husky用法错误，上述命令改为：

```sh
npx husky add .husky/pre-commit "npm-run-lint"
# 如果用lint-staged
# npm install lint-staged -D
# npx husky add .husky/pre-commit "npx lint-staged"
```

再手动修改 `.husky/pre-commit` 文件， `npm-run-lint` 改为 `npm run lint`


### step 5

每次commit的时候会执行 `npm run lint`


## 参考博客

* https://www.jianshu.com/p/552142ff16db



---

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=johnsoncodehk.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=johnsoncodehk.vscode-typescript-vue-plugin).

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```
