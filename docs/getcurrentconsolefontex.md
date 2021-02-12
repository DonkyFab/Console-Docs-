---
title: GetCurrentConsoleFontEx function
description: See reference information about the GetCurrentConsoleFontEx function, which retrieves extended information about the currently used console font.
author: miniksa
ms.author: miniksa
ms.topic: article
keywords: console, character mode applications, command line applications, terminal applications, console api
f1_keywords:
- consoleapi3/GetCurrentConsoleFontEx
- wincon/GetCurrentConsoleFontEx
- GetCurrentConsoleFontEx
MS-HAID:
- 'base.getcurrentconsolefontex'
- 'consoles.getcurrentconsolefontex'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/desktop'
ms.assetid: 97d8e730-4110-4be5-b099-0acc1b6f8eb5

topic_type:
- apiref
api_name:
- GetCurrentConsoleFontEx
api_location:
- Kernel32.dll
api_type:
- DllExport
---

# GetCurrentConsoleFontEx function

[!INCLUDE [not-recommended-banner](./includes/not-recommended-banner.md)]

Retrieves extended information about the current console font.

## Syntax

```C
BOOL WINAPI GetCurrentConsoleFontEx(
  _In_  HANDLE               hConsoleOutput,
  _In_  BOOL                 bMaximumWindow,
  _Out_ PCONSOLE_FONT_INFOEX lpConsoleCurrentFontEx
);
```

## Parameters

*hConsoleOutput* \[in\]  
A handle to the console screen buffer. The handle must have the **GENERIC\_READ** access right. For more information, see [Console Buffer Security and Access Rights](console-buffer-security-and-access-rights.md).

*bMaximumWindow* \[in\]  
If this parameter is **TRUE**, font information is retrieved for the maximum window size. If this parameter is **FALSE**, font information is retrieved for the current window size.

*lpConsoleCurrentFontEx* \[out\]  
A pointer to a [**CONSOLE\_FONT\_INFOEX**](console-font-infoex.md) structure that receives the requested font information.

## Return value

If the function succeeds, the return value is nonzero.

If the function fails, the return value is zero. To get extended error information, call [**GetLastError**](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

[!INCLUDE [no-vt-equiv-user-priv](./includes/no-vt-equiv-user-priv.md)]

## Requirements

| &nbsp; | &nbsp; |
|-|-|
| Minimum supported client | Windows Vista \[desktop apps only\] |
| Minimum supported server | Windows Server 2008 \[desktop apps only\] |
| Header | ConsoleApi3.h (via WinCon.h, include Windows.h) |
| Library | Kernel32.lib |
| DLL | Kernel32.dll |

## See also

[Console Functions](console-functions.md)

[**CONSOLE\_FONT\_INFOEX**](console-font-infoex.md)