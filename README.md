# codegen.macro

[![Babel Macro](https://img.shields.io/badge/babel--plugin--macro-%F0%9F%8E%A3-f5da55.svg?style=flat-square)](https://github.com/kentcdodds/babel-plugin-macros)

This is a [`babel-plugin-macros`][babel-plugin-macros] macro for
[`babel-plugin-codegen`][babel-plugin-codegen].

Please see those projects for more information.

## Installation

This module is distributed via [npm][npm] which is bundled with [node][node] and
should be installed as one of your project's `devDependencies`:

```
npm install --save-dev codegen.macro
```

You'll also need to install and configure
[`babel-plugin-macros`][babel-plugin-macros] if you haven't already.

## Usage

Once you've
[configured `babel-plugin-macros`](https://github.com/kentcdodds/babel-plugin-macros/blob/master/other/docs/user.md)
you can import/require `codegen.macro`. For example:

```js
import codegen from 'codegen.macro'

codegen`module.exports = ['a', 'b', 'c'].map(l => 'export const ' + l + ' = ' + JSON.stringify(l)).join(';')`

      ↓ ↓ ↓ ↓ ↓ ↓

export const a = "a";
export const b = "b";
export const c = "c";
```

You'll find more usage capabilities in the [`babel-plugin-codegen` test
snapshots][snapshots].

**Note**:

[`babel-plugin-codegen`][babel-plugin-codegen] allows you to have a few more
APIs than you have with this macro, but this macro comes with all the benefits
of using [`babel-plugin-macros`][babel-plugin-macros] (which you can read about
in the `babel-plugin-macros` docs).

<!-- prettier-ignore-start -->
[npm]: https://www.npmjs.com
[node]: https://nodejs.org

[babel-plugin-macros]: https://github.com/kentcdodds/babel-plugin-macros
[babel-plugin-codegen]: https://github.com/kentcdodds/babel-plugin-codegen
[snapshots]: https://github.com/kentcdodds/babel-plugin-codegen/blob/master/src/__tests__/__snapshots__/macro.js.snap
<!-- prettier-ignore-end -->
