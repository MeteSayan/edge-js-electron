# .NET and Node.js in-process on Electron

***
### [agracio](https://github.com/agracio) has resumed updating the [electron-edge-js](https://github.com/agracio/electron-edge-js) project. I am continuing to make new updates in the electron-edge-js repository. This repository is now deprecated.
***

This is a fork of [electron-edge-js](https://github.com/agracio/electron-edge-js) adapted to support the ~~newest [Electron](https://github.com/electron/electron/) versions~~. This repository was created because the previous repository did not support new electron versions and the maintainer was not actively making new developments.

- Thanks to [Tomasz Janczuk](https://github.com/tjanczuk) for [Edge.js](https://github.com/tjanczuk/edge).
- Thanks to [agracio](https://github.com/agracio) for [electron-edge-js](https://github.com/agracio/electron-edge-js).

Compatible with

- Electron 12.x - Node.js v14.16.0
- Electron 13.x - Node.js v14.16.0
- ~~Electron 14.x - Node.js v14.17.0~~
- Electron 15.x - Node.js v16.5.0
- Electron 16.x - Node.js v16.9.1
- Electron 17.x - Node.js v16.13.0
- Electron 18.x - Node.js v16.13.2
- Electron 19.x - Node.js v16.14.2
- Electron 20.x - Node.js v16.15.0
- Electron 21.x - Node.js v16.16.0
- Electron 22.x - Node.js v16.17.1
- Electron 23.x - Node.js v18.12.1
- Electron 24.x - Node.js v18.14.0
- Electron 25.x - Node.js v18.15.0
- Electron 26.x - Node.js v18.16.1
- Electron 27.x - Node.js v18.17.1

Usage is the same as edge or edge-js, replace `require('electron-edge-js')` with `require('edge-js-electron')`:

```bash
npm install edge-js-electron
```

```diff
-var edge = require('electron-edge-js');
+var edge = require('edge-js-electron');

var helloWorld = edge.func(function () {/*
    async (input) => {
        return ".NET Welcomes " + input.ToString();
    }
*/});
```

## Requirements (Windows)

You must install [Microsoft Visual C++ Redistributable (x86)](https://www.microsoft.com/en-us/download/details.aspx?id=52685)

## Why use `electron-edge-js`?

Electron is built using specific version of Node.js. In order to use `edge` in Electron project you would need to recompile it using the same Node.js version and Electron headers.

`electron-edge-js` comes precompiled with correct Node.js versions and headers.

## Quick start

Simple app that shows how to work with .NET Core using compiled C# libraries.  
<https://github.com/agracio/electron-edge-js-quick-start>

## MacOS

`edge-js` and `electron-edge-js` will fail to build on MacOS if Visual Studion for mac is installed.
VS installs Mono runtimes that `edge-js` fails to access durring `nmp install`.

## Packaging Electron application

Packaging example based on the app above.  
<https://github.com/zenb/electron-edge-js-quick-start>

Related issues to use for troubleshooting:  
<https://github.com/agracio/electron-edge-js/issues/39>  
<https://github.com/agracio/electron-edge-js/issues/74>  
<https://github.com/agracio/electron-edge-js/issues/21>

## Async execution

Underlying 'edge' component is written as synchronous C++ Node.js module and will cause Electron app to freeze when executing long running .NET code.  
For workaround refer to this issue: <https://github.com/agracio/electron-edge-js/issues/97>

## Documentation

For full documentation please see see original [edge-js](https://github.com/agracio/edge-js) repo.

## Build

Build.bat supports only Electron major versions.
