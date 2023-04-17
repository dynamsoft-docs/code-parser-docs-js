---
layout: default-layout
title: MappingStatus - Dynamsoft Code Parser SDK C++ Edition Enumeration
description: This page shows the MappingStatus Enumeration of Dynamsoft Code Parser SDK C++ Edition.
keywords: MappingStatus, Enumeration
needAutoGenerateSidebar: false
needGenerateH3Content: false
---

# MappingStatus Enumeration

Describes the mapping status for a parsed field.

## Declarations

```cpp
typedef enum MappingStatus
{
    MS_NONE,
    MS_SUCCEEDED,
    MS_FAILED
} MappingStatus;
```

## Members

| Member | Description |
| ------ | ----------- |
| MS_NONE | The field has no mapping specified. |
| MS_SUCCEEDED | Find a mapping for the field value. |
| MS_FAILED | Failed to find a mapping for the field value. |
