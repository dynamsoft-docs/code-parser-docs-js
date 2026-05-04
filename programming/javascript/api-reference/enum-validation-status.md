---
layout: default-layout
title: ValidationStatus Enum – Code Parser JS SDK Ref
description: "Explore ValidationStatus values in Dynamsoft Code Parser JavaScript API and learn how they define status, configuration, and processing behavior for modern web."
keywords: Validation status
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: ValidationStatus
---

# Enumeration ValidationStatus

`ValidationStatus` describes the outcome of a validation process on a field.

<div class="sample-code-prefix template2"></div>
   >- JavaScript
   >
>
```javascript
enum EnumValidationStatus {
    /** 
     * Indicates that no validation has been performed.
     */
    VS_NONE = 0,
    /** 
     * Indicates that the validation process was completed successfully.
     */
    VS_SUCCEEDED = 1,
    /** 
     * Indicates that the validation process failed.
     */
    VS_FAILED = 2
}
```