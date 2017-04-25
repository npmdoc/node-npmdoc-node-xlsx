# npmdoc-node-xlsx

#### basic api documentation for  [node-xlsx (v0.7.4)](https://github.com/mgcrea/node-xlsx#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-node-xlsx.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-node-xlsx) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-node-xlsx.svg)](https://travis-ci.org/npmdoc/node-npmdoc-node-xlsx)

#### NodeJS Excel files parser & builder

[![NPM](https://nodei.co/npm/node-xlsx.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/node-xlsx)

- [https://npmdoc.github.io/node-npmdoc-node-xlsx/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-node-xlsx/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-node-xlsx/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-node-xlsx/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-node-xlsx/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-node-xlsx/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Olivier Louvignes"
    },
    "bugs": {
        "url": "https://github.com/mgcrea/node-xlsx/issues"
    },
    "dependencies": {
        "xlsx": "^0.8.0"
    },
    "description": "NodeJS Excel files parser & builder",
    "devDependencies": {
        "babel-cli": "^6.16.0",
        "babel-eslint": "^7.0.0",
        "babel-plugin-transform-class-properties": "^6.16.0",
        "babel-plugin-transform-function-bind": "^6.8.0",
        "babel-plugin-transform-object-rest-spread": "^6.16.0",
        "babel-preset-es2015": "^6.16.0",
        "babel-register": "^6.16.3",
        "codeclimate-test-reporter": "^0.4.0",
        "eslint": "^3.8.1",
        "eslint-config-airbnb-base": "^9.0.0",
        "eslint-plugin-import": "^2.0.1",
        "eslint-plugin-jsx-a11y": "^2.2.3",
        "expect": "^1.20.2",
        "mocha": "^3.1.2",
        "nyc": "^8.3.1",
        "rimraf": "^2.5.4"
    },
    "directories": {},
    "dist": {
        "shasum": "1c3318e43b6c7ca4d01badb9f88f277a31e8a805",
        "tarball": "https://registry.npmjs.org/node-xlsx/-/node-xlsx-0.7.4.tgz"
    },
    "gitHead": "4b3dc3fc626587ae075a23ec7d6ce4095d2f1e25",
    "homepage": "https://github.com/mgcrea/node-xlsx#readme",
    "keywords": [
        "excel",
        "parser",
        "builder",
        "xlsx",
        "xls"
    ],
    "license": "Apache-2.0",
    "main": "lib/index.js",
    "maintainers": [
        {
            "name": "mgcrea"
        }
    ],
    "name": "node-xlsx",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/mgcrea/node-xlsx.git"
    },
    "scripts": {
        "compile": "rimraf lib/*; babel src/ -d lib/ -s",
        "compile:watch": "npm run compile -- -w",
        "lint": "eslint src/",
        "prepublish": "npm run compile",
        "start": "npm run test:watch",
        "test": "mocha",
        "test:coverage": "nyc --reporter=lcov npm test -- --reporter dot && nyc report",
        "test:watch": "npm run test -- --watch"
    },
    "version": "0.7.4",
    "bin": {}
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
