# ast-grep napi language for dart

Since Dart has been removed as an officially supported language in `ast-grep` ([see here](https://github.com/ast-grep/ast-grep/commit/cd25a628f07bba546b9b7f7333079de481995def)),
This adds Dart language support for `@ast-grep/napi` using the `tree-sitter-dart` library from <https://github.com/UserNobody14/tree-sitter-dart>.

Supporting Dart for `@ast-grep/napi` can be useful for codemods for the Dart and Flutter ecosystem.

## Installation

In a pnpm project, run:

```bash
pnpm install ast-grep-tree-sitter-dart
pnpm install @ast-grep/napi
# install the tree-sitter-cli if no prebuild is available
pnpm install @tree-sitter/cli --save-dev
```

## Usage

```js
import dart from 'ast-grep-tree-sitter-dart'
import { registerDynamicLanguage, parse } from '@ast-grep/napi'

registerDynamicLanguage({ dart })

const sg = parse('dart', `your code`)
sg.root().kind()
```
