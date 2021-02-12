---
title: GetConsoleOutputCP function
description: Retrieves the output code page used by the console associated with the calling process.
author: miniksa
ms.author: miniksa
ms.topic: article
keywords: console, character mode applications, command line applications, terminal applications, console api
f1_keywords:
- consoleapi/GetConsoleOutputCP
- wincon/GetConsoleOutputCP
- GetConsoleOutputCP
MS-HAID:
- '\_win32\_getconsoleoutputcp'
- 'base.getconsoleoutputcp'
- 'consoles.getconsoleoutputcp'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/desktop'
ms.assetid: c23706c7-ce17-4825-a494-20ca44534d45

topic_type:
- apiref
api_name:
- GetConsoleOutputCP
api_location:
- Kernel32.dll
- API-MS-Win-Core-Console-l1-1-0.dll
- KernelBase.dll
- API-MS-Win-DownLevel-Kernel32-l1-1-0.dll
- MinKernelBase.dll
api_type:
- DllExport
---

# GetConsoleOutputCP function

Retrieves the output code page used by the console associated with the calling process. A console uses its output code page to translate the character values written by the various output functions into the images displayed in the console window.

## Syntax

```C
UINT WINAPI GetConsoleOutputCP(void);
```

## Parameters

This function has no parameters.

## Return value

The return value is a code that identifies the code page. For a list of identifiers, see [Code Page Identifiers](/windows/win32/intl/code-page-identifiers).

If the return value is zero, the function has failed. To get extended error information, call [**GetLastError**](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

## Remarks

A code page maps 256 character codes to individual characters. Different code pages include different special characters, typically customized for a language or a group of languages. To retrieve more information about a code page, including it's name, see the [**GetCPInfoEx**](/windows/win32/api/winnls/nf-winnls-getcpinfoexa) function.

To set a console's output code page, use the [**SetConsoleOutputCP**](setconsoleoutputcp.md) function. To set and query a console's input code page, use the [**SetConsoleCP**](setconsolecp.md) and [**GetConsoleCP**](getconsolecp.md) functions.

## Requirements

| &nbsp; | &nbsp; |
|-|-|
| Minimum supported client | Windows 2000 Professional \[desktop apps only\] |
| Minimum supported server | Windows 2000 Server \[desktop apps only\] |
| Header | ConsoleApi.h (via WinCon.h, include Windows.h) |
| Library | Kernel32.lib |
| DLL | Kernel32.dll |

## See also

[Console Code Pages](console-code-pages.md)

[Console Functions](console-functions.md)

[**GetConsoleCP**](getconsolecp.md)

[**SetConsoleCP**](setconsolecp.md)

[**SetConsoleOutputCP**](setconsoleoutputcp.md)