---
layout: default-layout
title: Release Notes v1.x - Dynamsoft Code Parser JavaScript SDK
description: This is the release notes page for Dynamsoft Code Parser JavaScript SDK v1.x.
keywords: release notes, javascript
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# Release Notes for JavaScript SDK - 1.x

## 1.1.0 (07/18/2022)

### Add

* Add `CF_AADHAAR` to EnumCodeFormat.
* Add `RIT_AADHAAR` to EnumResultInfoType.
* Add some new enums to [EnumErrorCode](../api-reference/enum/EnumErrorCode.md).

### Change

* Change `CF_DL_AAMVA_ANSI` to `CF_DL_AAMVA`.
* Change `RIT_DRIVER_LICENSE_INFO` to `RIT_DRIVER_LICENSE_AAMVA` and `RIT_DRIVER_LICENSE_SOUTH_AFRICA`.
* Change `RIT_PERSONAL_ID_INFO` to `RIT_PERSONAL_ID`.
* Change `RIT_VDSNC_INFO` to `RIT_VDSNC`.

## 1.0.2 (06/08/2022)

### New

* New property `license` to control license of DCP.
* New property `engineResourcePath` to specify the path of DCP WASM engine.
* New `loadWasm()` to `CodeParser` to load and compile the WASM.
* New method `createInstance()` to `CodeParser` to create a CodeParser instance.
* New method `destroyContext()` to `CodeParser` to destroy the CodeParser instance in WASM.
* New method `setCodeFormat()` to `CodeParser` to set what type of code you want to parse.
* New method `parseData()` to `CodeParser` to parse code.
* New method `setCryptoPyblicKey()` to `CodeParser` to set a public key if code parsing needs.
* New method `setCertificate()` to `CodeParser` to set a certificate if code parsing needs.
