# kitsune-jsdoc-template

[![CircleCI](https://circleci.com/gh/mere/kitsune-jsdoc-template.svg?style=svg&circle-token=2b25198a8e03dee1c5fdcd430d465a03d63fc958)](https://circleci.com/gh/mere/kitsune-jsdoc-template)
[![npm version](https://badge.fury.io/js/kitsune-jsdoc-template.svg)](https://badge.fury.io/js/kitsune-jsdoc-template)
  
Fully customisable `jsdoc3` template, based on `nijikokun/minami`

## Dependencies

- [the Taffy Database library](http://taffydb.com/)
- [lodash Template library](https://www.npmjs.com/package/lodash.template)

## How to use

```bash
$ npm install --save-dev kitsune-jsdoc-template
```

### Example JSDoc Config

> Note: properties prefixed with _ (underscore) are automatically ignored

```js
{
  "tags": {
    "allowUnknownTags": true,
    "dictionaries": ["jsdoc"]
  },
  "source": {
    "include": ["src", "README.md"],
    "includePattern": ".+\\.(js|jsx)?$",
    "excludePattern": "(^|\\/|\\\\)_"
  },
  "plugins": [
    "plugins/markdown"
  ],
  "markdown": {
		"parser": "gfm",
		"hardwrap": true,
		"excludeTags": []
	},
  "templates": {
    "cleverLinks": true,
    "monospaceLinks": true,
    "useLongnameInNav": true,
    "applicationName": "nflow",
    "openGraph": {
      "title": "XYZ Documentation",
      "type": "website",
      "image": "logo.svg",
      "site_name": "XYZ API Docs",
      "url": ""
    },
    "meta": {
      "title": "",
      "description": "",
      "keyword": ""
    },
    "linenums": true,
    "default":{
      "outputSourceFiles" : true,
      "cssFiles":{
        "include":[
          "my-custom-styles.css"
        ],
        "_exclude":[
          "styles/jsdoc-default.css"
        ]
      },
      "_jsFiles":{
        "include":[
          "my-library.js"
        ],
        "_exclude":["scripts/prettify/lang-css.js"]
      },
      "_templateFiles":{
        "example":"src-docs/tmpl/my-custom-example.tmpl"
      },
      "staticFiles":{
        "_include": [
          "./src-docs/assets",
          "./node_modules/some-library"
        ]
      },
      "_i18nFile": "src-docs/tmpl/i18n.json",
      "theme":"github",
      "paramsDisplay":"compact"
    }
  },
  "opts": {
    "_template": "./node_modules/kitsune-jsdoc-template",
    "template": "../kitsune-jsdoc-template",
    "encoding": "utf8",
    "destination": "./docs/",
    "private": true,
    "recurse": true,
    "tutorials": "./src-docs/tutorials"
  }
}

```

## License

Licensed under the Apache2 license.
