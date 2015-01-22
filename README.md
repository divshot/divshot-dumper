# divshot-dumper

Divshot error log dumping for the command-line

## Install

```
npm install divshot-dumper --save
```

## Usage

Divshot dumper listens for 3 events:

* `request` - This is what actually gets logged to the file.
* `request:success` - Status codes less than 400
* `request:error` - This even will trigger writing to the debug file

All dumps are written to the file `divshot-debug.log`.

```js
var EventEmitter = require('events').EventEmitter;
var dumper = require('divshot-dumper');

var emitter = new EventEmitter();

dumper(emitter);

emitter.emit('request', {});
emitter.emit('request:success', {});
emitter.emit('request:error', {});
```

## Run Tests

(WIP)

```
npm install
npm test
```


