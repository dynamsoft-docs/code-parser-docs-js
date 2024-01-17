---
layout: default-layout
title: CodeParserModule Class - Dynamsoft Code Parser JavaScript Edition API
description: This page introduces APIs related to the CodeParserModule Class of Dynamsoft Code Parser JavaScript Edition.
keywords: capture vision, code parser Module, api reference, javascript, js
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# CodeParserModule Class

The `CodeParserModule` class is defined in the namespace `Dynamsoft.DCP`.

| API Name                             | Description                                                 |
| ------------------------------------ | ----------------------------------------------------------- |
| `static` [getVersion()](#getversion) | Returns the version of the `CodeParser` module.             |
| `static` [loadSpec()](#loadspec)     | Loads the specification for a certain type of code strings. |

### getVersion

Returns the version of the `CodeParser` module.

```typescript
static getVersion(): string;
```

**Code snippet**

```javascript
const version = Dynamsoft.DCP.CodeParserModule.getVersion();
console.log(version);
```

### loadSpec

Loads the specification for a certain type of code strings.

```typescript
loadSpec(specificationName: string, specificationPath?: string): Promise<void>;
```

**Parameters**

* `specificationName`: specifies the name of the specification.
* `specificationPath`: specifies the path to find the specification file. If not specified, the method will try to load the file from the path specified for the "dcp" module in `Dynamsoft.Core.CoreModule.engineResourcePaths`. For example, if the path for the "dcp" module is "https://cdn.jsdelivr.net/npm/dynamsoft-code-parser@2.0.20/dist/", then calling `Dynamsoft.DCP.CodeParserModule.loadSpec("AADHAAR")` will load the file "AADHAAR.data" from "https://cdn.jsdelivr.net/npm/dynamsoft-code-parser@2.0.20/dist/specification/AADHAAR.data".

**Code Snippet**

```javascript
await Dynamsoft.DCP.CodeParserModule.loadSpec("AADHAAR");
```
