---
title: 编译器错误 C3189 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3189
dev_langs:
- C++
helpviewer_keywords:
- C3189
ms.assetid: b254de79-931e-4a59-a9f4-1c690d90ca5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acf0e49ecf9c8003d8dcfe035b14c8f5c5067dbc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33251008"
---
# <a name="compiler-error-c3189"></a>编译器错误 C3189
typeid\<键入抽象声明符 >： 不再支持此语法，请使用:: typeid 改为  
  
 过时形式[typeid](../../windows/typeid-cpp-component-extensions.md)已使用，使用新的窗体。  
  
 下面的示例生成 C3189:  
  
```  
// C3189.cpp  
// compile with: /clr  
int main() {  
   System::Type^ t  = typeid<System::Object>;   // C3189  
   System::Type^ t2  = System::Object::typeid;   // OK  
}  
```