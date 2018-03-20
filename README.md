# querystringme
Library to process querystring parameters

1. Install 

```
npm install querystringme
```

2. Usage

```
var querquerystringmeyme = require('querystringme');

// You can load inital parameters with load()
querystringme.load({
    local_storage: true
});

querystringme.getParameters();
querystringme.getParameter('foo', { force: true });
querystringme.updateParameters({ foo: 'bar', other: 'boo' }, { local_storage: true });
```

3. Run tests

```
npm start // or node server.js
npm test
```

4. Options

All methods receive at least one optional object that can have the following options:
* force: boolean. When true parses URL every time instead of using stored values. Default: false.
* update_url: boolean. When true updates browser's URL after each parameter change. Default: true.
* local_storage: boolean. When true uses localStorage to store parameters and to restore them when the page is loaded. URL parameters overwrite stored values. Default: false.
* default_values: object. Key-value object to specify default values. Those values are overwritten by browser's URL. If these values are not present in URL they are added. Default: {}.

5. List of methods

* load(options): overwrites default options. Process URL and localStorage parameters and updates the browser URL. The parameter *options* is optional.
* getParameters(options): Return all the processed parameters after processing browser URL and localStorage. Browser's URL parameters overwrite localStorage ones. The parameter *options* is optional.
* getParameter(key, options): Returns the parameter with name *key*. The parameter *options* is optional.
* updateParameters(values, options): Receives an object with the parameters to update and sets those values. It updates the browser's URL and localStorage when enabled. The parameter *options* is optional.