---
title: qsort | Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- qsort
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- qsort
dev_langs:
- C++
helpviewer_keywords:
- qsort function
- quick-sort algorithm
- sorting arrays
- arrays [CRT], sorting
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ac444680a22a99f292b1728181103789435a150
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404703"
---
# <a name="qsort"></a>qsort

执行快速排序。 此函数有一个更安全的版本；请参阅 [qsort_s](qsort-s.md)。

## <a name="syntax"></a>语法

```C
void qsort(
   void *base,
   size_t num,
   size_t width,
   int (__cdecl *compare )(const void *, const void *)
);
```

### <a name="parameters"></a>参数

*基*目标数组的开头。

*数*数组中元素的大小。

*宽度*元素大小 （字节）。

*比较*到用户提供比较两个数组元素并返回一个值，指定其关系的例程的指针。

## <a name="remarks"></a>备注

**Qsort**函数可实现快速排序算法进行排序的数组*数*元素，每个*宽度*字节。 自变量*基*是指向要进行排序的数组的基类的指针。 **qsort**将使用的已排序的元素覆盖此数组。

**qsort**调用*比较*例程的一个或多个时间期间排序，并将指针传递给两个数组元素，在每次调用。

```C
compare( (void *) & elem1, (void *) & elem2 );
```

该例程将比较元素，并返回下列值之一。

|比较函数返回值|描述|
|-----------------------------------|-----------------|
|< 0|**elem1**小于**elem2**|
|0|**elem1**等效于**elem2**|
|> 0|**elem1**大于**elem2**|

数组按比较函数中定义的升序进行排序。 若要以降序对数组进行排序，请反转比较函数中的“大于”和“小于”的意义。

此函数验证其参数。 如果*比较*或*数*是**NULL**，或者如果*基*是**NULL**和 **数*不为零，或者如果*宽度*小于零，无效参数处理程序调用时中, 所述[参数验证](../../c-runtime-library/parameter-validation.md)。 如果允许执行继续，函数将返回和**errno**设置为**EINVAL**。

## <a name="requirements"></a>要求

|例程|必需的标头|
|-------------|---------------------|
|**qsort**|\<stdlib.h> 和 \<search.h>|

有关其他兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_qsort.c
// arguments: every good boy deserves favor

/* This program reads the command-line
* parameters and uses qsort to sort them. It
* then displays the sorted arguments.
*/

#include <stdlib.h>
#include <string.h>
#include <stdio.h>

int compare( const void *arg1, const void *arg2 );

int main( int argc, char **argv )
{
   int i;
   /* Eliminate argv[0] from sort: */
   argv++;
   argc--;

   /* Sort remaining args using Quicksort algorithm: */
   qsort( (void *)argv, (size_t)argc, sizeof( char * ), compare );

   /* Output sorted list: */
   for( i = 0; i < argc; ++i )
      printf( " %s", argv[i] );
   printf( "\n" );
}

int compare( const void *arg1, const void *arg2 )
{
   /* Compare all of both strings: */
   return _stricmp( * ( char** ) arg1, * ( char** ) arg2 );
}
```

```Output
boy deserves every favor good
```

## <a name="see-also"></a>请参阅

[搜索和排序](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch](bsearch.md)<br/>
[_lsearch](lsearch.md)<br/>
