---
title: Microsoft::WRL::Wrappers::HandleTraits Namespace |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
dev_langs:
- C++
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c83b921aabeee34b583c8f771190ecf60edccb59
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015806"
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Microsoft::WRL::Wrappers::HandleTraits 命名空间
介绍了常见的基于句柄的资源类型的特征。  
  
## <a name="syntax"></a>语法  
  
```cpp  
namespace Microsoft::WRL::Wrappers::HandleTraits;  
```  
  
## <a name="members"></a>成员  
  
### <a name="structures"></a>结构  
  
|名称|描述|  
|----------|-----------------|  
|[CriticalSectionTraits 结构](../windows/criticalsectiontraits-structure.md)|专门负责`CriticalSection`对象以支持无效的关键部分或函数，以释放关键节。|  
|[EventTraits 结构](../windows/eventtraits-structure.md)|定义特征`Event`类句柄。|  
|[FileHandleTraits 结构](../windows/filehandletraits-structure.md)|定义的文件句柄的特征。|  
|[HANDLENullTraits 结构](../windows/handlenulltraits-structure.md)|定义未初始化句柄的共同特征。|  
|[HANDLETraits 结构](../windows/handletraits-structure.md)|定义句柄的共同特征。|  
|[MutexTraits 结构](../windows/mutextraits-structure.md)|定义常见特征[互斥体](../windows/mutex-class1.md)类。|  
|[SemaphoreTraits 结构](../windows/semaphoretraits-structure.md)|定义信号量对象的共同特征。|  
|[SRWLockExclusiveTraits 结构](../windows/srwlockexclusivetraits-structure.md)|描述的常见特征`SRWLock`中排他锁模式的类。|  
|[SRWLockSharedTraits 结构](../windows/srwlocksharedtraits-structure.md)|描述的常见特征`SRWLock`中共享锁模式的类。|  
  
## <a name="requirements"></a>要求  
 **标头：** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>请参阅  
 [Microsoft::WRL::Wrappers 命名空间](../windows/microsoft-wrl-wrappers-namespace.md)