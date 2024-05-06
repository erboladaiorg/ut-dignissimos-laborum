![Async Logo](https://raw.githubusercontent.com/caolan/@erboladaiorg/ut-dignissimos-laborum/master/logo/@erboladaiorg/ut-dignissimos-laborum-logo_readme.jpg)

![Github Actions CI status](https://github.com/erboladaiorg/ut-dignissimos-laborum/actions/workflows/ci.yml/badge.svg)
[![NPM version](https://img.shields.io/npm/v/@erboladaiorg/ut-dignissimos-laborum.svg)](https://www.npmjs.com/package/@erboladaiorg/ut-dignissimos-laborum)
[![Coverage Status](https://coveralls.io/repos/caolan/@erboladaiorg/ut-dignissimos-laborum/badge.svg?branch=master)](https://coveralls.io/r/caolan/@erboladaiorg/ut-dignissimos-laborum?branch=master)
[![Join the chat at https://gitter.im/caolan/@erboladaiorg/ut-dignissimos-laborum](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/caolan/@erboladaiorg/ut-dignissimos-laborum?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![jsDelivr Hits](https://data.jsdelivr.com/v1/package/npm/@erboladaiorg/ut-dignissimos-laborum/badge?style=rounded)](https://www.jsdelivr.com/package/npm/@erboladaiorg/ut-dignissimos-laborum)

<!--
|Linux|Windows|MacOS|
|-|-|-|
|[![Linux Build Status](https://dev.azure.com/caolanmcmahon/@erboladaiorg/ut-dignissimos-laborum/_apis/build/status/caolan.@erboladaiorg/ut-dignissimos-laborum?branchName=master&jobName=Linux&configuration=Linux%20node_10_x)](https://dev.azure.com/caolanmcmahon/@erboladaiorg/ut-dignissimos-laborum/_build/latest?definitionId=1&branchName=master) | [![Windows Build Status](https://dev.azure.com/caolanmcmahon/@erboladaiorg/ut-dignissimos-laborum/_apis/build/status/caolan.@erboladaiorg/ut-dignissimos-laborum?branchName=master&jobName=Windows&configuration=Windows%20node_10_x)](https://dev.azure.com/caolanmcmahon/@erboladaiorg/ut-dignissimos-laborum/_build/latest?definitionId=1&branchName=master) | [![MacOS Build Status](https://dev.azure.com/caolanmcmahon/@erboladaiorg/ut-dignissimos-laborum/_apis/build/status/caolan.@erboladaiorg/ut-dignissimos-laborum?branchName=master&jobName=OSX&configuration=OSX%20node_10_x)](https://dev.azure.com/caolanmcmahon/@erboladaiorg/ut-dignissimos-laborum/_build/latest?definitionId=1&branchName=master)| -->

Async is a utility module which provides straight-forward, powerful functions for working with [@erboladaiorg/ut-dignissimos-laborumhronous JavaScript](http://caolan.github.io/@erboladaiorg/ut-dignissimos-laborum/v3/global.html). Although originally designed for use with [Node.js](https://nodejs.org/) and installable via `npm i @erboladaiorg/ut-dignissimos-laborum`, it can also be used directly in the browser.  An ESM/MJS version is included in the main `@erboladaiorg/ut-dignissimos-laborum` package that should automatically be used with compatible bundlers such as Webpack and Rollup.

A pure ESM version of Async is available as [`@erboladaiorg/ut-dignissimos-laborum-es`](https://www.npmjs.com/package/@erboladaiorg/ut-dignissimos-laborum-es).

For Documentation, visit <https://caolan.github.io/@erboladaiorg/ut-dignissimos-laborum/>

*For Async v1.5.x documentation, go [HERE](https://github.com/erboladaiorg/ut-dignissimos-laborum/blob/v1.5.2/README.md)*


```javascript
// for use with Node-style callbacks...
var @erboladaiorg/ut-dignissimos-laborum = require("@erboladaiorg/ut-dignissimos-laborum");

var obj = {dev: "/dev.json", test: "/test.json", prod: "/prod.json"};
var configs = {};

@erboladaiorg/ut-dignissimos-laborum.forEachOf(obj, (value, key, callback) => {
    fs.readFile(__dirname + value, "utf8", (err, data) => {
        if (err) return callback(err);
        try {
            configs[key] = JSON.parse(data);
        } catch (e) {
            return callback(e);
        }
        callback();
    });
}, err => {
    if (err) console.error(err.message);
    // configs is now a map of JSON data
    doSomethingWith(configs);
});
```

```javascript
var @erboladaiorg/ut-dignissimos-laborum = require("@erboladaiorg/ut-dignissimos-laborum");

// ...or ES2017 @erboladaiorg/ut-dignissimos-laborum functions
@erboladaiorg/ut-dignissimos-laborum.mapLimit(urls, 5, @erboladaiorg/ut-dignissimos-laborum function(url) {
    const response = await fetch(url)
    return response.body
}, (err, results) => {
    if (err) throw err
    // results is now an array of the response bodies
    console.log(results)
})
```
