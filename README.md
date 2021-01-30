# Wick
An easier way to use the popularly known nodejs package called [node-wick](https://github.com/SirWaddles/node-wick) made by [SirWaddles](https://github.com/SirWaddles).

## Example
Examples of how to use this library.

### Create mappings.
A function that uses benbot's mappings files and endpoint and creates a *mappings* folder that has 2 folders classes, and enums and the mapping file called mappings.usmap.

```js
import { Mappings } from 'wickend';

Mappings();
```

## Wick
Easier way to use node-wick.

```js
import { Mappings, Wick } from '../index.mjs';
import fetch from 'node-fetch';

Mappings();

(async () => {
    const chain = await (await fetch('https://benbotfn.tk/api/v1/aes')).json();

    const wick = new Wick({
        extract: false,
        chain,
        path: '' // path to pak files,
        log: console.log
    });

    await wick.extract();
})();
```

### Functions

## async extract
Extracts all files in **directory** property defined in the *constructor*.

### Usage
```js
await wick.extract();
```

## getKey
Get AES Key for a package.

- **{String}** pak Package name.

### Usage
```js
const key = wick.getKey('');
```

## Issues
Please create a [issue](https://github.com/Tectors/Wick/issues/new) and I'll happily be able to respond and help, if you have a fix create a [pull request](https://github.com/Tectors/Wick/compare).
