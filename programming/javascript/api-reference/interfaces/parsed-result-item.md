---
layout: default-layout
title: ParsedResultItem - Dynamsoft Code Parser JavaScript Interface
description: This page shows the ParsedResultItem interface of Dynamsoft Code Parser for JavaScript.
keywords: ParsedResultItem, javascript, interface
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: ParsedResultItem
---

# ParsedResultItem

The ParsedResultItem interface provides a structure representing the result items returned by Dynamsoft Code Parser.

```ts
interface ParsedResultItem extends Core.CapturedResultItem {
    codeType: string;
    jsonString: string;
    getFieldValue: (fieldName: string) => string;
    getFieldRawValue: (fieldName: string) => string;
    getFieldMappingStatus: (fieldName: string) => EnumMappingStatus;
    getFieldValidationStatus: (fieldName: string) => EnumValidationStatus;
    getAllFieldNames(): Array<string>;
}
```

<!-- | API Name                                                | Description                                                             |
| ------------------------------------------------------- | ----------------------------------------------------------------------- |
| [codeType](#codetype)                                   | Returns the code type of the parsed result.                             |
| [jsonString](#jsonstring)                               | Returns the parsed result as a JSON formatted string.                   |
| [getFieldValue()](#getfieldvalue)                       | Gets the value of a specified field from the parsed result.             |
| [getFieldMappingStatus()](#getfieldmappingstatus)       | Gets the mapping status of a specified field from the parsed result.    |
| [getFieldValidationStatus()](#getfieldvalidationstatus) | Gets the validation status of a specified field from the parsed result. |
| [getAllFieldNames()](#getallfieldnames)                  | Retrieves a list of all field names present in the parsed result.       | -->

## codeType

Returns the code type of the parsed result.

```ts
codeType: string;
```

## jsonString

Returns the parsed result as a JSON formatted string.

```ts
jsonString: string;
```

## getFieldValue

Gets the value of a specified field from the parsed result.

```ts
getFieldValue(fieldName: string): string;
```

**Parameters**

`fieldName`: specifies the name of the field.

**Return Value**

A string which contains the field value.

**Code Snippet**

```js
parser.getFieldValue("passportNumber");
```

## getFieldRawValue

Gets the value of a specified field from the parsed result, without mapping process.

```ts
getFieldRawValue(fieldName: string): string;
```

**Parameters**

`fieldName`: specifies the name of the field.

**Return Value**

A string which contains the field raw value.

**Code Snippet**

```js
parser.getFieldRawValue("passportNumber");
```

## getFieldMappingStatus

Gets the mapping status of a specified field from the parsed result.

```ts
getFieldMappingStatus: (fieldName: string) => EnumMappingStatus;
```

**Parameters**

`fieldName`: specifies the name of the field.

**Return Value**

A value that indicates whether the mapping succeeded.

**Code Snippet**

```js
await parser.getFieldMappingStatus("nationality");
```

**See Also**

* [EnumMappingStatus](../enum/EnumMappingStatus.md)

## getFieldValidationStatus

Gets the validation status of a specified field from the parsed result.

```ts
getFieldValidationStatus: (fieldName: string) => EnumValidationStatus;
```

**Parameters**

`fieldName`: specifies the name of the field.

**Return Value**

A value that indicates whether the validation succeeded.

**Code Snippet**

```js
await parser.getFieldValidationStatus("passportNumber");
```

**See Also**

* [EnumValidationStatus](../enum/EnumValidationStatus.md)

## getAllFieldNames

Retrieves a list of all field names present in the parsed result. This method allows for dynamic access to the fields in the parsed result, enabling users to iterate through all available fields without needing to know their names in advance.

```ts
getAllFieldNames(): Array<string>;
```

**Return Value**

An array of strings, where each string is a field name from the parsed result.

**Remarks**

* If a field is nested, its name includes all parent field names separated by a dot (`.`). The format follows this pattern: `<parent>[.<child>[.<...>]]`.
* New added in CaptureVisionBundle version 3.4.2000.

**Code Snippet**

```js
const fieldNames = parsedResultItem.getAllFieldNames();
for (const name of fieldNames) {
    console.log(name, parsedResultItem.getFieldValue(name));
}
```
