﻿---
title: 混合使用 C （结构化） 和 C++ 异常 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6e632faddb3b4f59733710a915ed121a12f4e0c6
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404858"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>混合使用 C（结构化）和 C++ 异常
若要编写可移植性更高的代码，建议不要在 C++ 程序中使用结构化异常处理。 但是，有时可能需要使用 **/EHa** 进行编译并混合使用结构化异常和 C++ 源代码，同时需要一些用于处理这两种异常的设备。 由于结构化异常处理程序没有对象或类型化异常概念，因此无法处理 C++ 代码抛出的异常；但是，C++ **catch** 处理程序可以处理结构化异常。 为此类中，c + + 异常处理语法 (**尝试**，**引发**，**捕获**) 不接受的 C 编译器，但结构化的异常处理语法 (**__try**， **__except**， **__finally**) 都支持 c + + 编译器支持。  
  
 请参阅 [_set_se_translator](../c-runtime-library/reference/set-se-translator.md)，了解如何将结构化异常作为 C++ 异常来处理。
  
 如果将结构化异常和 C++ 异常混合，请注意以下几点：  
  
1. 不能在同一函数中混合 C++ 异常和结构化异常。  
  
2.  终止处理程序 (**__finally**块) 将始终执行，即使引发异常后的展开过程。  
  
3. C++ 异常处理可以在所有使用 [/EH](../build/reference/eh-exception-handling-model.md) 编译器选项（此选项启用展开语义）进行编译的模块中捕获并保留展开语义。
  
4. 有时候，可能不会针对所有对象调用析构函数。例如，如果在尝试通过未初始化的函数指针进行函数调用时发生结构化异常，而该函数用作参数的对象是在调用之前构造的，则这些对象不会在堆栈展开过程中调用其析构函数。  
  
## <a name="what-do-you-want-to-know-more-about"></a>你想进一步了解什么？  
  
-   [C++ 程序中使用 setjmp 或 longjmp](../cpp/using-setjmp-longjmp.md)  
  
-   [SEH 和 C++ EH 之间的差异](../cpp/exception-handling-differences.md)  
  
## <a name="see-also"></a>请参阅  
 [C++ 异常处理](../cpp/cpp-exception-handling.md)
