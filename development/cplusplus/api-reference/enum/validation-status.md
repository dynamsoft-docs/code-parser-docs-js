---
layout: default-layout
title: ValidationStatus - Dynamsoft Code Parser SDK C++ Edition Enumeration
description: This page shows the ValidationStatus Enumeration of Dynamsoft Code Parser SDK C++ Edition.
keywords: ValidationStatus, Enumeration
needAutoGenerateSidebar: false
needGenerateH3Content: false
---

# ValidationStatus Enumeration

Describes the validation status for a parsed field.

## Declarations

```cpp
typedef enum ValidationStatus
{
    VS_NONE,
    VS_SUCCEEDED,
    VS_FAILED
} ValidationStatus;
```

## Members

| Member | Description |
| ------ | ----------- |
| VS_NONE | The field has no validation specified. |
| VS_SUCCEEDED | The validation for the field has been succeeded. |
| VS_FAILED | The validation for the field has been failed. |
