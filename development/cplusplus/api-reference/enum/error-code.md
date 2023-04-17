---
layout: default-layout
title: ErrorCode - Dynamsoft Code Parser SDK C++ Edition Enumeration
description: This page shows the ErrorCode Enumeration of Dynamsoft Code Parser SDK C++ Edition.
keywords: ErrorCode, Enumeration
needAutoGenerateSidebar: false
needGenerateH3Content: false
---

# ErrorCode Enumeration

Describes the mapping status for a parsed field.

## Declarations

```cpp
typedef enum ErrorCode
{
    EC_OK,
    //other members
} ErrorCode;
```

## Members

| Member | Description |
| ------ | ----------- |
| EC_OK | Successful. |
| EC_FILE_NOT_FOUND | The file is not found. |
| EC_JSON_PARSE_FAILED | Failed to parse JSON string. |
| EC_JSON_TYPE_INVALID | The value type is invalid. |
| EC_JSON_KEY_INVALID | The key is invalid. |
| EC_JSON_VALUE_INVALID | The value is invalid or out of range. |
| EC_JSON_NAME_KEY_MISSING | The mandatory key "Name" is missing. |
| EC_JSON_NAME_VALUE_DUPLICATED | The value of the key "Name" is duplicated. |
| EC_TEMPLATE_NAME_INVALID | The template name is invalid. |
| EC_NO_LICENSE | No license specified. |
| EC_LICENSE_BUFFER_FAILED | Failed to read or write license buffer. |
| EC_LICENSE_SYNC_FAILED | Failed to synchronize license info with License Server. |
| EC_DEVICE_NOT_MATCH | Device does not match with license buffer. |
| EC_BIND_DEVICE_FAILED | Failed to bind device. |
| EC_LICENSE_CLIENT_DLL_MISSING | The license client dll is missing. |
| EC_TRIAL_LICENSE | Using a trial license. |
| EC_FAILED_TO_REACH_DLS | Failed to reach License Server. |
| EC_RESOURCE_PATH_NOT_EXIST | The resource path does not exist. |
| EC_RESOURCE_LOAD_FAILED | The full code string is empty. |
| EC_CODE_SPECIFICATION_NOT_FOUND | The code specification is not found. |
| EC_FULL_CODE_EMPTY | The full code string is empty. |
| EC_FULL_CODE_PREPROCESS_FAILED | Failed to preprocess the full code string. |
| EC_ZA_DL_LICENSE_INVALID | The license for parsing South Africa Driver License is invalid. |
| EC_AAMVA_DL_ID_LICENSE_INVALID | The license for parsing North America DL/ID is invalid. |
| EC_AADHAAR_LICENSE_INVALID | The license for parsing Aadhaar is invalid. |
| EC_MRTD_LICENSE_INVALID | The license for parsing Machine Readable Travel Documents is invalid. |
| EC_VIN_LICENSE_INVALID | The license for parsing Vehicle Identification Number is invalid. |
| EC_CUSTOMIZED_CODE_TYPE_LICENSE_INVALID | The license for parsing customized code type is invalid. |
