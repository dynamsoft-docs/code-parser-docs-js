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
| `static` [onSpecLoadProgressChanged()](#onspecloadprogresschanged)                        | An event that fires during the loading of specification files. |

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
loadSpec(specificationName: string | Array<string>, specificationPath?: string): Promise<void>;
```

**Parameters**

* `specificationName`: specifies the name of the specification.
* `specificationPath`: specifies the path to find the specification file. If not specified, the method will try to load the file from the path specified in `Dynamsoft.Core.CoreModule.engineResourcePaths`. For example, if the engineResourcePaths.rootDirectory = "https://cdn.jsdelivr.net/npm/", then calling `Dynamsoft.DCP.CodeParserModule.loadSpec("AADHAAR")` will load the file "AADHAAR.data" from "https://cdn.jsdelivr.net/npm/dynamsoft-capture-vision-data/parser-resources/AADHAAR.data".

**Code Snippet**

```javascript
await Dynamsoft.DCP.CodeParserModule.loadSpec("AADHAAR");
```

**Remarks**

Starting from CaptureVisionBundle version 3.4.1000, some specification resources have been merged. The complete set of current resources can be found at:
https://www.npmjs.com/package/dynamsoft-capture-vision-data

### onSpecLoadProgressChanged

An event that fires during the loading of specification files.

**Syntax**

```typescript
static onSpecLoadProgressChanged (filePath: string, tag: "starting"| "in progress" | "completed", progress: { loaded: number, total: number }) : void;
```

**Parameter**

`filePath` : The path of the specification files.

`tag`(Optional) : Indicates the ongoing status of the file download ("starting", "in progress", "completed").

`progress` : An object indicating the progress of the download, with `loaded` and `total` bytes.

**Return value**

None.

**Code snippet**

```javascript
Dynamsoft.DCP.CodeParserModule.onSpecLoadProgressChanged = function(filePath, tag, progress) {
    console.log(`Status: ${tag} - File: ${filePath}`);
    if (tag === "in progress") {
        let percent = ((progress.loaded / progress.total) * 100).toFixed(1);
        console.log(`Progress: ${percent}%`);
    } else if (tag === "completed") {
        console.log("specification files loading completed!");
    }
};
```

**Remarks**

Introduced in Dynamsoft Barcode Reader Bundle version 11.2.2000 and Dynamsoft Capture Vision Bundle version 3.2.1000.