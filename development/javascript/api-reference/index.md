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
| [license](LicenseControl.md#license) | Initializes license of DCP. |

### Initialize Engine

| API Name | Description |
|---|---|
| [engineResourcePath](InitializationControl.md#engineresourcepath) | Specifies the path of WASM engine. |
| [loadWasm()](InitializationControl.md#loadwasm) | Loads and compiles the WASM. |

### Create and Destroy

| API Name | Description |
|---|---|
| [createInstance()](CodeParser.md#createinstance) | Creates a `CodeParser` instance. |
| [destroyContext()](CodeParser.md#destroycontext) | Destroys the `CodeParser` instance in WASM. |

### Set Code Format

| API Name | Description |
|---|---|
| [setCodeFormat()](CodeParser.md#setcodeformat) | Sets input code's format. |

### Parse Code Data

| API Name | Description |
|---|---|
| [parseData()](CodeParser.md#parsedata) | Parses code data for readable results. |

<!--

### Set Encryption Key

| API Name | Description |
|---|---|
| [setCryptoPublicKey()](CodeParser.md#setcryptopublickey) | Set a public key if code parsing needs. |
| [setCertificate()](CodeParser.md#setcertificate) | Set a certificate if code parsing needs. |

-->

## Interfaces and Enums

In order to make the code more predictable and readable, the library defines a series of supporting interfaces and enumerations:

### Interfaces

* [CodeParserException](../api-reference/interface/CodeParserEception.md)
* [BasicPersonalInfo](../api-reference/interface/BasicPersonalInfo.md)
* [ParseResult](../api-reference/interface/ParseResult.md)

### Enums

* [EnumErrorCode](../api-reference/enum/EnumErrorCode.md)
* [EnumCodeFormat](../api-reference/enum/EnumCodeFormat.md)
* [EnumResultInfoType](../api-reference/enum/EnumResultInfoType.md)
