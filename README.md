## Description

Enables various features from the ImpactJS HTML5 framework in Node.js to enable code
sharing and re-use between the client and server side. The features that are emulated are:

The features that are emulated or re-created are:

* The Module syste
* The Class system
* The Native type extensions

## Use Cases

* Server authoritative multiplayer games
* High score validation - record inputs from the game, send over to server after level is done, server can then
replay using the same logic and code on server
* Use game data or game structures in your webapp

## Usage

Enable the class system:

```javascript
require("node-impact-emu").useClass();
```

Enable the module system:

```javascript
// Note: Must pass in the root class path folder. This can be the same lib folder that
// contains your client-side modules
require("node-impact-emu").useModule(__dirname + '/lib');
```

Enable the native type extensions:

```javascript
require("node-impact-emu").useNative();
```


You can also enable more than one system at a time by chaining:

```javascript
require("node-impact-emu").useNative().useClass();
```

Or you can enable everything:

```javascript
require("node-impact-emu").useAll(__dirname + '/lib'); // Also requires class path folder
```

## Disclaimer

Enabling these features diverges from typical Node.js development practices. The global namespace is modified,
and modules are no longer entirely self-contained. Use at your own risk.