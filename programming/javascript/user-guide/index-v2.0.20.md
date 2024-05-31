---
layout: default-layout
title: User Guide - Dynamsoft Code Parser for JavaScript v2.x
description: This is the user guide page of Dynamsoft Code Parser for JavaScript SDK v2.x.
keywords: user guide, javascript
breadcrumbText: User Guide
noTitleIndex: true
needAutoGenerateSidebar: true
needGenerateH3Content: true
---

<!--The original doc is hosted here => https://github.com/dynamsoft-docs/code-parser-docs-js/programming/javascript/user-guide/index.md -->

# Dynamsoft Code Parser for Your Website

Dynamsoft Code Parser is designed to parse data strings (usually encrypted in barcodes, machine readable zones, etc.) into human-readable information. The JavaScript edition is based on WebAssembly and offers great speed and accuracy. With its well-designed API, you can equip your web pages with a code parser with just a few lines of code.

In this guide, you will learn step by step on how to integrate the SDK into your website.

<span style="font-size:20px">Table of Contents</span>

- [Dynamsoft Code Parser for Your Website](#dynamsoft-code-parser-for-your-website)
  - [Hello World](#hello-world)
    - [About the code](#about-the-code)
    - [Run the example](#run-the-example)
  - [Building your own page](#building-your-own-page)
    - [Include the SDK](#include-the-sdk)
      - [Use a CDN](#use-a-cdn)
      - [Host the SDK yourself](#host-the-sdk-yourself)
    - [Configure the SDK](#configure-the-sdk)
      - [Specify the license](#specify-the-license)
      - [Specify the location of the "engine" files (optional)](#specify-the-location-of-the-engine-files-optional)
    - [Interact with the SDK](#interact-with-the-sdk)
      - [Load the specification for parsing](#load-the-specification-for-parsing)
      - [Create a `CodeParser` object](#create-a-codeparser-object)
      - [Start Parsing](#start-parsing)
  - [System requirements](#system-requirements)
  - [Release notes](#release-notes)
  - [API Documentation](#api-documentation)

## Hello World

Dynamsoft Code Parser is designed to work both independently and alongside another functional product such as [Dynamsoft Barcode Reader](https://www.dynamsoft.com/barcode-reader/overview/) or [Dynamsoft Label Recognizer](https://www.dynamsoft.com/label-recognition/overview/).

Let's start with the "Hello World" example of the SDK which demonstrates how to use the minimum code to enable a web page to parse an existing string into human-readable fields.

The complete code of the "Hello World" example is shown below:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <script src="https://cdn.jsdelivr.net/npm/dynamsoft-core@3.0.30/dist/core.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/dynamsoft-license@3.0.20/dist/license.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/dynamsoft-code-parser@2.0.20/dist/dcp.js"></script>
</head>
<body>
<div
    id="results"
    style="width: 100%; min-height: 10vh; font-size: 3vh; overflow: auto"
></div>
<script>
    let passportMRZStr =
    "P<D<<ADENAUER<<KONRAD<HERMANN<JOSEPH<<<<<<<<1234567897D<<7601059M6704115<<<<<<<<<<<<<<<2";

    let parser = null;
    const resultsContainer = document.querySelector("#results");
    (async function () {
    Dynamsoft.License.LicenseManager.initLicense(
        "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9"
    );
    await Dynamsoft.DCP.CodeParserModule.loadSpec("MRTD_TD3_PASSPORT");
    parser = await Dynamsoft.DCP.CodeParser.createInstance();

    let parsedResultItem = await parser.parse(passportMRZStr);

    let parsedResult = JSON.parse(parsedResultItem.jsonString);
    let parsedLines = parsedResult.ResultInfo;
    resultsContainer.innerHTML = "";
    parsedLines.forEach((element) => {
        resultsContainer.innerHTML +=
        "<hr><strong>" + element.FieldName + "</strong><br /><hr>";
        element.ChildFields[0].forEach((childElement) => {
        resultsContainer.innerHTML +=
            "  " +
            `${childElement.FieldName}: <strong>${childElement.Value}</strong><br />`;
        });
    });
    })();
</script>
</body>
</html>

```

### About the code

- `let passportMRZStr = "P<D<<ADENAUER<<KONRAD<HERMANN<JOSEPH<<<<<<<<1234567897D<<7601059M6704115<<<<<<<<<<<<<<<2";`: this string is a fabricated example that conforms to the `MRTD_TD3_PASSPORT` specification. In a practical scenario, such a string would be provided by an external software. For instance, it could be the textual output of "Dynamsoft Label Recognizer" following the scanning of a passport.

- `Dynamsoft.License.LicenseManager.initLicense()`: initializes the license using a license key string.

- `Dynamsoft.DCP.CodeParserModule.loadSpec("MRTD_TD3_PASSPORT")`: preloads the `MRTD_TD3_PASSPORT` specification which helps with the parsing of the string.

- `Dynamsoft.DCP.CodeParser.createInstance()`: initializes the `parser` variable by creating an instance of the `CodeParser` class.

- `parser.parse(passportMRZStr)`: parses the sample string and returns a structured result item.

### Run the example

Create a text file called "code-parser.html", fill it with the code above and save it. After that, open the example page in your browser, and you will see the parsed result displayed on the page.

> NOTE:
> 
> The sample code requires the following to run:
> 
> 1. Internet connection
> 2. [A supported browser](#system-requirements)

Please note:

- Although the page should work properly when opened directly as a file ("file:///"), it's recommended that you deploy it to a web server and access it via HTTPS.
- On first use, you need to wait a few seconds for the SDK to initialize.
- The license "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" used in this sample is an online license good for 24 hours and requires network connection to work. To test the SDK further, you can request a 30-day trial license via the <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=guide&architecture=dcv&product=dcp&package=js" target="_blank">Request a Trial License</a> link.
 

If the test doesn't go as expected, you can [contact us](https://www.dynamsoft.com/company/customer-service/#contact).

## Building your own page

### Include the SDK

#### Use a CDN

The simplest way to include the SDK is to use either the [jsDelivr](https://jsdelivr.com/) or [UNPKG](https://unpkg.com/) CDN. The "hello world" example above uses **jsDelivr**.

* jsDelivr

    ```html
    <script src="https://cdn.jsdelivr.net/npm/dynamsoft-core@3.0.30/dist/core.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/dynamsoft-license@3.0.20/dist/license.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/dynamsoft-code-parser@2.0.20/dist/dcp.js"></script>
    ```

* UNPKG  

    ```html
    <script src="https://unpkg.com/dynamsoft-core@3.0.30/dist/core.js"></script>
    <script src="https://unpkg.com/dynamsoft-license@3.0.20/dist/license.js"></script>
    <script src="https://unpkg.com/dynamsoft-code-parser@2.0.20/dist/dcp.js"></script>
    ```

#### Host the SDK yourself

Besides using the CDN, you can also download the SDK and host its files on your own website / server before including it in your application.

Options to download the SDK:

- From the website

  Sign in the [Customer Portal](https://www.dynamsoft.com/customer/index?utm_source=docs&product=dcp) and Download the JavaScript ZIP package

* yarn

    ```cmd
    yarn add dynamsoft-core@3.0.30 --save
    yarn add dynamsoft-license@3.0.20 --save
    yarn add dynamsoft-code-parser@2.0.20 --save
    ```

* npm

    ```cmd
    npm install dynamsoft-core@3.0.30 --save
    npm install dynamsoft-license@3.0.20 --save
    npm install dynamsoft-code-parser@2.0.20 --save
    ```

Depending on how you downloaded the SDK and where you put it, you can typically include it like this:

```html
<!-- Upon extracting the zip package into your project, you can generally include it in the following manner -->
<script src="./dynamsoft/distributables/dynamsoft-core@3.0.30/dist/core.js"></script>
<script src="./dynamsoft/distributables/dynamsoft-license@3.0.20/dist/license.js"></script>
<script src="./dynamsoft/distributables/dynamsoft-code-parser@2.0.20/dist/dcp.js"></script>
```

or

```html
<script src="./node_modules/dynamsoft-core/dist/core.js"></script>
<script src="./node_modules/dynamsoft-license/dist/license.js"></script>
<script src="./node_modules/dynamsoft-code-parser/dist/dcp.js"></script>
```

or

```typescript
import { LicenseManager } from "dynamsoft-license";
import { type ParsedResultItem, CodeParser } from 'dynamsoft-code-parser';
```

### Configure the SDK

Before using the SDK, you need to configure a few things.

#### Specify the license

The SDK requires a license to work, use the method `Dynamsoft.License.LicenseManager.initLicense` to specify the license key.

```javascript
//You can visit https://www.dynamsoft.com/customer/license/trialLicense?utm_source=github&product=dcp&package=js to get your own trial license good for 30 days. 
Dynamsoft.License.LicenseManager.initLicense("YOUR-LICENSE-KEY");
```

#### Specify the location of the "engine" files (optional)

This is usually only required with frameworks like Angular or React, etc. where the referenced JavaScript files such as `core.js`, `dcp.js` are compiled into another file.

The purpose is to tell the SDK where to find the engine files (\*.worker.js, \*.wasm.js and \*.wasm, etc.). The API is called `Dynamsoft.Core.CoreModule.engineResourcePaths`:

```javascript
//The following code uses the jsDelivr CDN, feel free to change it to your own location of these files
Dynamsoft.Core.CoreModule.engineResourcePaths.core = "https://cdn.jsdelivr.net/npm/dynamsoft-core@3.0.30/dist/";
Dynamsoft.Core.CoreModule.engineResourcePaths.license = "https://cdn.jsdelivr.net/npm/dynamsoft-license@3.0.20/dist/";
Dynamsoft.Core.CoreModule.engineResourcePaths.dcp = "https://cdn.jsdelivr.net/npm/dynamsoft-code-parser@2.0.20/dist/";
```

### Interact with the SDK

#### Load the specification for parsing

The SDK requires the specification of the code string to parse it. If we are going to parse the MRZ strings found on passports, we need the specification "MRTD\_TD3\_PASSPORT". 

```javascript
await Dynamsoft.DCP.CodeParserModule.loadSpec("MRTD_TD3_PASSPORT");
```

#### Create a `CodeParser` object

Then we create a `CodeParser` object.

```javascript
let parser = null;
try {
    parser = await Dynamsoft.DCP.CodeParser.createInstance();
} catch (ex) {
    console.error(ex);
}
```

Tip: When creating a `CodeParser` object within a function which may be called more than once, it's best to use a "helper" variable to avoid double creation such as `helperParser` in the following code

```javascript
let helperParser = null;

function foo() {
    try {
        const parser = await (helperParser = helperParser || Dynamsoft.DCP.CodeParser.createInstance());
    } catch (ex) {
        console.error(ex);
    }
}
```

#### Start Parsing

The method `parse()` takes data in two formats: `Uint8Array` and `string`. `Uint8Array` refers to the binary data produced by another software such as Dynamsoft Barcode Reader.

```javascript
let parsedResultItem = await parser.parse("THE-CODE-TO-PARSE");
```

## System requirements

The SDK requires the following features to work:

- Secure context (HTTPS deployment)

  When deploying your application / website for production, make sure to serve it via a secure HTTPS connection. This is required because Dynamsoft License requires a secure context to work.

- `WebAssembly`, `Blob`, `URL`/`createObjectURL`, `Web Workers`

  The above four features are required for the SDK to work.

The following table is a list of supported browsers based on the above requirements:

  | Browser Name | Version |
  | :----------: | :-----: |
  |    Chrome    |  v78+   |
  |   Firefox    |  v62+   |
  |    Safari    |  v14+   |
  |     Edge     |  v79+   |

Apart from the browsers, the operating systems may impose some limitations of their own that could restrict the use of the SDK.

## Release notes

Learn what are included in each release at [Dynamsoft Code Parser JavaScript Edition Release Notes](https://www.dynamsoft.com/code-parser/docs/web/programming/javascript/release-notes/?ver=latest).

## API Documentation

For more information about the APIs of the SDK, read [Dynamsoft Code Parser JavaScript Edition API Reference](https://www.dynamsoft.com/code-parser/docs/web/programming/javascript/api-reference/?ver=2.0.20).
