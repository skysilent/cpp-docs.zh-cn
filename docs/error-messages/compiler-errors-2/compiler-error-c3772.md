---
title: 编译器错误 C3772 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3772
dev_langs:
- C++
helpviewer_keywords:
- C3772
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01003a4d474b80c152d271546f659d418f3c4df7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275445"
---
# <a name="compiler-error-c3772"></a>编译器错误 C3772
“name”: 友元模板声明无效  
  
声明类模板专用化的友元无效。 不能声明一个类模板的显式或部分专用化，也不能在同一语句中声明该专用化的友元。 *名称* 占位符标识无效的声明。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   不能声明类模板专用化的友元。  
  
-   如果对应用程序适用，请声明类模板的友元，或声明特定部分专用化或显式专用化的友元。  
  
## <a name="example"></a>示例  
 下面的代码示例失败，因为它声明的是类模板部分专用化的友元。  
  
```cpp  
// c3772.cpp  
// compile with: /c  
  
// A class template.  
    template<class T> class A {};  
  
// A partial specialization of the class template.  
    template<class T> class A<T*> {};  
  
// An explicit specialization.  
    template<> class A<char>;  
  
class X {  
// Invalid declaration of a friend of a partial specialization.  
    template<class T> friend class A<T*>; // C3772  
  
// Instead, if it is appropriate for your application, declare a   
// friend of the class template. Consequently, all specializations   
// of the class template are friends:  
//    template<class T> friend class A;  
// Or declare a friend of a particular partial specialization:  
//    friend class A<int*>;  
// Or declare a friend of a particular explicit specialization:  
//    friend class A<char>;  
};  
```  
  
## <a name="see-also"></a>请参阅  
[模板](../../cpp/templates-cpp.md)   
[模板特殊化](../../cpp/template-specialization-cpp.md)   
