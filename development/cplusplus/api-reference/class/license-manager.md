---
layout: default-layout
title: CLicenseManager Class - Dynamsoft Code Parser SDK C++ Edition API Reference
description: This page shows CLicenseManager Class of Dynamsoft Code Parser SDK C++ Edition.
keywords: CLicenseManager, api reference, c++
needAutoGenerateSidebar: true
---


# CLicenseManager Class

```cpp
class dynamsoft::license::CLicenseManager
```

  | Method               | Description |
  |----------------------|-------------|
  | [`InitLicense`](#initlicense) | Initializes license key and activate the SDK. |
  | [`GetDeviceUUID`](#getdeviceuuid) | Gets the device uuid used for license activating. |
  | [`SetDeviceFriendlyName`](#setdevicefriendlyname) | Sets a human-readable name that identifies the device. |
  | [`SetLicenseCachePath`](#setlicensecachepath) | Sets a directory path for saving the license cache. |

## InitLicense

Initializes license key and activate the SDK.

```cpp
static int dynamsoft::license::CLicenseManager::InitLicense(const char* pLicense, char errorMsgBuffer[] = NULL, const int errorMsgBufferLen = 0)
```

**Parameters**

`[in] pLicense` The license key.  
`[in, out] errorMsgBuffer` The buffer is allocated by caller and the recommended length is 512. The error message will be copied to the buffer.  
`[in] errorMsgBufferLen` The length of allocated buffer.  

**Return Value**

Returns error code.

**Code Snippet**

```cpp
char errorBuf[512];
dynamsoft::license::CLicenseManager::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CCodeParser* dcp = new CCodeParser();
// do something with dcp object
```

## GetDeviceUUID

Gets the device uuid used for license activating.

```cpp
static int dynamsoft::license::CLicenseManager::GetDeviceUUID(int uuidGenerationMethod, char uuidBuffer[], const int uuidBufferLen)
```

**Parameters**

`[in] uuidGenerationMethod` The method used to generate the UUID.

- 1: Generates UUID with random values.
- 2: Generates UUID based on hardware info.

`[in, out] uuidBuffer` The buffer is allocated by caller and the recommended length is 36. The UUID will be copied to the buffer.  
`[in] uuidBufferLen` The length of allocated buffer.  

**Return Value**

Returns error code.

## SetDeviceFriendlyName

Sets a human-readable name that identifies the device.

```cpp
static int dynamsoft::license::CLicenseManager::SetDeviceFriendlyName(const char* name)
```

**Parameters**

`[in] name` The device alias.

**Return Value**

Returns error code.

**Code Snippet**

```cpp
char errorBuf[512];
dynamsoft::license::CLicenseManager::SetDeviceFriendlyName("My-PC");
dynamsoft::license::CLicenseManager::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CCodeParser* dcp = new CCodeParser();
// do something with dcp object
```

## SetLicenseCachePath

Sets a directory path for saving the license cache.

```cpp
static int dynamsoft::license::CLicenseManager::SetLicenseCachePath(const char* directoryPath)
```

**Parameters**

`[in] directoryPath` The directory path where to save the license cache.

**Return Value**

Returns error code.

**Code Snippet**

```cpp
char errorBuf[512];
dynamsoft::license::CLicenseManager::SetLicenseCachePath("DIRECTORY-PATH-FOR-LICENSE-CACHE");
dynamsoft::license::CLicenseManager::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CCodeParser* dcp = new CCodeParser();
// do something with dcp object
```
