---
title: 3.3.1 omp_get_wtime 函数 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d71296d23df72464ed730713566c95e2403760a1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689488"
---
# <a name="331-ompgetwtime-function"></a>3.3.1 omp_get_wtime 函数
`omp_get_wtime`函数将返回以秒为单位，由于某些"过去的时间"的已用的挂钟时间双精度浮点值。  实际"过去的时间"是任意的但可以保证无法应用程序执行期间发生更改。 格式如下所示：  
  
```  
#include <omp.h>  
double omp_get_wtime(void);  
```  
  
 我们已预见到该函数将用于度量经过的时间，如下面的示例中所示：  
  
```  
double start;  
double end;  
start = omp_get_wtime();  
... work to be timed ...  
end = omp_get_wtime();  
printf_s("Work took %f sec. time.\n", end-start);  
```  
  
 返回的时间都"每个线程时间"这为了不需要它们来参与应用程序的所有线程都是全局一致。