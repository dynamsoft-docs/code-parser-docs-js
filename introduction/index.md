---
layout: default-layout
title: Introduction - Dynamsoft Code Parser SDK
description: This is the main page of Dynamsoft Code Parser Introduction. 
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Introduction to Dynamsoft Code Parser

When working with IDs, driver licenses, or sometimes even general barcodes, you may encounter results (usually as a plain string) that are "unreadable" but contain all the useful information you need. Dynamsoft Code Parser (DCP) is an SDK designed for parsing these types of results into human-readable information.

For the initial release, DCP is only available for web applications as "DCP JavaScript Edition". Based on JavaScript and WebAssembly, DCP JavaScript Edition can run in all major modern browsers on all major platforms.

## Usage Scenarios

* AAMVA driver's license

Countries covered: USA, Canada.

All versions of the AAMVA Driver's License/Identification Specification used in the US and Canada are supported. The PDF417 barcodes on driver licenses with magnetic stripes, which follow the AAMVA Magnetic Stripe standard, are capable to get parsed.

* South African driver's license

The fields parsed from the South African driver's license are currently limited to some personal information, while the full information will be parsed in a future release.

* Aadhaar Card in India

The normal QR codes or Secure QR codes on eAadhaar, Aadhaar Letter and Aadhaar PVC Card are all capable to be parsed. 

* Coming soon

Future releases will support more scenarios such as international COVID-19 vaccination certificates, machine readable zones and ID parsing.

## Supported Platforms

| Platforms | Languages                 |
|-----------|---------------------------|
| <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACIAAAAiCAYAAAA6RwvCAAAACXBIWXMAAAsSAAALEgHS3X78AAADPklEQVRYhZ1XvY4TMRD+JqKkCG+QDiQKFtEgUWR5AKQtKfMAFCkpt6RMTZXyKpR7AnIFJSKRDonuUlJBkCjoBs3e55zXa3udG2mlxPbMfPNvi6qilERkBqABUAOw388C1j2AA4AtgI2qHkplT0oOiUgtIib8hiDs908A1wAe8bvm2pZnbozHeIuQmEdSH4CKgs2yBYAp1+330f3n2pTnlt7/heehKqsrA2JpOAG0gcIZQdQRnpp7swBgS1nLs4AAWFPgwApat8oYYEq3kfWKMtdFQAhi53shYvFgLxKimMemlD0AEwtHUhG9scjF2suhgVc8MMcwTKfyFRFz3TcAXwH8jeS1CXgK4EtRFQCvAHyn0pAeAngB4Lmq7jr9HhCz9geAi4Tg9yzPdSGQd1T4IbH/FsATVb0tby/2Ftdc7HvVUBCeLjlLc6ko9g5oKQiPL5q0sVyasG3PrSVn3FyP7KfIddkUmcy5YZhwdlyqaiypHFUsu/sAmaU2qfPSMDzwZkeOXDzPIlVdswjGwNYTIh6ztgrLUESWIqIishORluUfs3rMANM9E86AN4ne4egzgNeO0VxKS90ocFeDKePurgG5cDuDjOe3A3I1cn7unbE5szEvsJwXntCKgBry7Als4xpXAkxXQlpQhoMewnAlS5reaei1gxt4/nUiKOPOI8lG5vWZ2BCLTuhMg1tSljI3Gm+/W0g2nVzDo4XJO0aBt06GTOi2aMZ7lOoHWwo8i5jEju9UVUsmU86CJnHZmZbkWMKTvbCClmbzxClMXJZ6sb4PiC40bDhXORfTlfvEmc3IPAmpYQvolXN3H+GV/xOAjwD+JQS8pPcuON5XuOsdFtrkTOkpvD2/ZZKf7jYTWmwbv6gsRWbB43Du0LIpp/go8bwZvhKRUzMM61xzfYHxbSPrm3PL2JtfXVsIN8cuz1Vsn50xW3kj8pqU1dHnhNfc2mBtFpZx7m0UnGs7j55TYr7SyOw5lbHH3+bAeE/XKoc0+uTk3ipscFxbhUb4ylIgBjmSiGHsEe4qZ6F9Tx3dyMgqjYArTSp3nbQ/XYXw+1P6xPCUR8N1bpab1d1sYk7Yon2jz1DyW1c13n7OqOI/jmBGl5fJ/S8AAAAASUVORK5CYII=" alt="web"> Web       | JavaScript                |

> Future versions will support more platforms, such as Android/Mobile, etc.

## How to use

There are mainly four steps to use a CodeParser, the following takes the JavaScript edtion for example:

1. Initialize license

    Before you begin, you must set up a license that allows you to use DCP. You can visit https://www.dynamsoft.com/customer/license/trialLicense?utm_source=github&product=dcp&package=js to get your own trial license good for 30 days.

2. Create Code Parser instance

    With a license in place, you can create a Code Parser instance to use. For the JavaScript edition, the SDK is designed to download and compile the WASM resources (the engine files) automaticly before creating an instance.

3. Set code format

    The 2nd last step is to set the code format (see [EnumCodeFormat](../development/javascript/api-reference/enum/EnumCodeFormat.md)) of the document image that you want to get information from.

4. Parse code

    Lastly, call the method `parseData()` to do the actual parsing and get results in a specific format (see [EnumResultInfoType](../development/javascript/api-reference/enum/EnumResultInfoType.md)).

<!-- > If your input code requires a public key or certificate to help with parsing, please set it up beforehand. For example, a public key needs to be set before parsing a South African driver's license, and a certificate is often required when parsing a COVID-19 vaccination certificate. -->

## Next Step

Learn how to use DCP to add code parsing capabilities to your web application:

* [JavaScript (Web)]({{site.javascript}})
