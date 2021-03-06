---
title: 易失性 （C++） |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- volatile_cpp
dev_langs:
- C++
helpviewer_keywords:
- interrupt handlers and volatile keyword [C++]
- volatile keyword [C++]
- volatile objects
- objects [C++], volatile
ms.assetid: 81db4a85-ed5a-4a2c-9a53-5d07a771d2de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82ea6211a51bbe45fa1613dd7bb682f363783367
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461918"
---
# <a name="volatile-c"></a>volatile (C++)
可用于声明可在程序中由硬件修改的对象的类型限定符。  
  
## <a name="syntax"></a>语法  
  
```  
volatile declarator ;  
```  
  
## <a name="remarks"></a>备注  
 可以使用[/volatile](../build/reference/volatile-volatile-keyword-interpretation.md)编译器开关来修改编译器解释此关键字的方式。  
  
 Visual Studio 将解释**易失性**以不同的方式具体取决于目标体系结构的关键字。 对于 ARM，如果没有 **/volatile**编译器选项指定，编译器将执行像 **/volatile: iso**指定。 对于 ARM，如果没有之外的体系结构 **/volatile**编译器选项指定，编译器将执行像 **/volatile: ms**指定; 因此，对于体系结构不是强 ARM 我们您指定的建议 **/volatile: iso**，并在处理跨线程共享的内存时使用显式同步基元和编译器内部函数。  
  
 可以使用**易失性**限定符来提供对异步处理，如中断处理程序使用的内存位置的访问。  
  
 当**易失性**还有的变量上使用[__restrict](../cpp/extension-restrict.md)关键字**易失性**优先。  
  
 如果**struct**成员标记为**易失性**，然后**易失性**传播到整个结构。 如果结构，不能可以复制其长度当前体系结构上使用一条指令**易失性**上该结构可能完全丢失。  
  
 **易失性**关键字可能对字段上的没有影响，如果以下条件之一为 true:  
  
-   可变字段的长度超过可使用一条指令在当前体系结构上复制的最大大小。  
  
-   最外层包含长度**结构**，或如果它是可能嵌套的成员**结构**-超出了可以使用一条指令在当前体系结构复制的最大大小。  
  
 尽管处理器不会对未缓存的内存访问，但必须标记为不可缓存的变量**易失性**为了保证编译器不会对内存访问。  
  
 声明为对象**易失性**因为在任何时候更改其值可以不使用的某些优化。  系统始终读取可变对象的当前值请求它时，即使上一条指令请求从同一个对象值。  此外，在分配上立即写入对象的值。  
  
## <a name="iso-compliant"></a>符合 ISO  
 如果您是熟悉 C# volatile 关键字，或熟悉的行为**可变**在 Visual c + + 的早期版本，请注意，C + + 11 ISO 标准**易失性**关键字是不同的且是在 Visual Studio 中受支持时[/volatile: iso](../build/reference/volatile-volatile-keyword-interpretation.md)指定编译器选项。 （对于 ARM，默认情况下将指定它。） **易失性**C + + 11 ISO 标准代码中的关键字是仅用于硬件访问; 因此，不要将其用于线程间的通信。 对于线程间通信使用机制例如[std::atomic\<T >](../standard-library/atomic.md)从[C++ 标准库](../standard-library/cpp-standard-library-reference.md)。  
  
## <a name="end-of-iso-compliant"></a>符合 ISO 的末尾  
  
## <a name="microsoft-specific"></a>Microsoft 专用  
 时 **/volatile: ms**使用编译器选项，面向 ARM 之外的体系结构时，默认情况，编译器将生成额外代码来维护对可变对象还维护的引用之间的排序对其他全局对象的引用的排序。 具体而言：  
  
-   对可变对象进行写入（也称为可变编写）具有“发布”语义；也就是说，对指令序列中的可变对象进行写入之前发生的全局或静态对象的引用将在已编译的库中写入可变对象之前发生。  
  
-   对可变对象进行读取（也称为可变读取）具有“获取”语义；也就是说，对指令序列中的可变对象进行读取之前发生的全局或静态对象的引用将在已编译的库中读取可变对象之前发生。  
  
 这样不稳定的对象，用于内存锁和多线程应用程序中的版本。  
  
> [!NOTE]
>  当它依赖于具有时提供的增强保证 **/volatile: ms**使用编译器选项时，该代码是不可移植。  
  
**结束 Microsoft 专用**  
  
## <a name="see-also"></a>请参阅  
 [关键字](../cpp/keywords-cpp.md)   
 [const](../cpp/const-cpp.md)   
 [固定和可变指针](../cpp/const-and-volatile-pointers.md)