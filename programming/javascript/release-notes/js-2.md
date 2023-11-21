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

## 2.0.20 (12/xx/2023)

### Changelog

* In this version, `DynamsoftCodeParser` SDK has been revamped to integrate with the `DynamsoftCaptureVision (DCV)` architecture, which is newly established to aggregate the features of multiple functional products powered by Dynamsoft. The features are designed to be pluggable, customizable and interactable. In addition, the functional products share the computation so that their processing speed is much higher than when they work individually.
* In this version, the following code types are supported:
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

| Version 1.x                                 | Version 2.x                                       |
| ------------------------------------------- | ------------------------------------------------- |
| Dynamsoft.DCP.CodeParser.license            | Dynamsoft.License.LicenseManager.initLicense()    |
| Dynamsoft.DCP.CodeParser.engineResourcePath | Dynamsoft.DCP.CodeParserModule.engineResourcePath |
| Dynamsoft.DCP.CodeParser.loadWasm()         | Dynamsoft.DCP.CodeParser.loadWasm()               |
| Dynamsoft.DCP.CodeParser.createInstance()   | Dynamsoft.DCP.CodeParser.createInstance()         |

* Instance API changes:

| Version 1.x      | Version 2.x   |
| ---------------- | ------------- |
| destroyContext() | dispose()     |
| setCodeFormat()  | No equivalent |
| parseData()      | parse()       |

* API added in v2.x

1. The method `initSettings()` can be used to set up a `CodeParser` instance for a parsing task.
2. The method `resetSettings()` can be used to reset a `CodeParser` instance to the default settings.
3. The property `disposed` returns whether a `CodeParser` instance has been disposed of.