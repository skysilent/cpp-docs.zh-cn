---
title: extent 类 | Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::extent
dev_langs:
- C++
helpviewer_keywords:
- extent class
- extent
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2e6df4526eea3b0b8b4e91fa4f3e6a89cdd8adb7
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964305"
---
# <a name="extent-class"></a>extent 类

获取数组维度。

## <a name="syntax"></a>语法

```cpp
template <class Ty, unsigned I = 0>
struct extent;
```

### <a name="parameters"></a>参数

*Ty*查询的类型。

*我*数组绑定到查询。

## <a name="remarks"></a>备注

如果*Ty*是至少具有一个数组类型*我*维度，则类型查询保留的元素数中由指定的维度*我*。如果*Ty*不是数组类型或它的级别小于*我*，或者，如果*我*为零并*Ty*属于类型"未知绑定的数组的`U`"，则类型查询保留值 0。

## <a name="example"></a>示例

```cpp
// std__type_traits__extent.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "extent 0 == "
        << std::extent<int[5][10]>::value << std::endl;
    std::cout << "extent 1 == "
        << std::extent<int[5][10], 1>::value << std::endl;

    return (0);
    }

```

```Output
extent 0 == 5
extent 1 == 10
```

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间：** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_all_extents 类](../standard-library/remove-all-extents-class.md)<br/>
[remove_extent 类](../standard-library/remove-extent-class.md)<br/>
