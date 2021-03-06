---
title: IOleControlImpl 类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IOleControlImpl
- ATLCTL/ATL::IOleControlImpl
- ATLCTL/ATL::IOleControlImpl::FreezeEvents
- ATLCTL/ATL::IOleControlImpl::GetControlInfo
- ATLCTL/ATL::IOleControlImpl::OnAmbientPropertyChange
- ATLCTL/ATL::IOleControlImpl::OnMnemonic
dev_langs:
- C++
helpviewer_keywords:
- IOleControlImpl class
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34bdb0af5965b300e77a02858af3708c90fa63d0
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879278"
---
# <a name="iolecontrolimpl-class"></a>IOleControlImpl 类
此类提供的默认实现`IOleControl`接口并实现`IUnknown`。  
  
> [!IMPORTANT]
>  不能在 Windows 运行时中执行的应用程序中使用此类和其成员。  
  
## <a name="syntax"></a>语法  
  
```
template<class T>
class IOleControlImpl
```   
  
#### <a name="parameters"></a>参数  
 *T*  
 您的类，派生自`IOleControlImpl`。  
  
## <a name="members"></a>成员  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[IOleControlImpl::FreezeEvents](#freezeevents)|指示忽略容器，也不接受来自控件的事件。|  
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|填写有关控件的键盘行为的信息。 ATL 实现返回 E_NOTIMPL。|  
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|通知控件已更改一个或多个容器的环境属性。 ATL 实现返回 S_OK。|  
|[IOleControlImpl::OnMnemonic](#onmnemonic)|通知控件用户已按指定的键击。 ATL 实现返回 E_NOTIMPL。|  
  
## <a name="remarks"></a>备注  
 类`IOleControlImpl`提供的默认实现[IOleControl](http://msdn.microsoft.com/library/windows/desktop/ms694320)接口并实现`IUnknown`信息发送给转储调试中的设备生成。  
  
 **相关文章** [ATL 教程](../../atl/active-template-library-atl-tutorial.md)，[创建 ATL 项目](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `IOleControl`  
  
 `IOleControlImpl`  
  
## <a name="requirements"></a>要求  
 **标头：** atlctl.h  
  
##  <a name="freezeevents"></a>  IOleControlImpl::FreezeEvents  
 在 ATL 的实现中，`FreezeEvents`递增的控件类`m_nFreezeEvents`数据成员如果`bFreeze`为 TRUE，并减少`m_nFreezeEvents`如果`bFreeze`为 FALSE。  
  
```
HRESULT FreezeEvents(BOOL bFreeze);
```  
  
### <a name="remarks"></a>备注  
 `FreezeEvents` 然后，返回 S_OK。  
  
 请参阅[iolecontrol:: Freezeevents](http://msdn.microsoft.com/library/windows/desktop/ms678482) Windows SDK 中。  
  
##  <a name="getcontrolinfo"></a>  IOleControlImpl::GetControlInfo  
 填写有关控件的键盘行为的信息。  
  
```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```  
  
### <a name="remarks"></a>备注  
 请参阅[IOleControl:GetControlInfo](http://msdn.microsoft.com/library/windows/desktop/ms693730) Windows SDK 中。  
  
### <a name="return-value"></a>返回值  
 返回 E_NOTIMPL。  
  
##  <a name="onambientpropertychange"></a>  IOleControlImpl::OnAmbientPropertyChange  
 通知控件已更改一个或多个容器的环境属性。  
  
```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="return-value"></a>返回值  
 返回 S_OK。  
  
### <a name="remarks"></a>备注  
 请参阅[IOleControl::OnAmbientPropertyChange](http://msdn.microsoft.com/library/windows/desktop/ms690175) Windows SDK 中。  
  
##  <a name="onmnemonic"></a>  IOleControlImpl::OnMnemonic  
 通知控件用户已按指定的键击。  
  
```
HRESULT OnMnemonic(LPMSG pMsg);
```  
  
### <a name="return-value"></a>返回值  
 返回 E_NOTIMPL。  
  
### <a name="remarks"></a>备注  
 请参阅[IOleControl::OnMnemonic](http://msdn.microsoft.com/library/windows/desktop/ms680699) Windows SDK 中。  
  
## <a name="see-also"></a>请参阅  
 [IOleObjectImpl 类](../../atl/reference/ioleobjectimpl-class.md)   
 [ActiveX 控件接口](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [类概述](../../atl/atl-class-overview.md)
