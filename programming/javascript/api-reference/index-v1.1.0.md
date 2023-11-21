---
layout: default-layout
title: Entry Page - Dynamsoft Code Parser JavaScript API
description: This is the main page of Dynamsoft Code Parser JavaScript SDK API Reference.
keywords: CodeParser, api reference, javascript, js
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: API Reference
---

# JavaScript API Reference

The Dynamsoft Code Parser JavaScript library comes with one primary class: `CodeParser`.

## CodeParser

A CodeParser takes code data in forms of byte array or plain string as input and returns parsed results. The following code snippet shows its basic usage:

```js
let parser = await Dynamsoft.DCP.CodeParser.createInstance();
parser.setCodeFormat(enumcodeformat);
let result = await parser.parseData(code);
console.log(result);
```

The APIs for this class include:

### Initialize License

| API Name | Description |
|---|---|
| [license](./licenseControl.html#license) | Initializes license of DCP. |

### Initialize Engine

| API Name | Description |
|---|---|
| [engineResourcePath](./initializeEngine.html#engineresourcepath) | Specifies the path of WASM engine. |
| [loadWasm()](./initializeEngine.html#loadwasm) | Loads and compiles the WASM. |

### Create and Destroy

| API Name | Description |
|---|---|
| [createInstance()](./codeParser.html#createinstance) | Creates a `CodeParser` instance. |
| [destroyContext()](./codeParser.html#destroycontext) | Destroys the `CodeParser` instance in WASM. |

### Set Code Format

| API Name | Description |
|---|---|
| [setCodeFormat()](./codeParser.html#setcodeformat) | Sets input code's format. |

### Parse Code Data

| API Name | Description |
|---|---|
| [parseData()](./codeParser.html#parsedata) | Parses code data for readable results. |

<!--

### Set Encryption Key

| API Name | Description |
|---|---|
| [setCryptoPublicKey()](CodeParser.html#setcryptopublickey) | Set a public key if code parsing needs. |
| [setCertificate()](CodeParser.html#setcertificate) | Set a certificate if code parsing needs. |

-->

## Interfaces and Enums

In order to make the code more predictable and readable, the library defines a series of supporting interfaces and enumerations:

### Interfaces

* [CodeParserException](./interface/CodeParserException.html)
* [BasicPersonalInfo](./interface/BasicPersonalInfo.html)
* [ParseResult](./interface/ParseResult.html)

### Enums

* [EnumErrorCode](./enum/EnumErrorCode.html)
* [EnumCodeFormat](./enum/EnumCodeFormat.html)
* [EnumResultInfoType](./enum/EnumResultInfoType.html)
