---
layout: default-layout
title: Release Notes v2.x - Dynamsoft Code Parser JavaScript SDK
description: This is the release notes page for Dynamsoft Code Parser JavaScript SDK v2.x.
keywords: release notes, javascript
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# Release Notes for JavaScript SDK - 2.x

## 2.0.20 (01/19/2024)

### Changelog

* The `DynamsoftCodeParser` SDK has been revamped to integrate with the newly established [DynamsoftCaptureVision (DCV)](https://www.dynamsoft.com/capture-vision/docs/core/architecture/index.html) architecture.
* The definition of a code type is now associated with a specific coding standard. These are the supported code types:
  * [MRTD_TD1_ID]({{ site.code_types }}mrtd.html)
  * [MRTD_TD2_ID]({{ site.code_types }}mrtd.html)
  * [MRTD_TD2_VISA]({{ site.code_types }}mrtd.html)
  * [MRTD_TD3_PASSPORT]({{ site.code_types }}mrtd.html)
  * [MRTD_TD3_VISA]({{ site.code_types }}mrtd.html)
  * [VIN]({{ site.code_types }}vin.html)
  * [AAMVA_DL_ID]({{ site.code_types }}aamva-dl-id.html)
  * [AAMVA_DL_ID_WITH_MAG_STRIPE]({{ site.code_types }}aamva-dl-id.html)
  * [AADHAAR]({{ site.code_types }}aadhaar.html)
  * [SOUTH_AFRICA_DL]({{ site.code_types }}za-dl.html)

The following shows the API changes

* Static API changes:

| Version 1.x                                 | Version 2.x                                    |
| ------------------------------------------- | ---------------------------------------------- |
| Dynamsoft.DCP.CodeParser.license            | Dynamsoft.License.LicenseManager.initLicense() |
| Dynamsoft.DCP.CodeParser.engineResourcePath | Dynamsoft.Core.CoreModule.engineResourcePaths  |
| Dynamsoft.DCP.CodeParser.loadWasm()         | Dynamsoft.Core.CoreModule.loadWasm()           |
| Dynamsoft.DCP.CodeParser.createInstance()   | Dynamsoft.DCP.CodeParser.createInstance()      |

* Instance API changes:

| Version 1.x      | Version 2.x   |
| ---------------- | ------------- |
| destroyContext() | dispose()     |
| setCodeFormat()  | No equivalent |
| parseData()      | parse()       |

* API added in v2.x

1. The method `initSettings()` can be used to set up a `CodeParser` instance for a parsing task.
2. The method `resetSettings()` can be used to reset a `CodeParser` instance to the default settings.
3. The property `disposed` returns whether a `CodeParser` instance has been disposed.
