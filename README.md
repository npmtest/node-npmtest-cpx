# npmtest-cpx

#### basic test coverage for  [cpx (v1.5.0)](https://github.com/mysticatea/cpx)  [![npm package](https://img.shields.io/npm/v/npmtest-cpx.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-cpx) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-cpx.svg)](https://travis-ci.org/npmtest/node-npmtest-cpx)

#### Copy file globs, watching for changes.

[![NPM](https://nodei.co/npm/cpx.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/cpx)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-cpx/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-cpx/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-cpx/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-cpx/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-cpx/build/test-report.html)|
| build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-cpx/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-cpx/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-cpx/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-cpx/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-cpx/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-cpx/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-cpx/build/test-report.html](https://npmtest.github.io/node-npmtest-cpx/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-cpx/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-cpx/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-cpx/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-cpx/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-cpx/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-cpx/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-cpx/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-cpx/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "cpx",
    "version": "1.5.0",
    "description": "Copy file globs, watching for changes.",
    "main": "lib/index.js",
    "bin": {
        "cpx": "bin/index.js"
    },
    "files": [
        "bin",
        "lib"
    ],
    "scripts": {
        "preversion": "run-s test build",
        "postversion": "git push && git push --tags",
        "clean": "rimraf .nyc_output bin coverage lib test-ws",
        "lint": "if-node-version \">=4\" eslint src",
        "prebuild": "npm run clean",
        "build": "cross-env NODE_ENV=production babel src --out-dir .",
        "pretest": "run-s clean lint",
        "test": "cross-env NODE_ENV=development nyc --require babel-register mocha test/*.js --timeout 60000",
        "prewatch": "run-s clean lint",
        "watch": "cross-env NODE_ENV=development mocha test/*.js --compilers js:babel-register --timeout 60000 --watch --growl",
        "open-coverage": "nyc report -r lcov && opener coverage/lcov-report/index.html",
        "codecov": "nyc report -r lcovonly && codecov"
    },
    "dependencies": {
        "babel-runtime": "^6.9.2",
        "chokidar": "^1.6.0",
        "duplexer": "^0.1.1",
        "glob": "^7.0.5",
        "glob2base": "^0.0.12",
        "minimatch": "^3.0.2",
        "mkdirp": "^0.5.1",
        "resolve": "^1.1.7",
        "safe-buffer": "^5.0.1",
        "shell-quote": "^1.6.1",
        "subarg": "^1.0.0"
    },
    "devDependencies": {
        "babel-cli": "^6.11.4",
        "babel-plugin-transform-runtime": "^6.9.0",
        "babel-plugin-unassert": "^2.1.1",
        "babel-preset-es2015": "^6.9.0",
        "babel-preset-power-assert": "^1.0.0",
        "babel-register": "^6.9.0",
        "codecov": "^1.0.1",
        "cross-env": "^2.0.0",
        "eslint": "^3.4.0",
        "eslint-config-mysticatea": "^6.0.0",
        "if-node-version": "^1.0.0",
        "mocha": "^3.0.2",
        "npm-run-all": "^3.1.0",
        "nyc": "^8.1.0",
        "opener": "^1.4.1",
        "power-assert": "^1.4.1",
        "rimraf": "^2.5.3",
        "shelljs": "^0.7.0",
        "through": "^2.3.8"
    },
    "repository": {
        "type": "git",
        "url": "https://github.com/mysticatea/cpx.git"
    },
    "keywords": [
        "cp",
        "cli",
        "tool",
        "commandline",
        "sync",
        "rsync",
        "watch",
        "observe",
        "copy",
        "dir",
        "directory",
        "directories",
        "file",
        "files"
    ],
    "author": "Toru Nagashima",
    "license": "MIT",
    "bugs": {
        "url": "https://github.com/mysticatea/cpx/issues"
    },
    "homepage": "https://github.com/mysticatea/cpx"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
