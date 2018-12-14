# angular2-webpack 创建者[@hulu7](https://github.com/hulu7)（支持中文和英文）
[![引用库的状态](https://david-dm.org/preboot/angular-webpack/status.svg)](https://david-dm.org/preboot/angular-webpack#info=dependencies) [![引用库的状态](https://david-dm.org/preboot/angular-webpack/dev-status.svg)](https://david-dm.org/preboot/angular-webpack#info=devDependencies)

>这是一个完整的针使用Webpack构建Angular 2+版本初学者的入门项目

本项目是一个Angular的入门项目，主要帮助任何打算快速掌握基于TypeScript的Angular的开发人员。本想项目使用[Webpack](http://webpack.github.io/)进行文件和模板的构建。本项目也使用Protractor进行端到端测试，使用Karmar进行单元测试。使用本项目前请了解如下知识：
* 了解[Angular](https://angular.io/)的文件和架构在最佳实践。
* 准备支持 [TypeScript](http://www.typescriptlang.org/)的 [Webpack](https://webpack.github.io/docs/)构建环境。
* 了解 [Jasmine](http://jasmine.github.io/) 和 [Karma](http://karma-runner.github.io/)对Angular进行测试的相关知识。
* 了解覆盖率测试工具 [Istanbul](https://github.com/gotwarlost/istanbul)。
* 了解端到端测试框架 [Protractor](https://angular.github.io/protractor/) 进行Angular测试的方法。
* 了解样式类型 [SASS](http://sass-lang.com/) (非必须, 本项目也支持常规css)。
* 了解静态代码分析工具 [TSLint](http://palantir.github.io/tslint/) 和 [Codelyzer](https://github.com/mgechev/codelyzer)的使用方法。

>提示: 请确保使用最新版本在 Node.js 和 NPM

### 快速进入项目

```bash
# 克隆代码
$ git clone https://github.com/hulu7/Angular2-Webpack.git my-app

# 进入项目目录
$ cd my-app

# 用 npm 安装项目依赖文件
$ npm install

# 启动本地服务器
$ npm start
```
用浏览器打开 [http://localhost:8080](http://localhost:8080)

# 项目文件结构

* [入口](#getting-started)
    * [依赖文件](#dependencies)
    * [安装文件](#installing)
    * [开发文件](#developing)
    * [测试代码](#testing)
    * [生产环境](#production)
    * [文档](#documentation)
* [问题和解答](#faq)
* [TypeScript](#typescript)
* [许可证](#license)

# 入门

## 安装依赖

运行次应用所需要在依赖:
* `node` 和 `npm` (使用 [NVM](https://github.com/creationix/nvm))
* 确保运行的 Node (`v6.x.x`+) 和 NPM (`3.x.x`+) 版本符合要求

## 安装

* `fork` 本代码库
* `clone` 你的 fork
* `npm install` 来安装所有依赖文件

## 开发

在完成所有依赖安装之后运行如下命令运行应用:

* `npm start`

项目将启动本地服务器 `webpack-dev-server` ，它将检测代码变化、自动构建（内存中），自动刷新页面。 应用在页面网址是 `http://localhost:8080`.

作为备选项，你可以使用模块热替换 (HMR):

* `npm run start:hmr`

完成所有设置后，你就能修改组件代码实时看到运行结果而不用手动刷新页面。

## 测试

#### 1. 单元测试

* 命令模式: `npm test`
* 实时模式 (TDD 风格): `npm run test-watch`

#### 2. 端到端测试 (e2e, 集成测试)

* 命令模式:
  * 窗口1, *如果项目没有启动，请先运行!*: `npm start`
  * 窗口2, 运行命令: `npm run webdriver-start`
  * 窗口3, 运行命令: `npm run e2e`
* 交互模式:
  * 除了上述命令, 你也可以运行命令: `npm run e2e-live`
  * 在编写和调试测试用例之前, 你可以在element explorer中直接使用Protractor命令可以避免运行所有在测试用例.
  * 更多详细信息可以查看 [Protractor Interactive Mode here](https://github.com/angular/protractor/blob/master/docs/debugging.md#testing-out-protractor-interactively)

## 生产环境

构建用于生产环境的代码，可以运行命令:

* `npm run build`

构建之后在生产代码执行文件在目录 `/dist`， 可以该目录下在文件直接部署到服务器上!

## 文档

你也可以运行如下命令生成 api 文档 (基于 [TypeDoc](http://typedoc.org/)):

* `npm run docs`

# FAQ

#### 需要添加 脚本或者链接标签到index.html中吗 ?

不需要， Webpack将自动添加所需要的以脚本标签形式的Javascript bundles和所有链接形式在样式文件。这样在好处在于不需要每次构建都修改index.html文件来更新hash值。

#### 如何引入外部 angular 库 ?

很简单, 只需要通过 npm 命令来导入所需要在代码. 同时需要在 [bootstrap](https://github.com/preboot/angular-webpack/blob/master/src/main.ts) 中设置外部依赖库。

#### 如何引入外部 css 文件象 bootstrap.css ?

只需要通过 [vendor.ts](https://github.com/preboot/angular-webpack/blob/master/src/vendor.ts) 来安装和导入样式文件。以bootstrap为例， 运行命令:

```sh
npm install bootstrap@next --save
```

同时在 [vendor.ts](https://github.com/preboot/angular-webpack/blob/master/src/vendor.ts) 中加入如下设置:

```ts
import 'bootstrap/dist/css/bootstrap.css';
```

# TypeScript

> 为了充分发挥TypeScript的优势， 你应该为编辑器选择正确在插件。

## 支持TypeScript的编辑器

可选择的编辑器:

* [Visual Studio Code](https://code.visualstudio.com/)
* [Webstorm 11+](https://www.jetbrains.com/webstorm/download/)
* [Atom](https://atom.io/) with [TypeScript plugin](https://atom.io/packages/atom-typescript)
* [Sublime Text](http://www.sublimetext.com/3) with [Typescript-Sublime-Plugin](https://github.com/Microsoft/Typescript-Sublime-plugin#installation)

# License

[MIT](/LICENSE)

联系方式:huiskai@hotmail.com


# angular2-webpack created by [@hulu7](https://github.com/hulu7) (Both Chinese and English are supported)
[![Dependency Status](https://david-dm.org/preboot/angular-webpack/status.svg)](https://david-dm.org/preboot/angular-webpack#info=dependencies) [![devDependency Status](https://david-dm.org/preboot/angular-webpack/dev-status.svg)](https://david-dm.org/preboot/angular-webpack#info=devDependencies)

A complete, yet simple, starter for Angular v2+ using Webpack.

This seed repo serves as an Angular starter for anyone looking to get up and running with Angular and TypeScript fast. Using [Webpack](http://webpack.github.io/) for building our files and assisting with boilerplate. We're also using Protractor for our end-to-end story and Karma for our unit tests.
* Best practices in file and application organization for [Angular](https://angular.io/).
* Ready to go build system using [Webpack](https://webpack.github.io/docs/) for working with [TypeScript](http://www.typescriptlang.org/).
* Testing Angular code with [Jasmine](http://jasmine.github.io/) and [Karma](http://karma-runner.github.io/).
* Coverage with [Istanbul](https://github.com/gotwarlost/istanbul)
* End-to-end Angular code using [Protractor](https://angular.github.io/protractor/).
* Stylesheets with [SASS](http://sass-lang.com/) (not required, it supports regular css too).
* Error reported with [TSLint](http://palantir.github.io/tslint/) and [Codelyzer](https://github.com/mgechev/codelyzer).
* Documentation with [TypeDoc](http://typedoc.org/).

>Warning: Make sure you're using the latest version of Node.js and NPM

### Quick start

```bash
# clone our repo
$ git clone https://github.com/hulu7/Angular2-Webpack.git my-app

# change directory to your app
$ cd my-app

# install the dependencies with npm
$ npm install

# start the server
$ npm start
```
go to [http://localhost:8080](http://localhost:8080) in your browser.

# Table of Contents

* [Getting Started](#getting-started)
    * [Dependencies](#dependencies)
    * [Installing](#installing)
    * [Developing](#developing)
    * [Testing](#testing)
    * [Production](#production)
    * [Documentation](#documentation)
* [Frequently asked questions](#faq)
* [TypeScript](#typescript)
* [License](#license)

# Getting Started

## Dependencies

What you need to run this app:
* `node` and `npm` (Use [NVM](https://github.com/creationix/nvm))
* Ensure you're running Node (`v6.x.x`+) and NPM (`3.x.x`+)

## Installing

* `fork` this repo
* `clone` your fork
* `npm install` to install all dependencies

## Developing

After you have installed all dependencies you can now start developing with:

* `npm start`

It will start a local server using `webpack-dev-server` which will watch, build (in-memory), and reload for you. The application can be checked at `http://localhost:8080`.

As an alternative, you can work using Hot Module Replacement (HMR):

* `npm run start:hmr`

And you are all set! You can now modify your components on the fly without having to reload the entire page.

## Testing

#### 1. Unit Tests

* single run: `npm test`
* live mode (TDD style): `npm run test-watch`

#### 2. End-to-End Tests (aka. e2e, integration)

* single run:
  * in a tab, *if not already running!*: `npm start`
  * in a new tab: `npm run webdriver-start`
  * in another new tab: `npm run e2e`
* interactive mode:
  * instead of the last command above, you can run: `npm run e2e-live`
  * when debugging or first writing test suites, you may find it helpful to try out Protractor commands without starting up the entire test suite. You can do this with the element explorer.
  * you can learn more about [Protractor Interactive Mode here](https://github.com/angular/protractor/blob/master/docs/debugging.md#testing-out-protractor-interactively)

## Production

To build your application, run:

* `npm run build`

You can now go to `/dist` and deploy that to your server!

## Documentation

You can generate api docs (using [TypeDoc](http://typedoc.org/)) for your code with the following:

* `npm run docs`

# FAQ

#### Do I need to add script / link tags into index.html ?

No, Webpack will add all the needed Javascript bundles as script tags and all the CSS files as link tags. The advantage is that you don't need to modify the index.html every time you build your solution to update the hashes.

#### How to include external angular libraries ?

It's simple, just install the lib via npm and import it in your code when you need it. Don't forget that you need to configure some external libs in the [bootstrap](https://github.com/preboot/angular-webpack/blob/master/src/main.ts) of your application.

#### How to include external css files such as bootstrap.css ?

Just install the lib and import the css files in [vendor.ts](https://github.com/preboot/angular-webpack/blob/master/src/vendor.ts). For example this is how to do it with bootstrap:

```sh
npm install bootstrap@next --save
```

And in [vendor.ts](https://github.com/preboot/angular-webpack/blob/master/src/vendor.ts) add the following:

```ts
import 'bootstrap/dist/css/bootstrap.css';
```

# TypeScript

> To take full advantage of TypeScript with autocomplete you would have to use an editor with the correct TypeScript plugins.

## Use a TypeScript-aware editor

We have good experience using these editors:

* [Visual Studio Code](https://code.visualstudio.com/)
* [Webstorm 11+](https://www.jetbrains.com/webstorm/download/)
* [Atom](https://atom.io/) with [TypeScript plugin](https://atom.io/packages/atom-typescript)
* [Sublime Text](http://www.sublimetext.com/3) with [Typescript-Sublime-Plugin](https://github.com/Microsoft/Typescript-Sublime-plugin#installation)

# License

[MIT](/LICENSE)

contact:huiskai@hotmail.com
