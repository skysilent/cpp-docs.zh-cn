---
title: IsBaseOfStrict 结构 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
dev_langs:
- C++
helpviewer_keywords:
- IsBaseOfStrict structure
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d4690c15adac7be66ca916b1fc0f769e6c50190c
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017891"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict 结构
支持 WRL 基础结构，不应在代码中直接使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
template <  
   typename Base,  
   typename Derived  
>  
  
struct IsBaseOfStrict;  
template <  
   typename Base  
>  
struct IsBaseOfStrict<Base, Base>;  
```  
  
### <a name="parameters"></a>参数  
 *基本*  
 基类型。  
  
 *派生*  
 派生的类型。  
  
## <a name="remarks"></a>备注  
 测试一种类型是否是另一种类型的基类。  
  
 第一个模板测试是否从可能产生的基类型派生的类型 **，则返回 true**或**false**。 第二个模板测试是否派生的类型是从其自身，这将始终产生**false**。  
  
## <a name="members"></a>成员  
  
### <a name="public-constants"></a>公共常量  
  
|name|描述|  
|----------|-----------------|  
|[IsBaseOfStrict::value 常量](../windows/isbaseofstrict-value-constant.md)|指示是否是一个类型的另一个基类。|  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `IsBaseOfStrict`  
  
## <a name="requirements"></a>要求  
 **标头：** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>请参阅  
 [Microsoft::WRL::Details 命名空间](../windows/microsoft-wrl-details-namespace.md)