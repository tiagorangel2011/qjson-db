<img src="https://user-images.githubusercontent.com/70700766/196008415-77fb1306-c178-4d7b-88fb-a0888d926171.png" width="300" alt="qjson-db: Dead simple JSON database">

***

A simplified and improved version of [nmaggioni/Simple-JSONdb](https://github.com/nmaggioni/Simple-JSONdb): a dead simple JSON database for your web app.

**Install:**: `npm i qjson-db` or `bun add qjson-db` if you're feeling extra fancy.
**Requirements:** Node >= 10.0
**Note:** If you want a database with more features (e.g. math, etc.) but less support for older versions of Node, I highly recommend you looking at [jsoning](https://github.com/khalby786/jsoning) by [@khalby786](https://github.com/khalby786)

## Usage

Start your database:

```javascript
const qjson = require('qjson-db');
const db = new qjson('/path/to/your/storage.json');
```

> **Note:** if you're using Glitch, you can store your db in the `.data` folder to keep it safe from other people viewing it. It will also not be included in remixes.

Then, you can use the functions:

### Set a key
`db.set('key', 'value');`

The `key` parameter must be a string, `value` can be whatever kind of object can be stored in JSON format.

### Read a key
`db.get('key');`

The `key` parameter must be a string. If the key exists its value is returned, if it doesn't the function returns `undefined`.

### Check a key
`db.has('key');`

The `key` parameter must be a string. If the key exists `true` is returned, if it doesn't the function returns `false`.

### Delete a key

`db.delete('key');`

The `key` parameter must be a string. The function returns [as per the _delete_ operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete#Return_value) if the key exists, else it returns `undefined`.

### Read JSON storage
`db.JSON();`

This will return a copy of the internal JSON storage object.

### Replace JSON storage
`db.JSON({ data });`

Giving a parameter to the `JSON` function makes the object passed to replace the internal one. _Be careful, as there's no way to recover the old object._
