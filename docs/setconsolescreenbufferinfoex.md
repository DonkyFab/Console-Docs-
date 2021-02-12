---
title: SetConsoleScreenBufferInfoEx function
description: Sets extended information about the specified console screen buffer to the specified buffer.
author: miniksa
ms.author: miniksa
ms.topic: article
keywords: console, character mode applications, command line applications, terminal applications, console api
f1_keywords:
- consoleapi2/SetConsoleScreenBufferInfoEx
- wincon/SetConsoleScreenBufferInfoEx
- SetConsoleScreenBufferInfoEx
MS-HAID:
- 'base.setconsolescreenbufferinfoex'
- 'consoles.setconsolescreenbufferinfoex'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/desktop'
ms.assetid: ff851144-eee9-4410-8fd1-28aa24fc25f1

topic_type:
- apiref
api_name:
- SetConsoleScreenBufferInfoEx
api_location:
- Kernel32.dll
- API-MS-Win-Core-Console-l2-1-0.dll
- KernelBase.dll
- API-MS-Win-DownLevel-Kernel32-l1-1-0.dll
api_type:
- DllExport
---

# SetConsoleScreenBufferInfoEx function

[!INCLUDE [not-recommended-banner](./includes/not-recommended-banner.md)]

Sets extended information about the specified console screen buffer.

## Syntax

```C
BOOL WINAPI SetConsoleScreenBufferInfoEx(
  _In_ HANDLE                        hConsoleOutput,
  _In_ PCONSOLE_SCREEN_BUFFER_INFOEX lpConsoleScreenBufferInfoEx
);
```

## Parameters

*hConsoleOutput* \[in\]  
A handle to the console screen buffer. The handle must have the **GENERIC\_WRITE** access right. For more information, see [Console Buffer Security and Access Rights](console-buffer-security-and-access-rights.md).

*lpConsoleScreenBufferInfoEx* \[in\]  
A [**CONSOLE\_SCREEN\_BUFFER\_INFOEX**](console-screen-buffer-infoex.md) structure that contains the console screen buffer information.

## Return value

If the function succeeds, the return value is nonzero.

If the function fails, the return value is zero. To get extended error information, call [**GetLastError**](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

## Remarks

> [!TIP]
> This API has a partial **[virtual terminal](console-virtual-terminal-sequences.md)** equivalent. **[Cursor positioning buffer](console-virtual-terminal-sequences.md#cursor-positioning)** and **[text attributes](console-virtual-terminal-sequences.md#text-formatting)** have specific sequence equivalents. The color table is not configurable, but **[extended colors](console-virtual-terminal-sequences.md#extended-colors)** are available beyond what is normally available through **[console functions](console-functions.md)**. Popup attributes have no equivalent as popup menus are the responsibility of the command-line client application in the **virtual terminal** world. Finally, the size of the window and the full screen status are considered privileges owned by the user in the **virtual terminal** world and have no equivalent sequence.

## Requirements

| &nbsp; | &nbsp; |
|-|-|
| Minimum supported client | Windows Vista \[desktop apps only\] |
| Minimum supported server | Windows Server 2008 \[desktop apps only\] |
| Header | ConsoleApi2.h (via WinCon.h, include Windows.h) |
| Library | Kernel32.lib |
| DLL | Kernel32.dll |

## See also

[Console Functions](console-functions.md)

[**CONSOLE\_SCREEN\_BUFFER\_INFOEX**](console-screen-buffer-infoex.md)

[**GetConsoleScreenBufferInfoEx**](getconsolescreenbufferinfoex.md)