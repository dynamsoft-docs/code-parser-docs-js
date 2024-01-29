---
layout: default-layout
title: CodeParser Module - Dynamsoft Code Parser JavaScript Edition API
description: This page introduces the CodeParser module in Dynamsoft Code Parser JavaScript Edition.
keywords: code parser, module, api reference, javascript, js
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---
<!-- 2.0.20 -- Updated on 12/11/2023-->

# DynamsoftCodeParser Module

The CodeParser module is defined in the namespace `Dynamsoft.DCP`. It includes the classes `CodeParser` and `CodeParserModule` along with a few interfaces and enumerations.

## CodeParserModule Class

This class defines common functionality in the `CodeParser` module. At present, there is only one API.

| API Name                                                          | Description                                                 |
| ----------------------------------------------------------------- | ----------------------------------------------------------- |
| `static` [getVersion()](./code-parser-module-class.md#getversion) | Returns the version of the CodeParser module.               |
| `static` [loadSpec()](./code-parser-module-class.md#loadspec)     | Loads the specification for a certain type of code strings. |

## CodeParser Class

The `CodeParser` class enable users to parse given bytes or a string.

| Method                                                       | Description                                                            |
| ------------------------------------------------------------ | ---------------------------------------------------------------------- |
| `static` [createInstance()](./code-parser.md#createinstance) | Initializes a new instance of the `CodeParser` class.                  |
| [dispose()](./code-parser.md#dispose)                        | Releases all resources used by the `CodeParser` object.                |
| [disposed](./code-parser.md#disposed)                        | Returns whether the `CodeParser` object has been disposed of.          |
| [initSettings](./code-parser.md#initsettings)                | Initializes runtime settings with the settings in a given JSON string. |
| [resetSettings](./code-parser.md#resetsettings)              | Resets runtime settings to default.                                    |
| [parse](./code-parser.md#parse)                              | Parses code data for readable results.                                 |

## Interfaces

* [ParsedResultItem](./interfaces/parsed-result-item.md)
* [ParsedResult](./interfaces/parsed-result.md)

## Enumerations

* [EnumMappingStatus]({{ site.dcv_enumerations }}code-parser/mapping-status.html)
* [EnumValidationStatus]({{ site.dcv_enumerations }}code-parser/validation-status.html)