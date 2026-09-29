# @stackline/vfile-statistics

> vfile utility to count messages per category: failures, warnings, etc.

[![npm version](https://img.shields.io/npm/v/@stackline/vfile-statistics.svg?style=flat-square)](https://www.npmjs.com/package/@stackline/vfile-statistics)
[![license](https://img.shields.io/npm/l/@stackline/vfile-statistics.svg?style=flat-square)](https://github.com/alexandroit/stackline-vfile-statistics)
[![GitHub repository](https://img.shields.io/badge/GitHub-repository-181717?style=flat-square&logo=github)](https://github.com/alexandroit/stackline-vfile-statistics)
[![Docs](https://img.shields.io/badge/docs-alexandro.net-0f766e?style=flat-square)](https://alexandro.net/docs/vanilla/vfile-statistics/)
[![Reddit community](https://img.shields.io/badge/community-r%2FStackline-ff4500?style=flat-square&logo=reddit&logoColor=white)](https://www.reddit.com/r/Stackline/)

**[Documentation](https://alexandro.net/docs/vanilla/vfile-statistics/)** | **[npm](https://www.npmjs.com/package/@stackline/vfile-statistics)** | **[Issues](https://github.com/alexandroit/stackline-vfile-statistics/issues)** | **[Repository](https://github.com/alexandroit/stackline-vfile-statistics)**

**Current package version:** `1.0.2`

---

## Why this package?

`@stackline/vfile-statistics` is the Stackline-maintained distribution of `vfile-statistics@2.0.1`. It is an independent continuation of [vfile-statistics](https://github.com/vfile/vfile-statistics); original authors and licenses remain credited below.

## Compatibility

| Item | Value |
| :--- | :--- |
| Package | `@stackline/vfile-statistics@1.0.2` |
| API target | `vfile-statistics@2.0.1` |
| Supported Node.js | `See supported framework requirements` |
| License | `MIT` |
| Module type | `module` |
| Main entry | `index.js` |
| Types | `index.d.ts` |
| Runtime dependencies | `vfile, vfile-message` |

## Installation

```bash
npm install @stackline/vfile-statistics
```

Preserve existing imports and plugin resolution with an npm alias:

```bash
npm install vfile-statistics@npm:@stackline/vfile-statistics
```

## Usage and API reference

### vfile-statistics


[vfile][] utility to count messages per category (fatal, warn, info, etc).

## Contents

*   [What is this?](#what-is-this)
*   [When should I use this?](#when-should-i-use-this)
*   [Install](#install)
*   [Use](#use)
*   [API](#api)
    *   [`statistics(file)`](#statisticsfile)
    *   [`Statistics`](#statistics)
*   [Types](#types)
*   [Compatibility](#compatibility)
*   [Contribute](#contribute)
*   [License](#license)

## What is this?

This tiny package gives you stats about messages in files.

## When should I use this?

This is really tiny, you could do it yourself, but this is useful as a building
block.

## Install

This package is [ESM only][esm].
In Node.js (version 14.14+ and 16.0+), install with [npm][]:

```sh
npm install @stackline/vfile-statistics
```

In Deno with [`esm.sh`][esmsh]:

```js
import {statistics} from 'https://esm.sh/vfile-statistics@2'
```

In browsers with [`esm.sh`][esmsh]:

```html
<script type="module">
  import {statistics} from 'https://esm.sh/vfile-statistics@2?bundle'
</script>
```

## Use

```js
import {VFile} from 'vfile'
import {statistics} from '@stackline/vfile-statistics'

const file = new VFile({path: '~/example.md'})

file.message('This could be better')
file.message('That could be better')

try {
  file.fail('This is terribly wrong')
} catch {}

file.info('This is perfect')

console.log(statistics(file))
```

Yields:

```js
{fatal: 1, nonfatal: 3, warn: 2, info: 1, total: 4}
```

## API

This package exports the identifier [`statistics`][api-statistics].
There is no default export.

### `statistics(file)`

Get stats for a file, list of files, or list of messages.

###### Parameters

*   `file` ([`VFile`][vfile], [`VFileMessage`][vfile-message],
    `Array<VFile | VFileMessage>`, optional)
    — file, message, or list of files or messages.

###### Returns

Statistics ([`Statistics`][api-statistics-map]).

### `Statistics`

Statistics (TypeScript type).

###### Fields

*   `fatal` — fatal errors (`fatal: true`)
*   `warn` — warning messages (`fatal: false`)
*   `info` — informational messages (`fatal: null | undefined`)
*   `nonfatal` — warning or info messages
*   `total` — all messages

## Types

This package is fully typed with [TypeScript][].
It exports the additional type [`Statistics`][api-statistics-map].

## Compatibility

Projects maintained by the unified collective are compatible with all maintained
versions of Node.js.
As of now, that is Node.js 14.14+ and 16.0+.
Our projects sometimes work with older versions, but this is not guaranteed.

## Contribute

See [`contributing.md`][contributing] in [`vfile/.github`][health] for ways to
get started.
See [`support.md`][support] for ways to get help.

This project has a [code of conduct][coc].
By interacting with this repository, organization, or community you agree to
abide by its terms.

## License

[MIT][license] © [Titus Wormer][author]



[build-badge]: https://github.com/vfile/vfile-statistics/workflows/main/badge.svg

[build]: https://github.com/vfile/vfile-statistics/actions

[coverage-badge]: https://img.shields.io/codecov/c/github/vfile/vfile-statistics.svg

[coverage]: https://codecov.io/github/vfile/vfile-statistics

[downloads-badge]: https://img.shields.io/npm/dm/vfile-statistics.svg

[downloads]: https://www.npmjs.com/package/vfile-statistics

[size-badge]: https://img.shields.io/bundlephobia/minzip/vfile-statistics.svg

[size]: https://bundlephobia.com/result?p=vfile-statistics

[sponsors-badge]: https://opencollective.com/unified/sponsors/badge.svg

[backers-badge]: https://opencollective.com/unified/backers/badge.svg

[collective]: https://opencollective.com/unified

[chat-badge]: https://img.shields.io/badge/chat-discussions-success.svg

[chat]: https://github.com/vfile/vfile/discussions

[npm]: https://docs.npmjs.com/cli/install

[esm]: https://gist.github.com/sindresorhus/a39789f98801d908bbc7ff3ecc99d99c

[esmsh]: https://esm.sh

[typescript]: https://www.typescriptlang.org

[contributing]: https://github.com/vfile/.github/blob/main/contributing.md

[support]: https://github.com/vfile/.github/blob/main/support.md

[health]: https://github.com/vfile/.github

[coc]: https://github.com/vfile/.github/blob/main/code-of-conduct.md

[license]: license

[author]: https://wooorm.com

[vfile]: https://github.com/vfile/vfile

[vfile-message]: https://github.com/vfile/vfile-message

[api-statistics]: #statisticsfile

[api-statistics-map]: #statistics

## Credits and original authors

- Original project: [vfile-statistics](https://github.com/vfile/vfile-statistics).
- Titus Wormer.
- Brendan Abbott.
- Copyright (c) 2016 Titus Wormer <tituswormer@gmail.com>.
- Stackline maintenance: [Alexandro Paixao Marques](https://www.linkedin.com/in/aleinfo/) and [Stackline contributors](https://github.com/alexandroit).

Original copyright, license notices and contributor acknowledgements remain part of this distribution. Stackline maintenance does not replace authorship of the original work.

## Community and Links

- [Stackline website](https://alexandro.net/)
- [GitHub projects](https://github.com/alexandroit)
- [npm packages](https://www.npmjs.com/~alex360qc)
- [Reddit community — r/Stackline](https://www.reddit.com/r/Stackline/)
- [Maintainer LinkedIn](https://www.linkedin.com/in/aleinfo/)

Use this repository's issue tracker for reproducible bugs and feature requests. Join r/Stackline for examples, usage questions and release discussions.
