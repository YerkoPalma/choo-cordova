# choo-cordova
[![Build Status](https://img.shields.io/travis/YerkoPalma/choo-cordova/master.svg?style=flat-square)](https://travis-ci.org/YerkoPalma/choo-cordova) [![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg?style=flat-square)](https://github.com/feross/standard)

> Choo hooks for the cordova API

## Usage

```js
var choo = require('choo')

var app = choo()

app.use(require('choo-cordova'))

app.route('/', require('./views/main'))
app.mount('#app')
```

## Events
This store emit events for every cordova events. Those events are:

- `'deviceready'`
- `'pause'`
- `'resume'`
- `'backbutton'`
- `'menubutton'`
- `'searchbutton'`
- `'startcallbutton'`
- `'endcallbutton'`
- `'volumedownbutton'`
- `'volumeupbutton'`
- `'activated'`

For further documentation about those, check [cordova docs](https://cordova.apache.org/docs/en/latest/cordova/events/events.html)

## API
After registering this store, a `cordova` property will be added to the store. This will have some of the cordova object properties. As the time of writing, this object looks like.

```js
JSON.stringify(choo.state.cordova, null, 2)
"{
  "version": "5.0.3",
  "platformVersion": "5.0.3",
  "platformId": "browser",
  "callbackId": 65806389,
  "callbacks": {},
  "callbackStatus": {
    "NO_RESULT": 0,
    "OK": 1,
    "CLASS_NOT_FOUND_EXCEPTION": 2,
    "ILLEGAL_ACCESS_EXCEPTION": 3,
    "INSTANTIATION_EXCEPTION": 4,
    "MALFORMED_URL_EXCEPTION": 5,
    "IO_EXCEPTION": 6,
    "INVALID_ACTION": 7,
    "JSON_EXCEPTION": 8,
    "ERROR": 9
  },
  "commandProxy": {}
}"
```

## License
[MIT](/license)
