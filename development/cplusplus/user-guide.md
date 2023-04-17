---
layout: default-layout
title: User Guide - Dynamsoft Code Parser SDK C++ Edition
description: This is the user guide of Dynamsoft Code Parser SDK C++ Edition.
keywords: user guide, c++
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Getting Started with C++ Edition

In this guide, you will learn step by step on how to build a code parsing application with Dynamsoft Code Parser SDK using C++ language.

## Requirements

- Operating System:
  - Windows 7, 8, 10, 11, 2003, 2008, 2008 R2, 2012, 2016, 2019, 2022
  - Linux x64: Ubuntu 14.04.4+ LTS, Debian 8+, etc

- Developing Tool
  - Visual Studio 2008 or above
  - G++ 5.4+  

>Note:
>Dynamsoft Code Parser provides both online and offline license options. The online license option might not work in an environment that doesn't have network connection. In such case, you can get an offline trial license key via <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=guide&product=dcp&package=desktop" target="_blank">Customer Portal</a> or by <a href="https://www.dynamsoft.com/company/contact/" target="_blank">contacting us</a>.

## Installation

If you haven't downloaded the SDK yet, download the `C/C++ Package` now from <a href="https://www.dynamsoft.com/code-parser/downloads/?utm_source=docs" target="_blank">Dynamsoft website</a> and unpack the package into the directory of your choice.
>For this tutorial, we unpack it to `[INSTALLATION FOLDER]`, change it to your unpacking path for the following content.

## Build Your First Application

Let's start by creating a console application which demonstrates how to use the minimum code to get the human-readable information from the code string.  
> You can <a href="https://github.com/Dynamsoft/code-parser-cpp-samples/blob/main/samples/HelloWorld.cpp" target="_blank">download the entire source code here</a>.

### Create a New Project

#### For Windows

1. Open Visual Studio. Go to File > New > Project, create a new Empty Project and set Project name as `DCPSample`.

2. Add a new source file named `DCPSample.cpp` into the project.

#### For Linux/ARM/Mac

1. Create a new source file named `DCPSample.cpp` and place it into the folder `[INSTALLATION FOLDER]/Samples`.

### Include the Library

1. Add headers and libs in `DCPSample.cpp`.

    ```cpp
    #include<iostream>
    #include "[INSTALLATION FOLDER]/Include/DynamsoftCodeParser.h"
    #include "[INSTALLATION FOLDER]/Include/DynamsoftCore.h"
    #include "[INSTALLATION FOLDER]/Include/DynamsoftLicense.h"
    using namespace std;
    using namespace dynamsoft::dcp;
    using namespace dynamsoft::license;
    #if defined(_WIN64) || defined(_WIN32)
        #ifdef _WIN64
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftCodeParserx64.lib")
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftCorex64.lib")
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftLicensex64.lib")
        #else
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x86/DynamsoftCodeParserx86.lib")
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x86/DynamsoftCorex86.lib")
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x86/DynamsoftLicensex86.lib")
        #endif
    #endif
    ```

### Initialize a Code Parser Instance

1. Initialize the license key.

    ```cpp
    int errorCode = 0;
    char errorBuf[512];
    errorCode = CLicenseManager::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
    if (errorCode != EC_OK)
    {
        // Add your code for license error processing;
        cout << errorBuf << endl;
    }
    ```

    >Please replace `YOUR-LICENSE-KEY` with a valid DCP licensekey. There are two ways to obtain one:
    >- Search `InitLicense` and find the license from `[INSTALLATION FOLDER]/Samples/HelloWorld/HelloWorld.cpp`.
    >- Request a trial license from <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=guide&product=dcp&package=desktop" target="_blank">Customer Portal</a>.

2. Create an instance of Dynamsoft Code Parser.

    ```cpp
    CCodeParser* dcp = new CCodeParser();
    ```

### Parse and Output Results

1. Parse a code string.

    ```cpp
    int errorCode = -1;
    //get codeString and codeStringLenght somewhere else
    CParsedResultItem* dcpResult = dcp->Parse(codeString, codeStringLenght, "", &errorCode);
    ```

2. Get and output results.

    ```cpp
    if (dcpResult != NULL)
    {
        cout << "CodeType: " << dcpResult->GetCodeType() << endl;
        cout << "Value of A-SPECIFIC-FIELD-NAME: " << dcpResult->GetFieldValue("A-SPECIFIC-FIELD-NAME") << endl;
    }
    ```

    >Please replace `A-SPECIFIC-FIELD-NAME` to a specific field name based on the code string you are parsing. Check out [Supported Code Types and Fields]({{ site.code_types }}) for details.

### Release Allocated Memory

1. Release the allocated memory for the barcode results.

    ```cpp
    if (dcpResult != NULL)           
        delete dcpResult;
    ```

2. Release the allocated memory for the instance.

    ```cpp
    if (dcp != NULL)           
        delete dcp;
    ```

>Note:  
Please change all `[INSTALLATION FOLDER]` in above code snippet to your unpacking path.

### Build and Run the Project

#### For Windows

1. In Visual Studio, set the solution to build as Release\|x64.

2. Build the project to generate program `DCPSample.exe`.

3. Copy **ALL** `*.dll` files under `[INSTALLATION FOLDER]\Lib\Windows\x64` to the same folder as the `DCPSample.exe`.

4. Run the program `DCPSample.exe`.

>The SDK supports both x86 and x64, please set the platform based on your needs.

#### For Linux

1. Open a terminal and change to the target directory where `DCPSample.cpp` located in. Build the sample:

    ```bash
    g++ -o DCPSample DCPSample.cpp -lDynamsoftCodeParser -lDynamsoftCore -lDynamsoftLicense -L ../Lib/Linux -Wl,-rpath=../Lib/Linux -std=c++11
    ```

2. Run the program `DCPSample`.

    ```bash
    ./DCPSample
    ```

> You can <a href="https://github.com/Dynamsoft/code-parser-cpp-samples/blob/main/samples/HelloWorld.cpp" target="_blank">download the entire source code here</a>.
