---
layout: post
title: Vue全家桶搭档Typescript
subtitle: Typescript && Vue
date: 2018-06-26
author: Rick
catalog: true
header-img: img/vue-typescript.png
tags:
  -Vue Vuex Vue-Router Typescript
---

## Typescript是什么
Typescript是微软基于javascript基础之上的一门语言，其本身是javascript的超集，以兼容最新的ECMAScript标准为目的，并在基础之上集成强类型、接口、泛型等js本身不具备的强大特性！用好typescript能使我们的程序更为健壮、安全，提升开发效率。

### 开发环境搭建
本来想使用vue-cli3.0beta直接一键生成vue-typescript模板的，但是折腾半天以后发现还是问题多多，还是等正式版本出来以后再使用这个命令吧！退而求其次，我们先使用vue-cli命令生成一个vue全家桶项目的模板, 执行以下命令，然后一路回车确认即可
```zsh
vue init webpack vue-ts-demo 
```
第二步 添加typescript相关的包:
```zsh
npm install --save-dev typescript ts-loader tslint tslint-config-standard tslint-loader
```
第三步 在根目录下创建tsconfig.json的配置文件, 配置如下
```js
{
  "include": [
    "src/*",
    "src/**/*"
  ],
  "exclude": [
    "node_modules"
  ],
   "compilerOptions": {
    "types": [
      "node"
    ],
    "typeRoots": [
      "node_modules/@types"
    ],
    "noImplicitThis": true,
    "jsx": "preserve",
    "jsxFactory": "h",
    "allowJs": true,
    "allowSyntheticDefaultImports": true,
    "experimentalDecorators": true,
    "module": "esnext",
    "target": "es5",
    "moduleResolution": "node",
    "noImplicitAny": true,
    "lib": [
      "dom",
      "es2015",
      "es2017",
      "es2015.promise"
    ],
    "sourceMap": true,
    "pretty": true
  }
}
```
具体配置项的含义以及更多的配置项查看typescript官方文档<https://www.typescriptlang.org/>
