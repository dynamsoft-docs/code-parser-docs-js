---
layout: default-layout
title: Initialize License - Dynamsoft Code Parser JavaScript API
description: This page shows the APIs used to initialize license in Dynamsoft Code Parser JavaScript SDK.
keywords: Initialize License, api reference, javascript, js
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Initialize License
---

# License Control

* license


## license

Specify an online license or an offline license. Dynamsoft usually provides an online license. 

`license` needs to be set before `createInstance()` or `loadWasm()`.

```typescript
static license: string
```

**Code Snippet**

```js
Dynamsoft.DCP.CodeParser.license = "YOUR-LICENSE-KEY";
let parser = await Dynamsoft.DCP.CodeParser.createInstance();
```