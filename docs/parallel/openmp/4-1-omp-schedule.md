---
title: 4.1 OMP_SCHEDULE |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d0dce411-2351-4ee9-a1cc-c0322a58b65c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e13332077a40e741f56b5602ac5197bbdfef071
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691045"
---
# <a name="41-ompschedule"></a>4.1 OMP_SCHEDULE
**OMP_SCHEDULE**仅适用于**为**和**为并行**指令具有计划类型**运行时**。 通过向任何已识别的计划类型和一个可选设置此环境变量，可以在运行时设置所有此类循环的计划类型和区块大小*使用 chunk_size*。  
  
 有关**为**和**为并行**具有计划类型以外的指令**运行时**， **OMP_SCHEDULE**将被忽略。 此环境变量的默认值是实现定义的。 如果可选*使用 chunk_size*值必须为正数的设置。 如果*使用 chunk_size*未设置，则假定此值为 1，除非的情况下**静态**计划。 有关**静态**计划，默认块区大小设置为除以应用于循环的线程数的循环迭代空间。  
  
 示例:  
  
```  
setenv OMP_SCHEDULE "guided,4"  
setenv OMP_SCHEDULE "dynamic"  
```  
  
## <a name="cross-references"></a>交叉引用：  
  
-   **有关**指令，请参阅[部分 2.4.1](../../parallel/openmp/2-4-1-for-construct.md)第 11 页上。  
  
-   **有关并行**指令，请参阅[部分 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md)第 16 页上。