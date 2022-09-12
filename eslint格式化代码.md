# 配置eslint自动格式化代码

## 安装eslint

``` sh
npm install --save-dev eslint eslint-plugin-vue

//or

yarn add -D eslint eslint-plugin-vue
```

## 初始化eslint

``` sh
./node_modules/.bin/eslint --init

//or

eslint --init //全局安装了的时候
```

保证`.eslintrc.js`文件里面有的extends有规则

``` js
module.exports = {
  extends: [
    // add more generic rulesets here, such as:
    // 'eslint:recommended',
    'plugin:vue/vue3-recommended',
    // 'plugin:vue/recommended' // 如果您使用的是Vue2
  ],
  rules: {
    // override/add rules settings here, such as:
    // 'vue/no-unused-vars': 'error'
  }
}
```

更多详细的规则 <https://eslint.vuejs.org/>

## 打开保存自动格式化

ctrl+shift+p 进入vscode的配置页面settings.json，然后添加或修改下面的配置

```json
"editor.formatOnSave": true, //打开自动保存
"editor.codeActionsOnSave": {
    "source.fixAll.eslint": true //设置保存后操作，eslint --fix
  },
  ```

这三步是为了配置不让vetur格式话js和html，只格式话css或者sass/less就好

``` json
  "[vue]": {
        "editor.defaultFormatter": "octref.vetur" //设置vetur为格式化的配置
    },
    "vetur.format.defaultFormatter.js": "none", //取消格式化js
    "vetur.format.defaultFormatter.html": "none", //取消格式化html
```