# api documentation for  [node-xlsx (v0.7.4)](https://github.com/mgcrea/node-xlsx#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-node-xlsx.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-node-xlsx) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-node-xlsx.svg)](https://travis-ci.org/npmdoc/node-npmdoc-node-xlsx)
#### NodeJS Excel files parser & builder

[![NPM](https://nodei.co/npm/node-xlsx.png?downloads=true)](https://www.npmjs.com/package/node-xlsx)

[![apidoc](https://npmdoc.github.io/node-npmdoc-node-xlsx/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-node-xlsx_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-node-xlsx/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-node-xlsx/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-node-xlsx/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Olivier Louvignes",
        "email": "olivier@mg-crea.com"
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
            "name": "mgcrea",
            "email": "olivier@mg-crea.com"
        }
    ],
    "name": "node-xlsx",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
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
    "version": "0.7.4"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module node-xlsx](#apidoc.module.node-xlsx)
1.  [function <span class="apidocSignatureSpan">node-xlsx.</span>build (worksheets)](#apidoc.element.node-xlsx.build)
1.  [function <span class="apidocSignatureSpan">node-xlsx.</span>parse (mixed)](#apidoc.element.node-xlsx.parse)
1.  object <span class="apidocSignatureSpan">node-xlsx.</span>default
1.  object <span class="apidocSignatureSpan">node-xlsx.</span>helpers
1.  object <span class="apidocSignatureSpan">node-xlsx.</span>workbook

#### [module node-xlsx.default](#apidoc.module.node-xlsx.default)
1.  [function <span class="apidocSignatureSpan">node-xlsx.default.</span>build (worksheets)](#apidoc.element.node-xlsx.default.build)
1.  [function <span class="apidocSignatureSpan">node-xlsx.default.</span>parse (mixed)](#apidoc.element.node-xlsx.default.parse)

#### [module node-xlsx.helpers](#apidoc.module.node-xlsx.helpers)
1.  [function <span class="apidocSignatureSpan">node-xlsx.helpers.</span>buildSheetFromMatrix (data)](#apidoc.element.node-xlsx.helpers.buildSheetFromMatrix)
1.  [function <span class="apidocSignatureSpan">node-xlsx.helpers.</span>isBoolean (maybeBoolean)](#apidoc.element.node-xlsx.helpers.isBoolean)
1.  [function <span class="apidocSignatureSpan">node-xlsx.helpers.</span>isNumber (maybeNumber)](#apidoc.element.node-xlsx.helpers.isNumber)
1.  [function <span class="apidocSignatureSpan">node-xlsx.helpers.</span>isString (maybeString)](#apidoc.element.node-xlsx.helpers.isString)

#### [module node-xlsx.workbook](#apidoc.module.node-xlsx.workbook)
1.  [function <span class="apidocSignatureSpan">node-xlsx.workbook.</span>default ()](#apidoc.element.node-xlsx.workbook.default)



# <a name="apidoc.module.node-xlsx"></a>[module node-xlsx](#apidoc.module.node-xlsx)

#### <a name="apidoc.element.node-xlsx.build"></a>[function <span class="apidocSignatureSpan">node-xlsx.</span>build (worksheets)](#apidoc.element.node-xlsx.build)
- description and source-code
```javascript
function build(worksheets) {
  var options = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : {};

  var defaults = {
    bookType: 'xlsx',
    bookSST: false,
    type: 'binary'
  };
  var workBook = new _workbook2.default();
  worksheets.forEach(function (worksheet) {
    var name = worksheet.name || 'Sheet';
    var data = (0, _helpers.buildSheetFromMatrix)(worksheet.data || [], options);
    workBook.SheetNames.push(name);
    workBook.Sheets[name] = data;
  });
  var excelData = _xlsx2.default.write(workBook, Object.assign({}, defaults, options));
  return excelData instanceof Buffer ? excelData : new Buffer(excelData, 'binary');
}
```
- example usage
```shell
...
1. Building a xlsx

'''js
import xlsx from 'node-xlsx';
// Or var xlsx = require('node-xlsx').default;

const data = [[1, 2, 3], [true, false, null, 'sheetjs'], ['foo', 'bar', new Date('2014-02-19T14:30Z'), '0.3'], ['baz', null, 'qux
']];
var buffer = xlsx.build([{name: "mySheetName", data: data}]); // Returns a buffer
'''


### Contributing

Please submit all pull requests the against master branch. If your unit test contains javascript patches or features, you should
 include relevant unit tests. Thanks!
...
```

#### <a name="apidoc.element.node-xlsx.parse"></a>[function <span class="apidocSignatureSpan">node-xlsx.</span>parse (mixed)](#apidoc.element.node-xlsx.parse)
- description and source-code
```javascript
function parse(mixed) {
  var options = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : {};

  var workSheet = _xlsx2.default[(0, _helpers.isString)(mixed) ? 'readFile' : 'read'](mixed, options);
  return Object.keys(workSheet.Sheets).map(function (name) {
    var sheet = workSheet.Sheets[name];
    return { name: name, data: _xlsx2.default.utils.sheet_to_json(sheet, { header: 1, raw: true }) };
  });
}
```
- example usage
```shell
...
1. Parsing a xlsx from file/buffer, outputs an array of worksheets

'''js
import xlsx from 'node-xlsx';
// Or var xlsx = require('node-xlsx').default;

// Parse a buffer
const workSheetsFromBuffer = xlsx.parse(fs.readFileSync('${__dirname}/myFile.xlsx'));
// Parse a file
const workSheetsFromFile = xlsx.parse('${__dirname}/myFile.xlsx');
'''

1. Building a xlsx

'''js
...
```



# <a name="apidoc.module.node-xlsx.default"></a>[module node-xlsx.default](#apidoc.module.node-xlsx.default)

#### <a name="apidoc.element.node-xlsx.default.build"></a>[function <span class="apidocSignatureSpan">node-xlsx.default.</span>build (worksheets)](#apidoc.element.node-xlsx.default.build)
- description and source-code
```javascript
function build(worksheets) {
  var options = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : {};

  var defaults = {
    bookType: 'xlsx',
    bookSST: false,
    type: 'binary'
  };
  var workBook = new _workbook2.default();
  worksheets.forEach(function (worksheet) {
    var name = worksheet.name || 'Sheet';
    var data = (0, _helpers.buildSheetFromMatrix)(worksheet.data || [], options);
    workBook.SheetNames.push(name);
    workBook.Sheets[name] = data;
  });
  var excelData = _xlsx2.default.write(workBook, Object.assign({}, defaults, options));
  return excelData instanceof Buffer ? excelData : new Buffer(excelData, 'binary');
}
```
- example usage
```shell
...
1. Building a xlsx

'''js
import xlsx from 'node-xlsx';
// Or var xlsx = require('node-xlsx').default;

const data = [[1, 2, 3], [true, false, null, 'sheetjs'], ['foo', 'bar', new Date('2014-02-19T14:30Z'), '0.3'], ['baz', null, 'qux
']];
var buffer = xlsx.build([{name: "mySheetName", data: data}]); // Returns a buffer
'''


### Contributing

Please submit all pull requests the against master branch. If your unit test contains javascript patches or features, you should
 include relevant unit tests. Thanks!
...
```

#### <a name="apidoc.element.node-xlsx.default.parse"></a>[function <span class="apidocSignatureSpan">node-xlsx.default.</span>parse (mixed)](#apidoc.element.node-xlsx.default.parse)
- description and source-code
```javascript
function parse(mixed) {
  var options = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : {};

  var workSheet = _xlsx2.default[(0, _helpers.isString)(mixed) ? 'readFile' : 'read'](mixed, options);
  return Object.keys(workSheet.Sheets).map(function (name) {
    var sheet = workSheet.Sheets[name];
    return { name: name, data: _xlsx2.default.utils.sheet_to_json(sheet, { header: 1, raw: true }) };
  });
}
```
- example usage
```shell
...
1. Parsing a xlsx from file/buffer, outputs an array of worksheets

'''js
import xlsx from 'node-xlsx';
// Or var xlsx = require('node-xlsx').default;

// Parse a buffer
const workSheetsFromBuffer = xlsx.parse(fs.readFileSync('${__dirname}/myFile.xlsx'));
// Parse a file
const workSheetsFromFile = xlsx.parse('${__dirname}/myFile.xlsx');
'''

1. Building a xlsx

'''js
...
```



# <a name="apidoc.module.node-xlsx.helpers"></a>[module node-xlsx.helpers](#apidoc.module.node-xlsx.helpers)

#### <a name="apidoc.element.node-xlsx.helpers.buildSheetFromMatrix"></a>[function <span class="apidocSignatureSpan">node-xlsx.helpers.</span>buildSheetFromMatrix (data)](#apidoc.element.node-xlsx.helpers.buildSheetFromMatrix)
- description and source-code
```javascript
function buildSheetFromMatrix(data) {
  var options = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : {};

  var workSheet = {};
  var range = { s: { c: 1e7, r: 1e7 }, e: { c: 0, r: 0 } };
  for (var R = 0; R !== data.length; ++R) {
    for (var C = 0; C !== data[R].length; ++C) {
      if (range.s.r > R) range.s.r = R;
      if (range.s.c > C) range.s.c = C;
      if (range.e.r < R) range.e.r = R;
      if (range.e.c < C) range.e.c = C;
      if (data[R][C] === null) {
        continue; // eslint-disable-line
      }
      var cell = { v: data[R][C] };
      var cellRef = _xlsx2.default.utils.encode_cell({ c: C, r: R });
      if (isNumber(cell.v)) {
        cell.t = 'n';
      } else if (isBoolean(cell.v)) {
        cell.t = 'b';
      } else if (cell.v instanceof Date) {
        cell.t = 'n';
        cell.v = buildExcelDate(cell.v);
        cell.z = _xlsx2.default.SSF._table[14]; // eslint-disable-line no-underscore-dangle
      } else {
        cell.t = 's';
      }
      workSheet[cellRef] = cell;
    }
  }
  if (range.s.c < 1e7) {
    workSheet['!ref'] = _xlsx2.default.utils.encode_range(range);
  }
  if (options['!cols']) {
    workSheet['!cols'] = options['!cols'];
  }
  if (options['!merges']) {
    workSheet['!merges'] = options['!merges'];
  }
  return workSheet;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.node-xlsx.helpers.isBoolean"></a>[function <span class="apidocSignatureSpan">node-xlsx.helpers.</span>isBoolean (maybeBoolean)](#apidoc.element.node-xlsx.helpers.isBoolean)
- description and source-code
```javascript
function isBoolean(maybeBoolean) {
  return typeof maybeBoolean === 'boolean';
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.node-xlsx.helpers.isNumber"></a>[function <span class="apidocSignatureSpan">node-xlsx.helpers.</span>isNumber (maybeNumber)](#apidoc.element.node-xlsx.helpers.isNumber)
- description and source-code
```javascript
function isNumber(maybeNumber) {
  return typeof maybeNumber === 'number';
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.node-xlsx.helpers.isString"></a>[function <span class="apidocSignatureSpan">node-xlsx.helpers.</span>isString (maybeString)](#apidoc.element.node-xlsx.helpers.isString)
- description and source-code
```javascript
function isString(maybeString) {
  return typeof maybeString === 'string';
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.node-xlsx.workbook"></a>[module node-xlsx.workbook](#apidoc.module.node-xlsx.workbook)

#### <a name="apidoc.element.node-xlsx.workbook.default"></a>[function <span class="apidocSignatureSpan">node-xlsx.workbook.</span>default ()](#apidoc.element.node-xlsx.workbook.default)
- description and source-code
```javascript
function Workbook() {
  _classCallCheck(this, Workbook);

  this.SheetNames = [];
  this.Sheets = {};
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
