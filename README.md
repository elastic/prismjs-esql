# Prism.js and `refractor` ES|QL grammar

This package contains the ES|QL grammar for Prism.js and `refractor`.

Usage:

```js
import {register} from 'refractor';
import {esql} from '@elastic/prismjs-esql';

register(esql)
```

## Run test and build steps

```
yarn test
yarn format
yarn lint
yarn build
```

## Releasing
See [CONTRIBUTING.md](./CONTRIBUTING.md)


## License

MIT
