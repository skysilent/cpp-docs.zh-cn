---
title: 支持使用 wmain |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- wWinMain
dev_langs:
- C++
helpviewer_keywords:
- wide characters [C++], wmain function
- wWinMain function
- wmain function
ms.assetid: 41213c41-668c-40a4-8a1e-77d9eded720d
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 390f2a11b98a851b5f33b4e0a941a515421d5836
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011612"
---
# <a name="support-for-using-wmain"></a>支持使用 wmain
Visual c + + 支持定义**wmain**函数，并将宽字符自变量传递给 Unicode 应用程序。 您将形参声明为**wmain**，使用的格式类似于`main`。 然后可以将宽字符自变量和宽字符环境指针（可选）传递给该程序。 wmain 的 `argv` 和 `envp` 参数为 `wchar_t*` 类型。 例如：  
  
```  
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )  
```  
  
> [!NOTE]
>  MFC Unicode 应用程序使用`wWinMain`作为入口点。 在这种情况下，`CWinApp::m_lpCmdLine`是 Unicode 字符串。 请务必设置`wWinMainCRTStartup`与[/ENTRY](../build/reference/entry-entry-point-symbol.md)链接器选项。  
  
 如果程序使用`main`函数，则多字节字符环境由运行时库在程序启动时创建。 环境的宽字符副本仅在需要时创建（如调用 `_wgetenv` 或 `_wputenv` 函数时）。 在首次调用`_wputenv`，或在首次调用`_wgetenv`如果 MBCS 环境已存在，创建一个相应的宽字符字符串环境。 在环境并指向通过`_wenviron`全局变量是宽字符版本的`_environ`全局变量。 此时，两个副本 （MBCS 和 Unicode） 环境的同时存在，并由运行时系统的整个程序的生命期维护。  
  
 同样，如果程序使用 wmain 函数，则在程序启动时创建宽字符环境并用 `_wenviron` 全局变量指向该环境。 在首次调用创建 MBCS (ASCII) 环境`_putenv`或`getenv`和指向`_environ`全局变量。  
  
## <a name="see-also"></a>请参阅  
 [有关 Unicode 的支持](../text/support-for-unicode.md)   
 [Unicode 编程摘要](../text/unicode-programming-summary.md)   
 [WinMain 函数](http://msdn.microsoft.com/library/windows/desktop/ms633559)