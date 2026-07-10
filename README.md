# Prism.js and `refractor` ES|QL grammar

> [!IMPORTANT]
> This repository has moved. Development now happens in the
> [`elastic/esql-js`](https://github.com/elastic/esql-js) monorepo, under
> [`packages/prismjs-esql`](https://github.com/elastic/esql-js/tree/main/packages/prismjs-esql).
> Please open issues and pull requests there instead of here. This repository
> is kept for historical reference only and is no longer maintained.

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
