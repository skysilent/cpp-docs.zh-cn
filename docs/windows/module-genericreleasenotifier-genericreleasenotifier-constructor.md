---
title: Module::GenericReleaseNotifier::GenericReleaseNotifier 构造函数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- GenericReleaseNotifier, constructor
ms.assetid: feb5b687-a4b0-4809-9022-8f292181b7a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5aa78562c934c41b2ff2ab7b381f6b2612426651
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014583"
---
# <a name="modulegenericreleasenotifiergenericreleasenotifier-constructor"></a>Module::GenericReleaseNotifier::GenericReleaseNotifier 构造函数
初始化的新实例**module:: genericreleasenotifier**类。  
  
## <a name="syntax"></a>语法  
  
```cpp  
GenericReleaseNotifier(  
   T callback,   
   bool release  
) throw() : ReleaseNotifier(release), callback_(callback);  
```  
  
### <a name="parameters"></a>参数  
 *回调*  
 Lambda、 functor 或可以使用括号函数运算符调用的函数指针事件处理程序 (`()`)。  
  
 *release*  
 指定 **，则返回 true**若要启用调用基础[模块:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md)方法; 否则，指定**false**。  
  
## <a name="requirements"></a>要求  
 **标头：** module.h  
  
 **命名空间：** Microsoft::WRL  
  
## <a name="see-also"></a>请参阅  
 [Module::GenericReleaseNotifier 类](../windows/module-genericreleasenotifier-class.md)