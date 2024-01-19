---
layout: default-layout
title: ParsedResult - Dynamsoft Code Parser JavaScript Interface
description: This page shows the ParsedResult interface of Dynamsoft Code Parser for JavaScript.
keywords: ParsedResult, javascript, interface
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: ParsedResult
---

# ParsedResult

The ParsedResult interface provides a structure representing the result object returned by Dynamsoft Code Parser.

```ts
interface ParsedResult {
  originalImageHashId: string;
  originalImageTag: Core.ImageTag;
  parsedResultItems: Array<ParsedResultItem>;
  hasItem: (item: ParsedResultItem) => boolean;
  removeItem: (item: ParsedResultItem) => void;
  errorCode: number;
  errorString: string;
}
```

| API Name                                    | Description                                                 |
| ------------------------------------------- | ----------------------------------------------------------- |
| [originalImageHashId](#originalimagehashid) | Returns the hash id of the original image.                  |
| [originalImageTag](#originalimagetag)       | Returns the tag of the original image.                      |
| [parsedResultItems](#parsedresultitems)     | Returns an array that contains all `ParsedResultItem`s.     |
| [hasItem()](#hasitem)                       | Checks whether the specified `ParsedResultItem` exists.     |
| [removeItem()](#removeitem)                 | Removes the specified `ParsedResultItem`.                   |
| [errorCode](#errorcode)                     | Returns the error code for the parsing operation.           |
| [errorString](#errorstring)                 | Returns the error string that corresponds with `errorCode`. |

## originalImageHashId

Returns the hash id of the original image.

```ts
originalImageHashId: string;
```

## originalImageTag

Returns the tag of the original image.

```ts
originalImageTag: Core.ImageTag;
```

**See Also**

* [ImageTag](https://www.dynamsoft.com/capture-vision/docs/web/programming/javascript/api-reference/core/basic-structures/image-tag.html)

## parsedResultItems

Returns an array that contains all `ParsedResultItem`s.

## hasItem()

Checks whether the specified `ParsedResultItem` exists.

## removeItem()

Removes the specified `ParsedResultItem`.

## errorCode

Returns the error code for the parsing operation.

## errorString

Returns the error string that corresponds with `errorCode`.
