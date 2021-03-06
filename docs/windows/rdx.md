---
title: rdx |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.rdx
dev_langs:
- C++
helpviewer_keywords:
- rdx attribute
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 32dd702dd7d429c4437875a6aead86ae687dfb2b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011044"
---
# <a name="rdx"></a>rdx
创建注册表项或修改现有的注册表项。  
  
## <a name="syntax"></a>语法  
  
```cpp  
[ rdx(   
   key,   
   valuename=NULL,   
   regtype   
) ]  
```  
  
### <a name="parameters"></a>参数  
 *key*  
 若要创建或打开密钥的名称。  
  
 *valuename* （可选）  
 指定要设置的值字段。 如果键中不存在具有此名称的值字段，将其添加。  
  
 *regtype*  
 要添加的注册表项的类型。 可以是以下之一： `text`， `dword`， `binary`，或`CString`。  
  
## <a name="remarks"></a>备注  
 **Rdx** c + + 属性创建或修改现有的注册表项为 COM 组件。 该属性将 BEGIN_RDX_MAP 宏添加到实现的目标成员的对象。 `RegistryDataExchange`由于 BEGIN_RDX_MAP 宏，注入的函数可用于在注册表和数据成员之间传输数据  
  
 可以结合使用此特性[组件类](../windows/coclass.md)， [progid](../windows/progid.md)，或[vi_progid](../windows/vi-progid.md)属性或隐含其中之一的其他属性。  
  
## <a name="requirements"></a>要求  
  
### <a name="attribute-context"></a>特性上下文  
  
|||  
|-|-|  
|**适用对象**|**类**或**结构**成员|  
|**可重复**|否|  
|**必需的特性**|无|  
|**无效的特性**|无|  
  
 有关特性上下文的详细信息，请参见 [特性上下文](../windows/attribute-contexts.md)。  
  
## <a name="example"></a>示例  
 以下代码添加到系统描述 CMyClass COM 组件调用 MyValue 注册表项。  
  
```cpp  
// cpp_attr_ref_rdx.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
  
[module (name="MyLib")];  
  
class CMyClass {  
public:  
   CMyClass() {  
      strcpy_s(m_sz, "SomeValue");  
   }  
  
   [ rdx(key = "HKCR\\MyApp.MyApp.1", valuename = "MyValue", regtype = "text")]   
   char m_sz[256];  
};  
```  
  
## <a name="see-also"></a>请参阅  
 [COM 特性](../windows/com-attributes.md)   
 [registration_script](../windows/registration-script.md)   