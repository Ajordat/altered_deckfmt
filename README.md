# altered-deckfmt

> This repository is a Python library of the original specification defined in [Taum/altered-deckfmt](https://github.com/Taum/altered-deckfmt).
> 
> This is a work in progress and many changes are still pending to be made. Among them, rewriting this file to adapt it to Python code.

A Compact format to share decklists for Altered TCG.

This binary format can be encoded to Base64 to share decks in URL-safe codes. As an example, a reasonable decklist such as:

```
1 ALT_CORE_B_YZ_03_C
3 ALT_CORE_B_BR_16_R2
2 ALT_CORE_B_YZ_04_C
3 ALT_CORE_B_YZ_07_R1
1 ALT_CORE_B_BR_10_R2
1 ALT_CORE_B_MU_08_R2
3 ALT_CORE_B_YZ_06_C
2 ALT_CORE_B_YZ_11_C
1 ALT_CORE_B_YZ_12_C
3 ALT_CORE_B_YZ_14_C
3 ALT_CORE_B_BR_25_R2
3 ALT_CORE_B_YZ_19_C
1 ALT_CORE_B_BR_28_R2
3 ALT_CORE_B_MU_25_R2
3 ALT_CORE_B_YZ_21_C
3 ALT_CORE_B_YZ_22_C
2 ALT_CORE_B_YZ_24_C
1 ALT_CORE_B_YZ_26_C
1 ALT_CORE_B_YZ_25_C
```

Can be encoded into the string:
```
EBAk3DNQrEPHVKmIvGLLHMPONZvTFcuZvVPWLYHaHZA=
```

This project provides a Javascript/Typescript module that can either be imported into a NodeJS project or loaded into a web page.

Demo page to encode/decode decklists: https://taum.github.io/altered-deckfmt/

A format specification in available in [FORMAT_SPEC.md](FORMAT_SPEC.md).

## Usage

see `src/test/encoding.test.ts` for an example of using these functions

```
import { encodeList } from 'altered-deckfmt'

const myList = "1 ALT_CORE_B_YZ_03_C\n3 ALT_CORE_B_BR_16_R2 ..."
const base64deck = encodeList(myList)

console.log(base64deck) // "EBAk3DNQrEPHVKmIvGLLHMPONZvTFcuZvVPWLYHaHZA="
```

```
import { decodeList } from 'altered-deckfmt'

const myBase64id = "EBAk3DNQrEPHVKmIvGLLHMPONZvTFcuZvVPWLYHaHZA="
const decklist = decodeList(myBase64id)

console.log(decklist) // "1 ALT_CORE_B_YZ_03_C\n3 ALT_CORE_B_BR_16_R2 ..."
```

### Import in a web page

Use the `UMD` import provided in the `dist` folder.
See [dist-demo.html](dist-demo.html) for an example of how to use in your page.

## Developement

### Install
```
yarn install
```

### Development sandbox
```
yarn dev
```

### Run Tests
```
yarn test
```