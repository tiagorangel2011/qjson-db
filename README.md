<img src="https://user-images.githubusercontent.com/70700766/196008415-77fb1306-c178-4d7b-88fb-a0888d926171.png" width="300" alt="qjson-db: Dead simple JSON database">

***

A fork of [nmaggioni/Simple-JSONdb](https://github.com/nmaggioni/Simple-JSONdb), this is a dead simple JSON database for your web app. Check out the demo at [qjsondb-demo.glitch.me](https://glitch.com/~qjsondb-demo)

**Install:** `npm i qjson-db`

[![Tests tests](https://github.com/tiagorangel2011/qjson-db/actions/workflows/ci.yml/badge.svg)](https://github.com/tiagorangel2011/qjson-db/actions/workflows/ci.yml) [![Known Vulnerabilities](https://snyk.io/test/github/tiagorangel2011/qjson-db/badge.svg)](https://snyk.io/test/github/tiagorangel2011/qjson-db)
## Usage

Start by creating your database:

```javascript
const qjson = require('qjson-db');
const db = new qjson('/path/to/your/storage.json');
```

Then, you can use the functions:

### Set a key
`db.set('key', 'value');`

The `key` parameter must be a string, `value` can be whatever kind of object can be stored in JSON format.

### Get a key
`db.get('key');`

The `key` parameter must be a string. If the key exists its value is returned, if it doesn't the function returns `undefined`.

### Check a key
`db.has('key');`

The `key` parameter must be a string. If the key exists `true` is returned, if it doesn't the function returns `false`.

### Delete a key

`db.delete('key');`

The `key` parameter must be a string. The function returns [as per the _delete_ operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete#Return_value) if the key exists, else it returns `undefined`.

### Access JSON storage
`db.JSON();`

This will return a copy of the internal JSON storage object.

### Replace JSON storage
`db.JSON({ data });`

Giving a parameter to the `JSON` function makes the object passed replace the internal one. _Be careful, as there's no way to recover the old object if the changes have already been written to disk._