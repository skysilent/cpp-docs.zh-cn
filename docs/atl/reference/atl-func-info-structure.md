---
title: _ATL_FUNC_INFO 结构 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- _ATL_FUNC_INFO
- ATL::_ATL_FUNC_INFO
- ATL._ATL_FUNC_INFO
dev_langs:
- C++
helpviewer_keywords:
- _ATL_FUNC_INFO structure
- ATL_FUNC_INFO structure
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8852deacfd36ba988b9b31bdad363c05aee12b6e
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882203"
---
# <a name="atlfuncinfo-structure"></a>_ATL_FUNC_INFO 结构
包含用于描述调度接口方法或属性的类型信息。  
  
## <a name="syntax"></a>语法  
  
```
struct _ATL_FUNC_INFO {
    CALLCONV cc;
    VARTYPE vtReturn;
    SHORT nParams;
    VARTYPE pVarTypes[_ATL_MAX_VARTYPES];
};
```  
  
## <a name="members"></a>成员  
 `cc`  
 调用约定。 使用此结构与时[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)类，此成员必须为 CC_STDCALL。 `CC_CDECL` 是在 Windows CE 中支持的唯一选项`CALLCONV`字段的`_ATL_FUNC_INFO`结构。 任何其他值不受支持因此其行为未定义。  
  
 `vtReturn`  
 该函数的变体类型返回值。  
  
 `nParams`  
 函数参数的数目。  
  
 `pVarTypes`  
 函数参数的 variant 类型的数组。  
  
## <a name="remarks"></a>备注  
 在内部，ATL 还使用此结构来保存从类型库获取的信息。 可能需要直接操作此结构，如果您提供事件处理程序与一起使用的类型信息[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)类和[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)宏。  
  
## <a name="example"></a>示例  
 给定 IDL 中定义的调度接口方法：  
  
 [!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]  
  
 您需要定义`_ATL_FUNC_INFO`结构：  
  
 [!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]  
  
## <a name="requirements"></a>要求  
 标头： atlcom.h  
  
## <a name="see-also"></a>请参阅  
  [类和结构](../../atl/reference/atl-classes.md)  
 [IDispEventSimpleImpl 类](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)





