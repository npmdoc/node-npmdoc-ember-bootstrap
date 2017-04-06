# api documentation for  [ember-bootstrap (v0.11.3)](http://kaliber5.github.io/ember-bootstrap/)  [![npm package](https://img.shields.io/npm/v/npmdoc-ember-bootstrap.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-ember-bootstrap) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-ember-bootstrap.svg)](https://travis-ci.org/npmdoc/node-npmdoc-ember-bootstrap)
#### Twitter Bootstrap components for Ember.js

[![NPM](https://nodei.co/npm/ember-bootstrap.png?downloads=true)](https://www.npmjs.com/package/ember-bootstrap)

[![apidoc](https://npmdoc.github.io/node-npmdoc-ember-bootstrap/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-ember-bootstrap_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-ember-bootstrap/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-ember-bootstrap/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-ember-bootstrap/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Simon Ihmig",
        "email": "ihmig@kaliber5.de"
    },
    "bugs": {
        "url": "https://github.com/kaliber5/ember-bootstrap/issues"
    },
    "dependencies": {
        "broccoli-funnel": "^1.0.1",
        "broccoli-merge-trees": "^1.1.1",
        "ember-cli-babel": "^5.1.6",
        "ember-cli-htmlbars": "^1.1.0",
        "ember-runtime-enumerable-includes-polyfill": "^1.0.1",
        "ember-wormhole": "^0.4.1"
    },
    "description": "Twitter Bootstrap components for Ember.js",
    "devDependencies": {
        "broccoli-asset-rev": "^2.4.2",
        "chai": "^3.5.0",
        "conventional-changelog": "0.0.17",
        "ember-ajax": "^2.0.1",
        "ember-cli": "2.8.0",
        "ember-cli-app-version": "^1.0.0",
        "ember-cli-dependency-checker": "^1.2.0",
        "ember-cli-fastboot": "1.0.0-beta.9",
        "ember-cli-htmlbars-inline-precompile": "^0.3.5",
        "ember-cli-inject-live-reload": "^1.4.0",
        "ember-cli-jshint": "^1.0.0",
        "ember-cli-less": "1.5.3",
        "ember-cli-qunit": "^2.1.0",
        "ember-cli-release": "^0.2.9",
        "ember-cli-sri": "^2.1.0",
        "ember-cli-test-loader": "^1.1.0",
        "ember-cli-uglify": "^1.2.0",
        "ember-cli-yuidoc": "^0.8.7",
        "ember-disable-prototype-extensions": "^1.1.0",
        "ember-export-application-global": "^1.0.5",
        "ember-fastboot-addon-tests": "^0.1.0",
        "ember-load-initializers": "^0.5.1",
        "ember-resolver": "^2.0.3",
        "ember-sinon": "0.5.1",
        "ember-sinon-qunit": "1.3.4",
        "ember-suave": "4.0.0",
        "gh-pages": "^0.3.1",
        "glob": "^5.0.14",
        "gulp": "^3.9.0",
        "gulp-file": "^0.2.0",
        "gulp-rename": "^1.2.2",
        "gulp-transform": "^1.0.8",
        "loader.js": "^4.0.1",
        "rsvp": "^3.2.1",
        "striptags": "^2.1.1"
    },
    "directories": {
        "doc": "docs",
        "test": "tests"
    },
    "dist": {
        "shasum": "810d9e7202cfb5439d731360589a62144087e96c",
        "tarball": "https://registry.npmjs.org/ember-bootstrap/-/ember-bootstrap-0.11.3.tgz"
    },
    "ember-addon": {
        "configPath": "tests/dummy/config",
        "versionCompatibility": {
            "ember": ">=1.13.0"
        }
    },
    "engines": {
        "node": ">= 0.10.0"
    },
    "gitHead": "0ce8872d888e47b9583af8e8a8b8d0b0c4bcaac8",
    "homepage": "http://kaliber5.github.io/ember-bootstrap/",
    "keywords": [
        "ember-addon",
        "bootstrap"
    ],
    "license": "MIT",
    "maintainers": [
        {
            "name": "simonihmig",
            "email": "ihmig@kaliber5.de"
        }
    ],
    "name": "ember-bootstrap",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/kaliber5/ember-bootstrap.git"
    },
    "scripts": {
        "build": "ember build",
        "start": "ember server",
        "test": "ember try:each && ember fastboot:test"
    },
    "version": "0.11.3"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module ember-bootstrap](#apidoc.module.ember-bootstrap)
1.  [function <span class="apidocSignatureSpan">ember-bootstrap.</span>included (app)](#apidoc.element.ember-bootstrap.included)
1.  [function <span class="apidocSignatureSpan">ember-bootstrap.</span>treeForStyles (tree)](#apidoc.element.ember-bootstrap.treeForStyles)
1.  string <span class="apidocSignatureSpan">ember-bootstrap.</span>name



# <a name="apidoc.module.ember-bootstrap"></a>[module ember-bootstrap](#apidoc.module.ember-bootstrap)

#### <a name="apidoc.element.ember-bootstrap.included"></a>[function <span class="apidocSignatureSpan">ember-bootstrap.</span>included (app)](#apidoc.element.ember-bootstrap.included)
- description and source-code
```javascript
function included(app) {
  // workaround for https://github.com/ember-cli/ember-cli/issues/3718
  if (typeof app.import !== 'function' && app.app) {
    app = app.app;
  }
  this.app = app;

  var options = extend(defaultOptions, app.options['ember-bootstrap']);
  var bootstrapPath = path.join(app.bowerDirectory, 'bootstrap/dist');

  // Import css from bootstrap
  if (options.importBootstrapCSS) {
    app.import(path.join(bootstrapPath, 'css/bootstrap.css'));
    app.import(path.join(bootstrapPath, 'css/bootstrap.css.map'), {destDir: 'assets'});
  }

  if (options.importBootstrapTheme) {
    app.import(path.join(bootstrapPath, 'css/bootstrap-theme.css'));
    app.import(path.join(bootstrapPath, 'css/bootstrap-theme.css.map'), {destDir: 'assets'});
  }

  // Import glyphicons
  if (options.importBootstrapFont) {
    app.import(path.join(bootstrapPath, 'fonts/glyphicons-halflings-regular.eot'), {destDir: '/fonts'});
    app.import(path.join(bootstrapPath, 'fonts/glyphicons-halflings-regular.svg'), {destDir: '/fonts'});
    app.import(path.join(bootstrapPath, 'fonts/glyphicons-halflings-regular.ttf'), {destDir: '/fonts'});
    app.import(path.join(bootstrapPath, 'fonts/glyphicons-halflings-regular.woff'), {destDir: '/fonts'});
    app.import(path.join(bootstrapPath, 'fonts/glyphicons-halflings-regular.woff2'), {destDir: '/fonts'});
  }

  if (!process.env.EMBER_CLI_FASTBOOT) {
    app.import('vendor/transition.js');
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.ember-bootstrap.treeForStyles"></a>[function <span class="apidocSignatureSpan">ember-bootstrap.</span>treeForStyles (tree)](#apidoc.element.ember-bootstrap.treeForStyles)
- description and source-code
```javascript
function treeForStyles(tree) {
  var styleTrees = [];

  if (this.app.project.findAddonByName('ember-cli-less')) {
    var lessTree = new Funnel(path.join(this.app.bowerDirectory, 'bootstrap/less'), {
      destDir: 'ember-bootstrap'
    });
    styleTrees.push(lessTree);
  }

  if (tree) {
    styleTrees.push(tree);
  }

  return mergeTrees(styleTrees, { overwrite: true });
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
