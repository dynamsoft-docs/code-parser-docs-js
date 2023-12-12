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
Dynamsoft.License.LicenseManager.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9"); //Change to your own license key
let parser = await Dynamsoft.DCP.CodeParser.createInstance();
// Assume "code" is the string that needs to be parsed.
let result = await parser.parse(code);
if(result){
    let codeType = result.getCodeType();
    console.log("The type of the code is: " + codeType);
    if (codeType == "MRTD_TD3_PASSPORT")
    {
        let passportNumber = result.getFieldValue("passportNumber");
        if (passportNumber)
        {
            console.log("The passport number is : " + passportNumber);
        }
        // Check out https://www.dynamsoft.com/code-parser/docs/core/code-types/mrtd.html#mrtd_td3_passport-fields for more supported fields
    }
}
```

The APIs for this class include:

### Initialize Engine

| API Name                                       | Description                  |
| ---------------------------------------------- | ---------------------------- |
| [loadWasm()](./initializeEngine.html#loadwasm) | Loads and compiles the WASM. |

### Create and Destroy

| API Name                                             | Description                                                  |
| ---------------------------------------------------- | ------------------------------------------------------------ |
| [createInstance()](./codeParser.html#createinstance) | Creates a `CodeParser` instance.                             |
| [dispose()](./codeParser.html#dispose)               | Releases all resources used by the `CodeParser` instance.    |
| [disposed](./codeParser.html#dispose)                | Returns whether the `CodeParser` instance has been released. |

### Change Settings

| API Name                                            | Description                                               |
| --------------------------------------------------- | --------------------------------------------------------- |
| [initSettings()](./codeParser.html#initsettings)    | Sets up the `CodeParser` instance for a parsing task.     |
| [resetSettings()](./codeParser.html#resetsetttings) | Resets the `CodeParser` instance to the default settings. |

### Parse Code Data

| API Name                               | Description                            |
| -------------------------------------- | -------------------------------------- |
| [parse()](./codeParser.html#parsedata) | Parses code data for readable results. |

## CodeParserModule

This class defines common functionality in the CodeParser module.

| API Name                                                | Description                                   |
| ------------------------------------------------------- | --------------------------------------------- |
| static [getVersion()](./codeParserModule.md#getversion) | Returns the version of the CodeParser module. |

## Interfaces and Enums

In order to make the code more predictable and readable, the library defines a series of supporting interfaces and enumerations:

### Interfaces

* [CodeParserException](./interface/CodeParserException.html)
* [ParseResult](./interface/ParseResult.html)

### Enums

* [EnumMappingStatus](./enum/EnumMappingStatus.md)
* [EnumValidationStatus](./enum/EnumValidationStatus.md)
