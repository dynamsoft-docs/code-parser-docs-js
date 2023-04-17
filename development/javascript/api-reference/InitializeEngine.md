---
layout: default-layout
title: Initialize Engine - Dynamsoft Code Parser JavaScript API
description: This page shows the APIs used to initialize engine in Dynamsoft Code Parser JavaScript SDK.
keywords: Initialize Engine, api reference, javascript, js
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Initialize Engine
---

# Initialization

* engineResourcePath
* loadWasm()

## engineResourcePath

Specifies the path to find the engine(s). The property needs to be set before [loadWasm](#loadwasm). If not specified, the library will try to find the engine in the same location as the main JavaScript file (dcp.js).

```typescript
static engineResourcePath: string
```

**Code Snippet**

```js
Dynamsoft.DCP.CodeParser.engineResourcePath = "https://cdn.jsdelivr.net/npm/dynamsoft-code-parser@1.1.0/dist/";
await Dynamsoft.DCP.CodeParser.loadWasm();
```

## loadWasm

Downloads and compiles the engine to get it loaded/ready for a CodeParser instance to be created. You can call this API to silently set the operating environment of the library as soon as the page is loaded, avoiding unnecessary waiting time when using the library later.

If this API is not called beforehand, it will be called automatically when creating an instance of CodeParser.

```typescript
static loadWasm(): Promise<void>
```

**Code Snippet**

```js
window.addEventListener('DOMContentLoaded', (event) => {
   Dynamsoft.DCP.CodeParser.loadWasm();
});
```
