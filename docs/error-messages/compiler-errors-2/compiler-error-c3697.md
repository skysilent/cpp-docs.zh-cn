---
title: 编译器错误 C3697 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3697
dev_langs:
- C++
helpviewer_keywords:
- C3697
ms.assetid: 2d3f63c4-b7f8-421d-a7a5-2bf17fd054f9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4689365859ec121c716e5fb060d2985647bba30
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33263809"
---
# <a name="compiler-error-c3697"></a>编译器错误 C3697
限定符： 不能使用此限定符 ^  
  
 跟踪句柄 (^) 已应用于它未设计为其的限定符。  
  
 下面的示例生成 C3697:  
  
```  
// C3697.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String ^__restrict s;   // C3697  
   String ^ s2;   // OK  
}  
```