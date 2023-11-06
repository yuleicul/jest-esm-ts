# Using Jest with ESModules and TypeScript

## Getting Started

Initialize `npm` package and install related packages:

```shell
npm init -y
npm install -D jest typescript ts-jest @types/jest
```

> `jest`: the test runner
> 
> `typescript`: the TypeScript compiler
> 
> `ts-jest`: a TypeScript preprocessor with source map support for Jest that lets you use Jest to test projects written in TypeScript
> 
> `@types/jest`: provides type definitions, including types for Jest globals without a need to import them

Create a basic Jest configuration that introduces a preset handling TypeScript and ESModules correctly:

```shell
npx ts-jest config:init
```

Create a `sum.ts` file:

```ts
export default function sum(a: number, b: number) {
  return a + b
}
```

Then, create a file named `sum.test.ts`:

```ts
import sum from './sum'

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3)
})
```

Add the following script to your `package.json`:

```json
{
  "scripts": {
    "test": "jest"
  }
}
```

Finally, run `npm test` and Jest will print this message:

```shell
PASS  ./sum.test.ts
✓ adds 1 + 2 to equal 3 (3 ms)
```

## References

- https://jestjs.io/docs/getting-started
- https://jestjs.io/docs/ecmascript-modules
- https://kulshekhar.github.io/ts-jest/docs/getting-started/installation
- https://kulshekhar.github.io/ts-jest/docs/getting-started/presets
- https://kulshekhar.github.io/ts-jest/docs/guides/esm-support
- https://www.totaltypescript.com/cannot-redeclare-block-scoped-variable
