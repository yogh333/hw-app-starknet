# `@yogh/hw-app-starknet`

> TODO: description

## Usage

    const hwAppStarknet = require('@yogh/hw-app-starknet');

    // TODO: DEMONSTRATE API

## API

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

#### Table of Contents

*   [Stark](#stark)
    *   [Parameters](#parameters)
    *   [Examples](#examples)
    *   [getVersion](#getversion)
    *   [getAppInfo](#getappinfo)
    *   [getPubKey](#getpubkey)
        *   [Parameters](#parameters-1)
    *   [showPubKey](#showpubkey)
        *   [Parameters](#parameters-2)
        *   [Examples](#examples-1)
    *   [sign](#sign)
        *   [Parameters](#parameters-3)
    *   [signFelt](#signfelt)
        *   [Parameters](#parameters-4)

### Stark

Starknet API

#### Parameters

*   `transport` **Transport** 

#### Examples

```javascript
import Stark from "@yogh/hw-app-starknet";
const stark = new Stark(transport)
```

#### getVersion

get version of Nano Starknet application

Returns **[Promise](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise)\<ResponseVersion>** an object with a major, minor, patch

#### getAppInfo

get information about Nano Starknet application

Returns **[Promise](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise)\<ResponseAppInfo>** an object with appName, appVersion

#### getPubKey

get Starknet public key derived from provided derivation path

##### Parameters

*   `path` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** a path in EIP-2645 format (<https://github.com/ethereum/EIPs/blob/master/EIPS/eip-2645.md>)

Returns **[Promise](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise)\<ResponseAddress>** an object with publicKey*   @examplestark.getPubKey("m/2645'/579218131'/0'/0'").then(o => o.publicKey)

#### showPubKey

get and show Starknet public key derived from provided derivation path

##### Parameters

*   `path` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** a path in EIP-2645 format (<https://github.com/ethereum/EIPs/blob/master/EIPS/eip-2645.md>)

##### Examples

```javascript
stark.showPubKey("m/2645'/579218131'/0'/0'").then(o => o.publicKey)
```

Returns **[Promise](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise)\<ResponseAddress>** an object with publicKey

#### sign

sign the given hash over the Starknet elliptic curve (!! apply a SHA256() on message before computing signature)

##### Parameters

*   `path` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** a path in EIP-2645 format
*   `message` **[Uint8Array](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array)** hexadecimal hash to sign

Returns **any** an object with (r, s, v) signature

#### signFelt

sign the given hash over the Starknet elliptic curve

##### Parameters

*   `path` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** a path in EIP-2645 format
*   `hash` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** 
*   `show`   (optional, default `true`)
*   `message`  hexadecimal hash to sign

Returns **any** an object with (r, s, v) signature
