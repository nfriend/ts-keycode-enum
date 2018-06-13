# ts-keycode-enum
A TypeScript enum definition that maps human-friendly key names to JavaScript key codes

<img align="right" src="https://raw.githubusercontent.com/nfriend/ts-keycode-enum/master/logo.jpg" />

## Important note

[`event.which`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/which) and [`event.keyCode`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/keyCode) have been deprecated.  It is recommended to instead use [`event.key`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key) in combination with this very similar module: [ts-key-enum](https://github.com/nfriend/ts-key-enum).

## Install

```bash
npm install ts-keycode-enum --save
```

## Purpose

Tired of referencing JavaScript keycodes by number?

```JavaScript
onKeyPress = (ev) => {

    // gross
    if (ev.which === 13) {
        ...
    }
}
```

Me too.  With this module, you can do this instead (in a TypeScript file):

```JavaScript
onKeyPress = (ev) => {

    // much better
    if (ev.which === Key.Enter) {
        ...
    }
}
```

## Usage

To use this module, import the `Key` enum at the top of your TypeScript file using the enum:

```JavaScript
import { Key } from 'ts-keycode-enum';
```

You can now use a readable enum value in place of any raw keycodes throughout the file:

```JavaScript
if (ev.which === Key.Escape) { ... }
```

See [Key.enum.ts](./Key.enum.ts) for a complete list of available keys.

In addition, to aid with readability, a number of enum values have aliases.  For example:

```JavaScript
// this  true - these values are equal
Key.One === Key.ExclamationMark
```

Use whichever value makes more sense for readability.

## Building

To build this module yourself, first install its dependencies using

```bash
npm install
```

Then, run the build using

```bash
npm run build
```

Build output is placed in the `dist` directory.

## Contributions

This module only contains some of the most commonly-used key codes.  If it's missing keycodes that you need, feel free to request the codes via an issue or a pull request.

## License

MIT