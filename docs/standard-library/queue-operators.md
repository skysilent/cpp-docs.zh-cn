---
title: '&lt;queue&gt; 运算符 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- queue/std::operator!=
- queue/std::operator&gt;
- queue/std::operator&gt;=
- queue/std::operator&lt;
- queue/std::operator&lt;=
- queue/std::operator==
dev_langs:
- C++
ms.assetid: 7c435b48-175c-45b0-88eb-24561044019c
helpviewer_keywords:
- std::operator!= (queue)
- std::operator&gt; (queue)
- std::operator&gt;= (queue)
- std::operator&lt; (queue)
- std::operator&lt;= (queue)
- std::operator== (queue)
ms.openlocfilehash: 138eddc6704b5e12798ccceacc5b3f37b3df1d96
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958287"
---
# <a name="ltqueuegt-operators"></a>&lt;queue&gt; 运算符

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>operator!=

测试运算符左侧和右侧的 queue 对象是否不相等。

```cpp
bool operator!=(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```

### <a name="parameters"></a>参数

*左*类型的对象`queue`。

*右*类型的对象`queue`。

### <a name="return-value"></a>返回值

如果两个队列不相等，则为 **true**；如果队列相等，则为 **false**。

### <a name="remarks"></a>备注

队列对象之间的比较基于其元素的成对比较。 如果两个队列具有的元素数目相等且对应元素具有相同的值，则两个队列相等。 否则，它们不相等。

### <a name="example"></a>示例

```cpp
// queue_op_ne.cpp
// compile with: /EHsc
#include <queue>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares queues with list base containers
   queue <int, list<int> > q1, q2, q3;

   // The following line would have caused an error because vector
   // does not support pop_front( ) and so cannot be adapted
   // by queue as a base container
   // queue <int, vector<int> > q1, q2, q3;

   q1.push( 1 );
   q2.push( 1 );
   q2.push( 2 );
   q3.push( 1 );

   if ( q1 != q2 )
      cout << "The queues q1 and q2 are not equal." << endl;
   else
      cout << "The queues q1 and q2 are equal." << endl;

   if ( q1 != q3 )
      cout << "The queues q1 and q3 are not equal." << endl;
   else
      cout << "The queues q1 and q3 are equal." << endl;
}
```

```Output
The queues q1 and q2 are not equal.
The queues q1 and q3 are equal.
```

## <a name="op_lt"></a>operator&lt;

测试运算符左侧的 queue 对象是否小于右侧的 queue 对象。

```cpp
bool operator<(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```

### <a name="parameters"></a>参数

*左*类型的对象`queue`。

*右*类型的对象`queue`。

### <a name="return-value"></a>返回值

如果运算符左侧的队列小于但不等于运算符右侧的队列，则为 **true**，否则为 **false**。

### <a name="remarks"></a>备注

队列对象之间的比较基于其元素的成对比较。 两个队列对象之间的小于关系基于首对不相等元素之间的比较。

### <a name="example"></a>示例

```cpp
// queue_op_lt.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares queues with default deque base container
   queue <int> q1, q2, q3;

   q1.push( 1 );
   q1.push( 2 );
   q2.push( 5 );
   q2.push( 10 );
   q3.push( 1 );
   q3.push( 2 );

   if ( q1 < q2 )
      cout << "The queue q1 is less than the queue q2." << endl;
   else
      cout << "The queue q1 is not less than the queue q2." << endl;

   if ( q1 < q3 )
      cout << "The queue q1 is less than the queue q3." << endl;
   else
      cout << "The queue q1 is not less than the queue q3." << endl;
}
```

```Output
The queue q1 is less than the queue q2.
The queue q1 is not less than the queue q3.
```

## <a name="op_lt_eq"></a>  operator&lt;=

测试运算符左侧的 queue 对象是否小于或等于右侧的 queue 对象。

```cpp
bool operator<=(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```

### <a name="parameters"></a>参数

*左*类型的对象`queue`。

*右*类型的对象`queue`。

### <a name="return-value"></a>返回值

如果运算符左侧的队列严格小于运算符右侧的队列，则为 **true**；否则为 **false**。

### <a name="remarks"></a>备注

队列对象之间的比较基于其元素的成对比较。 两个队列对象之间的小于或等于关系基于首对不相等元素的比较。

### <a name="example"></a>示例

```cpp
// queue_op_le.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;
   queue <int> q1, q2, q3;

   q1.push( 5 );
   q1.push( 10 );
   q2.push( 1 );
   q2.push( 2 );
   q3.push( 5 );
   q3.push( 10 );

   if ( q1 <= q2 )
      cout << "The queue q1 is less than or equal to "
           << "the queue q2." << endl;
   else
      cout << "The queue q1 is greater than "
           << "the queue q2." << endl;

   if ( q1 <= q3 )
      cout << "The queue q1 is less than or equal to "
           << "the queue q3." << endl;
   else
      cout << "The queue q1 is greater than "
           << "the queue q3." << endl;
}
```

```Output
The queue q1 is greater than the queue q2.
The queue q1 is less than or equal to the queue q3.
```

## <a name="op_eq_eq"></a>operator==

测试运算符左侧和右侧的队列对象是否相等。

```cpp
bool operator==(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```

### <a name="parameters"></a>参数

*左*类型的对象`queue`。

*右*类型的对象`queue`。

### <a name="return-value"></a>返回值

如果两个队列不相等，则为 **true**；如果队列相等，则为 **false**。

### <a name="remarks"></a>备注

队列对象之间的比较基于其元素的成对比较。 如果两个队列具有的元素数目相等且对应元素具有相同的值，则两个队列相等。 否则，它们不相等。

### <a name="example"></a>示例

```cpp
// queue_op_eq.cpp
// compile with: /EHsc
#include <queue>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares queues with list base containers
   queue <int, list<int> > q1, q2, q3;

   // The following line would have caused an error because vector
   // does not support pop_front( ) and so cannot be adapted
   // by queue as a base container
   // queue <int, vector<int> > q1, q2, q3;

   q1.push( 1 );
   q2.push( 2 );
   q3.push( 1 );

   if ( q1 != q2 )
      cout << "The queues q1 and q2 are not equal." << endl;
   else
      cout << "The queues q1 and q2 are equal." << endl;

   if ( q1 != q3 )
      cout << "The queues q1 and q3 are not equal." << endl;
   else
      cout << "The queues q1 and q3 are equal." << endl;
}
```

```Output
The queues q1 and q2 are not equal.
The queues q1 and q3 are equal.
```

## <a name="op_gt"></a>operator&gt;

测试运算符左侧的 queue 对象是否大于右侧的 queue 对象。

```cpp
bool operator>(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```

### <a name="parameters"></a>参数

*左*类型的对象`queue`。

*右*类型的对象`queue`。

### <a name="return-value"></a>返回值

如果运算符左侧的队列严格小于运算符右侧的队列，则为 **true**；否则为 **false**。

### <a name="remarks"></a>备注

队列对象之间的比较基于其元素的成对比较。 两个队列对象之间的大于关系基于首对不相等元素之间的比较。

### <a name="example"></a>示例

```cpp
// queue_op_gt.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;
   queue <int> q1, q2, q3;

   q1.push( 1 );
   q1.push( 2 );
   q1.push( 3 );
   q2.push( 5 );
   q2.push( 10 );
   q3.push( 1 );
   q3.push( 2 );

   if ( q1 > q2 )
      cout << "The queue q1 is greater than "
           << "the queue q2." << endl;
   else
      cout << "The queue q1 is not greater than "
           << "the queue q2." << endl;

   if ( q1> q3 )
      cout << "The queue q1 is greater than "
           << "the queue q3." << endl;
   else
      cout << "The queue q1 is not greater than "
           << "the queue q3." << endl;
}
```

```Output
The queue q1 is not greater than the queue q2.
The queue q1 is greater than the queue q3.
```

## <a name="op_gt_eq"></a>  operator&gt;=

测试运算符左侧的 queue 对象是否大于或等于右侧的 queue 对象。

```cpp
bool operator>=(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```

### <a name="parameters"></a>参数

*左*类型的对象`queue`。

*右*类型的对象`queue`。

### <a name="return-value"></a>返回值

如果运算符左侧的队列严格小于运算符右侧的队列，则为 **true**；否则为 **false**。

### <a name="remarks"></a>备注

队列对象之间的比较基于其元素的成对比较。 如果两个队列具有的元素数目相等且对应元素具有相同的值，则两个队列相等。 否则，它们不相等。

### <a name="example"></a>示例

```cpp
// queue_op_ge.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;
   queue <int> q1, q2, q3;

   q1.push( 1 );
   q1.push( 2 );
   q2.push( 5 );
   q2.push( 10 );
   q3.push( 1 );
   q3.push( 2 );

   if ( q1 >= q2 )
      cout << "The queue q1 is greater than or equal to "
           << "the queue q2." << endl;
   else
      cout << "The queue q1 is less than "
           << "the queue q2." << endl;

   if ( q1>= q3 )
      cout << "The queue q1 is greater than or equal to "
           << "the queue q3." << endl;
   else
      cout << "The queue q1 is less than "
           << "the queue q3." << endl;
}
```

```Output
The queue q1 is less than the queue q2.
The queue q1 is greater than or equal to the queue q3.
```

## <a name="see-also"></a>请参阅

[\<queue>](../standard-library/queue.md)<br/>
