---
title: CriticalSectionTraits 结构 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
dev_langs:
- C++
helpviewer_keywords:
- CriticalSectionTraits structure
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 149cb7fba3d0754e47ac656c137af2d9bf759f1a
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642186"
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits 结构
专门负责`CriticalSection`对象以支持无效的关键部分或函数，以释放关键节。  
  
## <a name="syntax"></a>语法  
  
```  
struct CriticalSectionTraits;  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-typedefs"></a>公共 Typedef  
  
|名称|描述|  
|----------|-----------------|  
|`Type`|一个**typedef**的关键部分定义指针。 `Type` 定义为`typedef CRITICAL_SECTION* Type;`。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[CriticalSectionTraits::GetInvalidValue 方法](../windows/criticalsectiontraits-getinvalidvalue-method.md)|专门负责`CriticalSection`模板，以便该模板始终无效。|  
|[CriticalSectionTraits::Unlock 方法](../windows/criticalsectiontraits-unlock-method.md)|专门负责`CriticalSection`模板以便支持指定的关键节对象的释放所有权。|  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `CriticalSectionTraits`  
  
## <a name="requirements"></a>要求  
 **标头：** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>请参阅  
 [Microsoft::WRL::Wrappers::HandleTraits 命名空间](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)