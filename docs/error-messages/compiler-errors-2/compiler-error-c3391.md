---
title: 编译器错误 C3391 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3391
dev_langs:
- C++
helpviewer_keywords:
- C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28615d85eca534966a4d8b90cef20ea577e0d592
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33256609"
---
# <a name="compiler-error-c3391"></a>编译器错误 C3391
type_arg： 必须是不可为 null 的值类型的泛型参数 param 泛型 generic_type 的类型参数无效。  
  
泛型类型实例化错误。 检查类型定义。 有关详细信息，请参阅<xref:System.Nullable>和[泛型](../../windows/generics-cpp-component-extensions.md)。  
  
## <a name="example"></a>示例  
下面的示例使用 C# 来创建包含具有 C + 中创建泛型类型时，不支持某些约束的泛型类型的组件 + CLI。 有关详细信息，请参阅[类型参数的约束](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)。  
  
```cs  
// C3391.cs  
// Compile by using: csc /target:library C3391.cs  
// a C# program  
public class GR<N>  
where N : struct {}  
```  
  
可用 C3391.dll 组件时，下面的示例生成 C3391。  
  
```cpp  
// C3391_b.cpp  
// Compile by using: cl /clr C3391_b.cpp  
#using <C3391.dll>  
using namespace System;  
value class VClass {};  
  
int main() {  
   GR< Nullable<VClass> >^ a =   
      gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable  
   GR<VClass>^ aa = gcnew GR<VClass>(); // OK  
}  
```