---
title: VerifyInheritanceHelper 结构 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
dev_langs:
- C++
helpviewer_keywords:
- VerifyInheritanceHelper structure
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7ed375a30ddadf72b7eee8a2cc852dec6620a992
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011112"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper 结构
支持 WRL 基础结构，不应在代码中直接使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
template <  
   typename I,  
   typename Base  
>  
struct VerifyInheritanceHelper;  
template <  
   typename I  
>  
struct VerifyInheritanceHelper<I, Nil>;  
```  
  
### <a name="parameters"></a>参数  
 *I*  
 一种类型。  
  
 *基本*  
 另一种类型。  
  
## <a name="remarks"></a>备注  
 测试是否有一个接口派生自另一个接口。  
  
## <a name="members"></a>成员  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[VerifyInheritanceHelper::Verify 方法](../windows/verifyinheritancehelper-verify-method.md)|测试当前的模板参数指定的两个接口，并确定是否派生自另一个接口。|  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `VerifyInheritanceHelper`  
  
## <a name="requirements"></a>要求  
 **标头：** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>请参阅  
 [Microsoft::WRL::Details 命名空间](../windows/microsoft-wrl-details-namespace.md)