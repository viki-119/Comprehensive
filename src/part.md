## [如何更新自己写的npm包（模块），假设已经在npm中发布了一个1.0.0版本的包](https://blog.csdn.net/cvper/article/details/79051048)

* 第一步：在本地更新这个包的版本  ,使用命令 npm version  <update_type>;
* 第二步：提交到远端npm中，使用命令npm publish;

### update_type 有三个参数:
* patch：这个是补丁的意思，补丁最合适；
* minor：这个是小修小改；
* major：这个是大改；

## [Visual Studio Code编写并实时预览Markdown](https://blog.csdn.net/supergao222/article/details/78596704)

### 方法一
* Ctrl + Shift + P 调出主命令框，输入 Markdown
* 选择Markdown: Open Preview to the Side，就能调出实时预览框了。
### 方法二
* 先按Ctrl + K，然后放掉，紧接着再按 v，也能调出实时预览框。

## [mac系统和windows系统如何键盘自定义设置](https://www.jianshu.com/p/314a9a1439f4)

* 下载KeyTweak软件实现        

## [babel实现代码转换](https://www.cnblogs.com/ertingbo/p/9474197.html)

```js
在项目目录中，安装 Babel
$ npm install --save-dev @babel/core

```

```js
# 命令行转码babel-cli
$ npm install -g babel-cli --save-dev

* npm install --save-dev babel-plugin-transform-react-jsx 

# ES2015转码规则
$ npm install --save-dev babel-preset-es2015
# 语法规则命令(用不到react的可以不用)
$ npm install --save-dev babel-preset-react
转换规则命令
# ES7不同阶段语法提案的转码规则（共有4个阶段），选装一个
$ npm install --save-dev babel-preset-stage-0
$ npm install --save-dev babel-preset-stage-1
$ npm install --save-dev babel-preset-stage-2
$ npm install --save-dev babel-preset-stage-3
$ npm install --save-dev babel-preset-stage-4

```
```js
Babel的配置文件是.babelrc
{
  "presets": [
    "es2015",
    "react",
    "stage-2"
  ],
  "plugins": []
}

or

# 在项目目录中，安装 Babel
$ npm install --save-dev @babel/core
# 命令行转码@babel/cli
$ npm install -g @babel/cli --save-dev
# 最新转码规则
$ npm install --save-dev @babel/preset-env
# 语法规则命令(用不到react的可以不用)
$ npm install --save-dev @babel/preset-react
{
  "presets": [
    "@babel/env",
    "@babel/preset-react"
  ],
  "plugins": []
}
```

```js
# 转码结果输出到标准输出
$ npx babel example.js

# 转码结果写入一个文件
# --out-file 或 -o 参数指定输出文件
$ npx babel example.js --out-file compiled.js
# 或者
$ npx babel example.js -o compiled.js

# 整个目录转码
# --out-dir 或 -d 参数指定输出目录
$ npx babel src --out-dir lib
# 或者
$ npx babel src -d lib

# -s 参数生成source map文件
$ npx babel src -d lib -s
```

```js
{
  "devDependencies": {
    "babel-cli": "^6.0.0"
  },
  "scripts": {
    "build": "npx babel src -d lib"
  },
}
```
```js
转码的时候就可以使用如下命令：
npm run build
```
[参考文档](https://www.cnblogs.com/zuoan-oopp/p/6484597.html)  
[参考文档](http://es6.ruanyifeng.com/#docs/intro)


## [babel单个文件转码](https://segmentfault.com/q/1010000015213294?utm_source=tag-newest)

* 包名： transform-es2015-modules-commonjs

### 创建react应用
https://react.docschina.org/docs/create-a-new-react-app.html

### [eslint相关包](https://www.jianshu.com/p/39e8aad781ed)

#### [eslint官网](http://eslint.cn/docs/user-guide/configuring#disabling-rules-with-inline-comments)

* npm install eslint --save-dev  
* npm install babel-eslint --save-dev
* npm install eslint-config-airbnb --save-dev
* npm install eslint-plugin-import --save-dev

// 下面两个为react项目安装，非react项目不需要安装
* npm install eslint-plugin-jsx-a11y --save-dev
* npm install eslint-plugin-react --save-dev

### [git commit前检测husky与pre-commit](https://www.jianshu.com/p/f0d31f92bfab)

查看全局安装的包：npm list -g --depth 0
