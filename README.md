# quickapp-h5
在网页中调用快应用的相关功能.


# [quickapp-h5](https://github.com/jinwyp/quickapp-h5)
[![](https://img.shields.io/badge/Powered%20by-jslib%20base-brightgreen.svg)](https://github.com/jinwyp/quickapp-h5)
[![license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/jinwyp/quickapp-h5/blob/master/LICENSE)
[![Build Status](https://travis-ci.org/jinwyp/quickapp-h5.svg?branch=master)](https://travis-ci.org/jinwyp/quickapp-h5)
[![Coveralls](https://img.shields.io/coveralls/jinwyp/quickapp-h5.svg)](https://coveralls.io/github/jinwyp/quickapp-h5)
[![npm](https://img.shields.io/badge/npm-0.1.0-orange.svg)](https://www.npmjs.com/package/quickapp-h5)
[![NPM downloads](http://img.shields.io/npm/dm/quickapp-h5.svg?style=flat-square)](http://www.npmtrends.com/quickapp-h5)
[![Percentage of issues still open](http://isitmaintained.com/badge/open/jinwyp/quickapp-h5.svg)](http://isitmaintained.com/project/jinwyp/quickapp-h5 "Percentage of issues still open")

English | [简体中文](./README.zh-CN.md)

The best third party `JS|TS` library scaffold. By forking or cloning the repository, you can complete the basic framework for building a new library.

**The library that based quickapp-h5 can be shared to the [jsmini](https://github.com/jsmini) platform**

## Characteristics

- Coded in ES6+ or TypeScript, easily compile and generate production code
- Integrated babel-runtime (Default set to closed)
- Third parties rely on automatic injection(Tree shaking)
- Supports multi environment, including default browsers, Node, AMD, CMD, Webpack, Rollup, Fis and so on.
- Integrated code style lint(eslint|tslint).
- Integrated unit test environment(mocha).
- Integrated test coverage(istanbul).
- Integrated continuous integration tool [travis-ci](https://www.travis-ci.org/)
- Supports banner
- Supports one-key renaming.
- Supports [sideEffects](https://github.com/webpack/webpack/tree/master/examples/side-effects)
- Integrated Issue template
- Integrated [jsmini](https://github.com/jsmini)

**Note:** When `export` and `export default` are not used at the same time, there is the option to 
turn on `legacy mode`. Under `legacy mode`, the module system can be compatible with `IE6-8`. For more information on legacy mode, 
please see rollup supplemental file. 

## Compatibility
Unit tests guarantee support on the following environment:

| IE   | CH   | FF   | SF   | OP   | IOS  | Android   | Node  |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ----- |
| 6+   | 29+ | 55+  | 9+   | 50+  | 9+   | 4+   | 4+ |

> Note: Compiling code depend on ES5, so you need import [es5-shim](http://github.com/es-shims/es5-shim/) to compatible with `IE6-8`, here is a [demo](./demo/demo-global.html)

## Directory
```
├── demo - Using demo
├── dist - Compiler output code
├── doc - Project documents
├── src - Source code directory
├── test - Unit tests
├── CHANGELOG.md - Change log
└── TODO.md - Planned features
```

## Usage Instructions

Using npm, download and install the code. 

```bash
$ npm install --save quickapp-h5
```


Pls check demo folder for detail,  parameter 'option' see doc: [quickapp 快应用](https://doc.quickapp.cn/tutorial/platform/url-jump-configuration.html)
```javascript

const quickApp1 = new QuickApp();
const option = {
    path: '/Home',
    params: {
        path: 'Detail',
        title: '测试文章',
        url: 'http://test.wkanx.com/tmp/build/index.html',
        id: '3163241194045440',
        cid: 9999999,
        type: 0,
        template: 9999999,
        utm_source: 'push',
        pop: 0,
    },
    packageName: 'xxx',
    confirm: ''
}
quickApp1.open(option)


```

也可以在初始化 new QuickApp 时传入 packageName, 使用时 open 可以不传则默认使用初始化的packageName, 也可以传packageName 打开不同的快应用

```javascript

const quickApp1 = new QuickApp({
    packageName: 'xxx',
});
const option = {
    path: '/Home',
    params: {
        path: 'Detail',
        title: '测试文章',
        url: 'http://test.wkanx.com/tmp/build/index.html',
        id: '3163241194045440',
        cid: 9999999,
        type: 0,
        template: 9999999,
        utm_source: 'push',
        pop: 0,
    },
    packageName: 'xxx',
    confirm: ''
}
quickApp1.open(option)

```



For node environment：

```js
const QuickApp = require('quickapp-h5');
const quickApp1 = new QuickApp();
quickApp1.open({
                    path: '/Home',
                    params: {
                        path: 'Detail',
                        title: '测试文章',
                        url: 'http://test.wkanx.com/tmp/build/index.html',
                        id: '3163241194045440',
                        cid: 9999999,
                        type: 0,
                        template: 9999999,
                        utm_source: 'push',
                        pop: 0,
                    },
                    packageName: 'xxx',
                    confirm: ''
                });
```

For webpack or similar environment：

```js
import QuickApp from 'quickapp-h5';
const quickApp1 = new QuickApp();
quickApp1.open({
                    path: '/Home',
                    params: {
                        path: 'Detail',
                        title: '测试文章',
                        url: 'http://test.wkanx.com/tmp/build/index.html',
                        id: '3163241194045440',
                        cid: 9999999,
                        type: 0,
                        template: 9999999,
                        utm_source: 'push',
                        pop: 0,
                    },
                    packageName: 'xxx',
                    confirm: ''
                });
```

For requirejs environment:

```js
requirejs(['node_modules/quickapp-h5/dist/index.aio.js'], function (QuickApp) {
    const quickApp1 = new QuickApp();
    quickApp1.open({
                        path: '/Home',
                        params: {
                            path: 'Detail',
                            title: '测试文章',
                            url: 'http://test.wkanx.com/tmp/build/index.html',
                            id: '3163241194045440',
                            cid: 9999999,
                            type: 0,
                            template: 9999999,
                            utm_source: 'push',
                            pop: 0,
                        },
                        packageName: 'xxx',
                        confirm: ''
                    });
})
```

For browser environment:

```html
<script src="node_modules/quickapp-h5/dist/index.aio.js"></script>
```

## Documents
[API](./doc/api.md)

## Contribution Guide

How to switch `JS` and `TS`

- `srctype` and `scripts` in `package.json`
- `require` file of `test/test.js`
- `require` file of `test/browser/index.html`

For the first time to run, you need to install dependencies firstly.

```bash
$ npm install
```

To build the project:

```bash
$ npm run build
```

To run unit tests:

```bash
$ npm test
```

> Note: The browser environment needs to be tested manually under ```test/browser```

Modify the version number in package.json, modify the version number in README.md, modify the CHANGELOG.md, and then release the new version.

```bash
$ npm run release
```

Publish the new version to NPM.

```bash
$ npm publish
```

For renaming project, you need change `fromName` and `toName` in `rename.js`, then run `npm run rename`, this command will auto renaming names for below files:

- The messages in README.md
- The messages in package.json
- The messages in config/rollup.js
- The repository name in test/browser/index.html
- Library name in demo/demo-global.html

## Contributors

[contributors](https://github.com/jinwyp/quickapp-h5/graphs/contributors)

## Change Log
[CHANGELOG.md](./CHANGELOG.md)

## TODO
[TODO.md](./TODO.md)

## Current Users

- [jsmini](https://github.com/jsmini)
- [...](https://github.com/jinwyp/quickapp-h5/issues/10)


## Relative links

- [typescript-library-template](https://github.com/jiumao-fe/typescript-library-template)
