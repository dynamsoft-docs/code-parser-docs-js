---
layout: default-layout
title: CodeParser Class - Dynamsoft Code Parser SDK JS Edition API Reference
description: This page shows CodeParser Class of Dynamsoft Code Parser SDK JS Edition.
keywords: CodeParser, api reference, JS, JavaScript
needAutoGenerateSidebar: true
---

# CodeParser Class

The `CodeParser` class enable users to parse given bytes or a string.

| Method                                       | Description                                                            |
| -------------------------------------------- | ---------------------------------------------------------------------- |
| `static` [createInstance()](#createinstance) | Initializes a new instance of the `CodeParser` class.                  |
| [dispose()](#dispose)                        | Releases all resources used by the `CodeParser` object.                |
| [disposed](#disposed)                        | Returns whether the `CodeParser` object has been disposed of.          |
| [initSettings](#initsettings)              | Initializes runtime settings with the settings in a given JSON string. |
| [resetSettings](#resetsettings)            | Resets runtime settings to default.                                    |
| [parse](#parse)                            | Parses code data for readable results.                                 |

## createInstance

Initializes a new instance of the `CodeParser` class.

**Syntax**

```typescript
createInstance(): Promise<CodeParser>;
```

**Parameter**

None.

**Return value**

A promise that resolves to the initialized `CodeParser` object.

**Code snippet**

```javascript
let parser = await Dynamsoft.CVR.CodeParser.createInstance();
```

## dispose

Releases all resources used by the `CodeParser` object.

**Syntax**

```typescript
dispose(): Promise<void>;
```

**Parameter**

None.

**Return value**

Returns a promise that resolves when the resources have been successfully released.

**Code snippet**

```javascript
let parser = await Dynamsoft.CVR.CodeParser.createInstance();
// Use the parser to perform a job.
// ...
// Release the resources after the job is finished.
parser.dispose();
```

## disposed

Returns whether the `CodeParser` object has been disposed of.

**Syntax**

```typescript
disposed: boolean;
```

**Parameter**

None.

**Return value**

A boolean value that indicates whether the `CodeParser` object has been disposed of.

**Code snippet**

```javascript
if(parser.disposed){
    console.log("The parser has been disposed of.");
} else {
    // Use the parser to perform a job.
}
```

## initSettings

Initializes settings from a given string.

```typescript
initSettings: (settings: string) => Promise<void>;
```

**Parameters**

* `settings`: A JSON string that represents the content of the settings.

## resetSettings

Resets all parameters to default values.

```typescript
resetSettings: () => void;
```

## parse

Parses code data for human-readable results.

```typescript
parse: (source: Array<number> | string, taskSettingName?: string) => Promise<ParsedResultItem>;
```

**Parameters**

* `source`: the array of bytes or the string to parse.

* `taskSettingName`: the name of [CodeParserTaskSetting]({{site.parameters}}file/task-settings/code-parser-task-settings.html) that defines the settings used for code parsing.

**Return Value**

Returns an array of [ParsedResultItem](./interfaces/parsed-result-item.md) containing the human-readable results.
