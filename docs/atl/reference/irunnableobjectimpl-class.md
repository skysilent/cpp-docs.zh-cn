---
title: IRunnableObjectImpl 类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl::GetRunningClass
- ATLCTL/ATL::IRunnableObjectImpl::IsRunning
- ATLCTL/ATL::IRunnableObjectImpl::LockRunning
- ATLCTL/ATL::IRunnableObjectImpl::Run
- ATLCTL/ATL::IRunnableObjectImpl::SetContainedObject
dev_langs:
- C++
helpviewer_keywords:
- containers, running controls
- IRunnableObjectImpl class
- IRunnableObject, ATL implementation
- controls [ATL], running
- controls [C++], container running in ATL
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2a98456d3d7d0d2e4600267a81151c44e38993c5
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885572"
---
# <a name="irunnableobjectimpl-class"></a>IRunnableObjectImpl 类
此类实现`IUnknown`，并提供的默认实现[IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783)接口。  
  
> [!IMPORTANT]
>  不能在 Windows 运行时中执行的应用程序中使用此类和其成员。  
  
## <a name="syntax"></a>语法  
  
```
template<class T>  
class IRunnableObjectImpl
```  
  
#### <a name="parameters"></a>参数  
 *T*  
 您的类，派生自`IRunnableObjectImpl`。  
  
## <a name="members"></a>成员  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|返回正在运行的控件的 CLSID。 ATL 实现设置为 GUID_NULL 的 CLSID，并返回 E_UNEXPECTED。|  
|[IRunnableObjectImpl::IsRunning](#isrunning)|确定控件是否正在运行。 ATL 实现，则返回 TRUE。|  
|[IRunnableObjectImpl::LockRunning](#lockrunning)|锁定到正在运行状态的控件。 ATL 实现返回 S_OK。|  
|[IRunnableObjectImpl::Run](#run)|强制控件运行。 ATL 实现返回 S_OK。|  
|[IRunnableObjectImpl::SetContainedObject](#setcontainedobject)|该值指示控件嵌入。 ATL 实现返回 S_OK。|  
  
## <a name="remarks"></a>备注  
 [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783)接口，若要确定控件是否正在运行，强制其运行，或将其锁定到正在运行状态的容器。 类`IRunnableObjectImpl`提供默认实现此接口并实现`IUnknown`信息发送给转储调试中的设备生成。  
  
 **相关文章** [ATL 教程](../../atl/active-template-library-atl-tutorial.md)，[创建 ATL 项目](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `IRunnableObject`  
  
 `IRunnableObjectImpl`  
  
## <a name="requirements"></a>要求  
 **标头：** atlctl.h  
  
##  <a name="getrunningclass"></a>  IRunnableObjectImpl::GetRunningClass  
 返回正在运行的控件的 CLSID。  
  
```
HRESULT GetRunningClass(LPCLSID lpClsid);
```  
  
### <a name="return-value"></a>返回值  
 ATL 实现集\* *lpClsid* GUID_NULL 和返回 E_UNEXPECTED。  
  
### <a name="remarks"></a>备注  
 请参阅[IRunnableObject::GetRunningClass](http://msdn.microsoft.com/library/windows/desktop/ms693734) Windows SDK 中。  
  
##  <a name="isrunning"></a>  IRunnableObjectImpl::IsRunning  
 确定控件是否正在运行。  
  
```
virtual BOOL IsRunning();
```  
  
### <a name="return-value"></a>返回值  
 ATL 实现，则返回 TRUE。  
  
### <a name="remarks"></a>备注  
 请参阅[IRunnableObject::IsRunning](http://msdn.microsoft.com/library/windows/desktop/ms678496) Windows SDK 中。  
  
##  <a name="lockrunning"></a>  IRunnableObjectImpl::LockRunning  
 锁定到正在运行状态的控件。  
  
```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```  
  
### <a name="return-value"></a>返回值  
 ATL 实现返回 S_OK。  
  
### <a name="remarks"></a>备注  
 请参阅[IRunnableObject::LockRunning](http://msdn.microsoft.com/library/windows/desktop/ms693361) Windows SDK 中。  
  
##  <a name="run"></a>  IRunnableObjectImpl::Run  
 强制控件运行。  
  
```
HRESULT Run(LPBINDCTX lpbc);
```  
  
### <a name="return-value"></a>返回值  
 ATL 实现返回 S_OK。  
  
### <a name="remarks"></a>备注  
 请参阅[IRunnableObject::Run](http://msdn.microsoft.com/library/windows/desktop/ms694517) Windows SDK 中。  
  
##  <a name="setcontainedobject"></a>  IRunnableObjectImpl::SetContainedObject  
 该值指示控件嵌入。  
  
```
HRESULT SetContainedObject(BOOL fContained);
```  
  
### <a name="return-value"></a>返回值  
 ATL 实现返回 S_OK。  
  
### <a name="remarks"></a>备注  
 请参阅[IRunnableObject::SetContainedObject](http://msdn.microsoft.com/library/windows/desktop/ms693710) Windows SDK 中。  
  
## <a name="see-also"></a>请参阅  
 [CComControl 类](../../atl/reference/ccomcontrol-class.md)   
 [类概述](../../atl/atl-class-overview.md)
