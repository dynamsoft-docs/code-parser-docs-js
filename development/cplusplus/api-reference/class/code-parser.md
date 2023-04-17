---
layout: default-layout
title: CCodeParser Class - Dynamsoft Code Parser SDK C++ Edition API Reference
description: This page shows CCodeParser Class of Dynamsoft Code Parser SDK C++ Edition.
keywords: CCodeParser, api reference, c++
needAutoGenerateSidebar: true
---

# CCodeParser Class

  | Method               | Description |
  |----------------------|-------------|
  | [`CCodeParser`](#constructor) | Default constructor of `CCodeParser` object.|
  | [`~CCodeParser`](#destructor) | Destructor of `CCodeParser` object.|
  | [`GetVersion`](#getversion) | Get version information of SDK.|
  | [`InitSettingsFromFile`](#initsettingsfromfile)  | Initialize runtime settings with the settings in a given JSON file. |
  | [`InitSettings`](#initsettings) | Initialize runtime settings with the settings in a given JSON string. |
  | [`Parse`](#parse) | Parses code data for readable results. |
  | [`ResetSettings`](#resetsettings) | Reset runtime settings to default. |

## CCodeParser {#constructor}

Default constructor of a `CCodeParser` object.

```cpp
dynamsoft::dcp::CCodeParser::CCodeParser()
```

## ~CCodeParser {#destructor}

Destructor of a `CCodeParser` object.

```cpp
dynamsoft::dcp::CCodeParser::~CCodeParser()
```

## GetVersion

Get version information of SDK.

```cpp
static const char* dynamsoft::dcp::CCodeParser::GetVersion()
```

**Return Value**

The version information string.

**Code Snippet**

```cpp
const char* versionInfo = dynamsoft::dcp::CCodeParser::GetVersion();
```

## Parse

Parses code data for human-readable results.

```cpp
CParsedResultItem* dynamsoft::dcp::CCodeParser::Parse(const unsigned char* pData, int length, const char* taskSettingName="", int* errorCode = NULL)
```

**Parameters**

`[in] pData` The array of bytes which contain the code string.  
`[in] length` The length of the code string bytes.  
`[in] taskSettingName`<sub>Optional</sub> The name of [`CodeParserTaskSetting`]({{site.parameters}}code-parser-task-setting-options.html) which defines the settings used for code parsing.
`[in,out] errorCode`<sub>Optional</sub> The error code.

**Return Value**

Returns [`CParsedResultItem`](parsed-result-item.md) which stores the human-readable results.

**Code Snippet**


```cpp
char errorBuf[512];
dynamsoft::dcp::CCodeParser::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CCodeParser* dcp = new CCodeParser();
//get code string data (pData, length) somewhere else
CParsedResultItem* dcpResult = dcp->Parse(pData, length);
cout << "CodeType: " << dcpResult->GetCodeType() << endl;
delete dcpResult;
delete dcp;
```

## ResetSettings

Reset all parameters to default values.

```cpp
int dynamsoft::dcp::CCodeParser::ResetSettings()
```

**Return Value**

Returns error code.  

**Code Snippet**


```cpp
char errorBuf[512];
dynamsoft::dcp::CCodeParser::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CCodeParser* dcp = new CCodeParser();
dcp->ResetSettings();
dcp->InitSettingsFromFile("PATH-TO-YOUR-SETTING-FILE", errorBuf, 512);
// Do something with dcp object
delete dcp;
```

## InitSettingsFromFile

Initialize settings from a given file.

```cpp
int dynamsoft::dcp::CCodeParser::InitSettingsFromFile(const char* filePath, char errorMsgBuffer[] = NULL, int errorMsgBufferLen = 0)
```

**Parameters**

`[in] filePath` The path of the settings file.  
`[in,out] errorMsgBuffer`<sub>Optional</sub> The buffer is allocated by caller and the recommended length is 512. The error message will be copied to the buffer.  
`[in] errorMsgBufferLen`<sub>Optional</sub> The length of the allocated buffer.

**Return Value**

Returns error code.

**Code Snippet**

```cpp
char errorBuf[512];
dynamsoft::dcp::CCodeParser::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CCodeParser* dcp = new CCodeParser();
dcp->ResetSettings();
dcp->InitSettingsFromFile("PATH-TO-YOUR-SETTING-FILE", errorBuf, 512);
// Do something with dcp object
delete dcp;
```

## InitSettings

Initialize settings from a given string.

```cpp
int dynamsoft::dcp::CCodeParser::InitSettings (const char* content, char errorMsgBuffer[] = NULL, int errorMsgBufferLen = 0)
```

**Parameters**

`[in] content` A JSON string that represents the content of the settings.
`[in,out] errorMsgBuffer`<sub>Optional</sub> The buffer is allocated by caller and the recommended length is 512. The error message will be copied to the buffer.  
`[in] errorMsgBufferLen`<sub>Optional</sub> The length of the allocated buffer.

**Return Value**

Returns error code.

**Code Snippet**


```cpp
char errorBuf[512];
dynamsoft::dcp::CCodeParser::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CCodeParser* dcp = new CCodeParser();
dcp->ResetSettings();
dcp->InitSettings("YOUR-SETTING-STRING", errorBuf, 512);
// Do something with dcp object
delete dcp;
```
