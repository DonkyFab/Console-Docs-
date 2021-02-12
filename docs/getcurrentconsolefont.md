---
title: GetCurrentConsoleFont function
description: Retrieves information about the current console font for a specified console screen buffer.
author: miniksa
ms.author: miniksa
ms.topic: article
keywords: console, character mode applications, command line applications, terminal applications, console api
f1_keywords:
- consoleapi3/GetCurrentConsoleFont
- wincon/GetCurrentConsoleFont
- GetCurrentConsoleFont
MS-HAID:
- '\_win32\_getcurrentconsolefont'
- 'base.getcurrentconsolefont'
- 'consoles.getcurrentconsolefont'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/desktop'
ms.assetid: 347508ea-5c15-4568-b99f-1e7f5cdac8c1

topic_type:
- apiref
api_name:
- GetCurrentConsoleFont
api_location:
- Kernel32.dll
api_type:
- DllExport
---

# GetCurrentConsoleFont function

[!INCLUDE [not-recommended-banner](./includes/not-recommended-banner.md)]

Retrieves information about the current console font.

## Syntax

```C
BOOL WINAPI GetCurrentConsoleFont(
  _In_  HANDLE             hConsoleOutput,
  _In_  BOOL               bMaximumWindow,
  _Out_ PCONSOLE_FONT_INFO lpConsoleCurrentFont
);
```

## Parameters

*hConsoleOutput* \[in\]  
A handle to the console screen buffer. The handle must have the **GENERIC\_READ** access right. For more information, see [Console Buffer Security and Access Rights](console-buffer-security-and-access-rights.md).

*bMaximumWindow* \[in\]  
If this parameter is **TRUE**, font information is retrieved for the maximum window size. If this parameter is **FALSE**, font information is retrieved for the current window size.

*lpConsoleCurrentFont* \[out\]  
A pointer to a [**CONSOLE\_FONT\_INFO**](console-font-info-str.md) structure that receives the requested font information.

## Return value

If the function succeeds, the return value is nonzero.

If the function fails, the return value is zero. To get extended error information, call [**GetLastError**](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

## Remarks

To compile an application that uses this function, define **\_WIN32\_WINNT** as 0x0500 or later. For more information, see [Using the Windows Headers](/windows/win32/winprog/using-the-windows-headers).

[!INCLUDE [no-vt-equiv-user-priv](./includes/no-vt-equiv-user-priv.md)]

## Requirements

| &nbsp; | &nbsp; |
|-|-|
| Minimum supported client | Windows XP \[desktop apps only\] |
| Minimum supported server | Windows Server 2003 \[desktop apps only\] |
| Header | ConsoleApi3.h (via WinCon.h, include Windows.h) |
| Library | Kernel32.lib |
| DLL | Kernel32.dll |

## See also

[Console Functions](console-functions.md)

[Console Screen Buffers](console-screen-buffers.md)

[**CONSOLE\_FONT\_INFO**](console-font-info-str.md)

[**GetConsoleFontSize**](getconsolefontsize.md)