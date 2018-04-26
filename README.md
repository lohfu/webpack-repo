# webpack-repo

The file `./src/index.js` imports named exports from the `lowline` package using the following line:

```js
import { merge, isPlainObject } from 'lowline'
```

This works fine. However, webpack errors when the the file `rek/es/factory.mjs` in the `rek` module tries to import exactly the same named exports in exactly
the same way. It appears that when importing lowline from rek, webpack is suddenly prefering the `main` field from lowlines package.json.

To run the build

```sh
$ npm run webpack
```

The build will fail. If the import rek line is removed from `./src/index.js` the build succeeds.
