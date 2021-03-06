---
title: _com_ptr_t::operator = |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t.operator=
- _com_ptr_t::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator = [C++], pointers
- = operator [C++], with specific Visual C++ objects
- operator= [C++], pointers
ms.assetid: 46849455-371c-4d0f-bae4-c1f737d2ca4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f8cc7c45c9195ea866725b2ef60d5eae624401b8
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408752"
---
# <a name="comptrtoperator-"></a>_com_ptr_t::operator =
**Microsoft 专用**  
  
 将新值赋给现有 `_com_ptr_t` 对象。  
  
## <a name="syntax"></a>语法  
  
```  
template<typename _OtherIID>   
_com_ptr_t& operator=( const _com_ptr_t<_OtherIID>& p );  
  
// Sets a smart pointer to be a different smart pointer of a different   
// type or a different raw interface pointer. QueryInterface is called   
// to find an interface pointer of this smart pointer's type, and   
// Release is called to decrement the reference count for the previously   
// encapsulated pointer. If QueryInterface fails with an E_NOINTERFACE,   
// a NULL smart pointer results.  
template<typename _InterfaceType>   
_com_ptr_t& operator=(_InterfaceType* p );  
  
// Encapsulates a raw interface pointer of this smart pointer's type.   
// AddRef is called to increment the reference count for the encapsulated  
// interface pointer, and Release is called to decrement the reference   
// count for the previously encapsulated pointer.  
template<> _com_ptr_t&    
operator=( Interface* pInterface ) throw();  
  
// Sets a smart pointer to be a copy of another instance of the same   
// smart pointer of the same type. AddRef is called to increment the   
// reference count for the encapsulated interface pointer, and Release   
// is called to decrement the reference count for the previously   
// encapsulated pointer.  
_com_ptr_t& operator=( const _com_ptr_t& cp ) throw();  
  
// Sets a smart pointer to NULL. The NULL argument must be a zero.  
_com_ptr_t& operator=( int null );  

// Sets a smart pointer to be a _variant_t object. The encapsulated   
// VARIANT must be of type VT_DISPATCH or VT_UNKNOWN, or it can be   
// converted to one of these two types. If QueryInterface fails with an   
// E_NOINTERFACE error, a NULL smart pointer results.  
_com_ptr_t& operator=( const _variant_t& varSrc );  
```  
  
## <a name="remarks"></a>备注  
 将接口指针分配给此 `_com_ptr_t` 对象。  
  
 **结束 Microsoft 专用**  
  
## <a name="see-also"></a>请参阅  
 [_com_ptr_t 类](../cpp/com-ptr-t-class.md)