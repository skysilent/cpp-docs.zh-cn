---
title: vararg |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.vararg
dev_langs:
- C++
helpviewer_keywords:
- vararg attribute
ms.assetid: 20fc3244-18e9-411c-990e-d5b4fa29a570
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cad2cc52c7c785a715caa96913f2a1c1bf3630b2
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010904"
---
# <a name="vararg"></a>vararg
指定该函数采用数目可变的参数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
[vararg]  
```  
  
## <a name="remarks"></a>备注  
 **Vararg** c + + 属性具有相同的功能[vararg](http://msdn.microsoft.com/library/windows/desktop/aa367304) MIDL 特性。  
  
## <a name="example"></a>示例  
 下面的代码演示的一种用法**vararg**:  
  
```cpp  
// cpp_attr_ref_vararg.cpp  
// compile with: /LD  
#include "unknwn.h"  
#include "oaidl.h"  
[module(name="MyLibrary")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface X : public IUnknown   
{  
   [vararg] HRESULT Button([in, satype(VARIANT)]SAFEARRAY *psa);  
};  
```  
  
## <a name="requirements"></a>要求  
  
### <a name="attribute-context"></a>特性上下文  
  
|||  
|-|-|  
|**适用对象**|接口方法|  
|**可重复**|否|  
|**必需的特性**|无|  
|**无效的特性**|无|  
  
 有关特性上下文的详细信息，请参见 [特性上下文](../windows/attribute-contexts.md)。  
  
## <a name="see-also"></a>请参阅  
 [IDL 特性](../windows/idl-attributes.md)   
 [方法特性](../windows/method-attributes.md)   