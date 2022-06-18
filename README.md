Bug reproduction.

To run it:

```bash
git clone git@github.com:brillout/graphql-apollo_vite-3_bug-2
cd graphql-apollo_vite-3_bug-2/
pnpm run setup
pnpm install
pnpm run build
cd examples/graphql-apollo-vue/
pnpm run prod
```

Same as single line (copy paste me):

```bash
git clone git@github.com:brillout/graphql-apollo_vite-3_bug-2 && cd graphql-apollo_vite-3_bug-2/ && pnpm run setup && pnpm install && pnpm run build && cd examples/graphql-apollo-vue/ && pnpm run prod
```

Observe the error:

```
'default' is not exported by .../@apollo_client.js
```

More context:

```
vite v3.0.0-alpha.12 building for production...
transforming (110) node_modules/.vite/deps_build-69a4c753/cross-fetch.jsError when using sourcemap for reporting an error: Can't resolve original location of error.
✓ 114 modules transformed.
'default' is not exported by node_modules/.vite/deps_build-69a4c753/@apollo_client.js, imported by pages/index/index.page.vue
file: /home/romuuu/tmp/graphql-apollo_vite-3_bug-2/examples/graphql-apollo-vue/pages/index/index.page.vue:3:7
1: 
2: import { useQuery, useResult } from '/home/romuuu/tmp/graphql-apollo_vite-3_bug-2/examples/graphql-apollo-vue/node_modules/.vite/deps_build-69a4c753/@vue_apollo-composable.js'
3: import client from '/home/romuuu/tmp/graphql-apollo_vite-3_bug-2/examples/graphql-apollo-vue/node_modules/.vite/deps_build-69a4c753/@apollo_client.js'
          ^
4: const { gql } = client;
5: const getChar = gql`
error during build:
Error: 'default' is not exported by node_modules/.vite/deps_build-69a4c753/@apollo_client.js, imported by pages/index/index.page.vue
    at error (file:///home/romuuu/tmp/graphql-apollo_vite-3_bug-2/node_modules/.pnpm/rollup@2.75.6/node_modules/rollup/dist/es/shared/rollup.js:1858:30)
```
