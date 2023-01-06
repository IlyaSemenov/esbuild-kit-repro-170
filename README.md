See <https://github.com/esbuild-kit/tsx/issues/170>

Run `pnpm i`.

Run `pnpm tap --no-coverage --node-arg '--loader' --node-arg 'tsx' test.ts`, you will get:

```
 FAIL  test.ts
 ✖ should be equivalent

  test.ts
  1 | import tap from "tap"
> 2 |
  3 | tap.same("a", "a")
  4 |
  5 | tap.same("a", "b")
```

Run `pnpm tap --no-coverage --node-arg '-r' --node-arg '@swc-node/register' test.ts`, you will get:

```
 FAIL  test.ts
 ✖ should be equivalent

  test.ts
  3 | tap.same("a", "a")
  4 |
> 5 | tap.same("a", "b")
    | ----^
```
