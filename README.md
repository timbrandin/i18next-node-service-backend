# Introduction

This is a i18next backend to be used with node.js for external services such as [spacetranslate](http://spacetranslate.com) or [locize](http://locize.com) service. It's for the node.js server what the [i18next-service-backend](https://github.com/timbrandin/i18next-service-backend) is for the browser.

# Getting started

Source can be loaded via [npm](https://www.npmjs.com/package/i18next-node-service-backend).

```
$ npm install i18next-node-service-backend
```

Wiring up:

```js
var i18next = require('i18next');
var Backend = require('i18next-node-service-backend');

i18next
  .use(Backend)
  .init(i18nextOptions);
```

As with all modules you can either pass the constructor function (class) to the i18next.use or a concrete instance.

## Backend Options

```js
{
  // service url to the backend service
  // i.e. https://api.spacetranslate.com or https://api.locize.io
  service: '[SERVICE_URL]',

  // the id of your project
  projectId: '[PROJECTID]',

  // add an api key if you want to send missing keys
  apiKey: '[APIKEY]',

  // the reference language of your project
  referenceLng: '[LNG]',

  // version - defaults to latest
  version: '[VERSION]'
}
```

Options can be passed in:

**preferred** - by setting options.backend in i18next.init:

```js
var i18next = require('i18next');
var Backend = require('i18next-node-service-backend');

i18next
  .use(Backend)
  .init({
    backend: options
  });
```

on construction:

```js
var Backend = require('i18next-node-service-backend');
var backend = new Backend(null, options);
```

by calling init:

```js
var Backend = require('i18next-node-service-backend');
var backend = new Backend();
backend.init(null, options);
```
