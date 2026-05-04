---
layout: default-layout
title: MappingStatus Enum – Dynamsoft Code Parser JS API
description: "Explore MappingStatus values in Dynamsoft Code Parser JavaScript API and learn how they define status, configuration, and processing behavior for modern web."
keywords: Mapping status
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: MappingStatus
---

# Enumeration MappingStatus

`MappingStatus` represents the outcome of a mapping operation on a field.

<div class="sample-code-prefix template2"></div>
   >- JavaScript
   >
>
```javascript
enum EnumMappingStatus {
    /** 
     * Indicates that no mapping operation has been initiated.
     */
    MS_NONE = 0,
    /** 
     * Indicates that the mapping operation was successfully completed.
     */
    MS_SUCCEEDED = 1,
    /** 
     * Indicates that the mapping operation failed to complete.
     */
    MS_FAILED = 2
}
```