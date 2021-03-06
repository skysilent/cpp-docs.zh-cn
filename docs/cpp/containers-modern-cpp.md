---
title: 容器 （现代 C++） |Microsoft 文档
ms.custom: ''
ms.date: 1/18/2018
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d740bb36c1d574e474058c05d900d605c71e55f0
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406329"
---
# <a name="containers-modern-c"></a>容器（现代 C++）

默认情况下，使用[向量](../standard-library/vector-class.md)作为 C++ 中的首选顺序容器。 这相当于`List<T>`用.NET 语言。

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

使用[地图](../standard-library/map-class.md)(不`unordered_map`) 作为默认关联容器。 使用[设置](../standard-library/set-class.md)，[多重映射](../standard-library/multimap-class.md)，并[多重集](../standard-library/multiset-class.md)退化 & 多用例。

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

当需要性能优化时，请考虑使用：

- [数组](../standard-library/array-class-stl.md)键入时嵌入是重要的是，例如，作为类成员。

- 如无序的关联容器[unordered_map](../standard-library/unordered-map-class.md)。 这些开销具有较低的每个元素和常数时间查找，但它们可能很难正确有效地使用。

- 排序`vector`。 有关详细信息，请参阅[算法](../cpp/algorithms-modern-cpp.md)。

不要使用 C 样式数组。 对于需要直接访问数据的较旧的 Api，使用访问器方法如`f(vec.data(), vec.size());`相反。

有关容器的详细信息，请参阅[C++ 标准库容器](../standard-library/stl-containers.md)。

## <a name="see-also"></a>请参阅
 [欢迎回到 C++](../cpp/welcome-back-to-cpp-modern-cpp.md)  
 [C++ 语言参考](../cpp/cpp-language-reference.md)  
 [C++ 标准库](../standard-library/cpp-standard-library-reference.md)  