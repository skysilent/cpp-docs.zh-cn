---
title: equal_to 结构 | Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::equal_to
dev_langs:
- C++
helpviewer_keywords:
- equal_to function
- equal_to struct
ms.assetid: 8e4f2b50-b2db-48e3-b4cc-6cc03362c2a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68ca39b459b0d0e60305105986d3e76aa86a5bed
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961647"
---
# <a name="equalto-struct"></a>equal_to 结构

执行相等运算的二元谓词 (`operator==`) 对其自变量。

## <a name="syntax"></a>语法

```cpp
template <class Type = void>
struct equal_to : public binary_function<Type, Type, bool>
 {
    bool operator()(const Type& Left, const Type& Right) const;
 };

// specialized transparent functor for operator==
template <>
struct equal_to<void>
 {
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
      ->  decltype(std::forward<T>(Left) == std::forward<U>(Right));
 };
```

### <a name="parameters"></a>参数

*类型*， *T*， *U*支持任何类型`operator==`接受指定或推断类型的操作数。

*左侧*相等运算的左的操作数。 专用化的模板采用类型的左值引用参数*类型*。 专用化的模板可完美转移左值和右值引用参数的类型推断*T*。

*右*相等运算的右操作数。 专用化的模板采用类型的左值引用参数*类型*。 专用化的模板可完美转移左值和右值引用参数的类型推断*U*。

## <a name="return-value"></a>返回值

`Left == Right` 的结果。 专专用化模板可完美转移结果，该结果具有由 `operator==` 返回的类型。

## <a name="remarks"></a>备注

类型的对象*类型*必须是可比较相等性的。 这要求在对象集上定义的 `operator==` 满足等价关系的数学性质。 所有内置的数字和指针类型都满足此要求。

## <a name="example"></a>示例

```cpp
// functional_equal_to.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main( )
{
   vector <double> v1, v2, v3 ( 6 );
   vector <double>::iterator Iter1, Iter2, Iter3;

   int i;
   for ( i = 0 ; i <= 5 ; i+=2 )
   {
      v1.push_back( 2.0 *i );
      v1.push_back( 2.0 * i + 1.0 );
   }

   int j;
   for ( j = 0 ; j <= 5 ; j+=2 )
   {
      v2.push_back( - 2.0 * j );
      v2.push_back( 2.0 * j + 1.0 );
   }

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "The vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Testing for the element-wise equality between v1 & v2
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),
      equal_to<double>( ) );

   cout << "The result of the element-wise equal_to comparison\n"
      << "between v1 & v2 is: ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}
```

```Output
The vector v1 = ( 0 1 4 5 8 9 )
The vector v2 = ( -0 1 -4 5 -8 9 )
The result of the element-wise equal_to comparison
between v1 & v2 is: ( 1 1 0 1 0 1 )
```

