---
title: 符号名限制 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.restrictions.name
dev_langs:
- C++
helpviewer_keywords:
- symbol names
- symbols, names
- restrictions, symbol names
ms.assetid: 4ae7f695-ca86-4f4b-989a-fe6f89650ff7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 30852b22c9ff4cc74c8f0c57b3a5ed9d79a34838
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011443"
---
# <a name="symbol-name-restrictions"></a>符号名限制
对符号名的限制如下所示：  
  
-   所有[符号](../windows/symbols-resource-identifiers.md)必须是唯一的应用程序的作用域内。 这样可防止头文件中出现冲突的符号定义。  
  
-   符号名的有效字符包括 A-Z、a-z、0-9 和下划线 (_)。  
  
-   符号名不能以数字开头，仅限于 247 个字符。  
  
-   符号名不能包含空格。  
  
-   符号名不区分大小写，但是第一个符号定义的大小写会保留。 定义符号的头文件由资源编译器/编辑器和 C++ 程序用于引用资源文件中定义的资源。 对于只有大小写不同的两个符号名，C++ 程序会看到两个单独的符号，而资源编译器/编辑器将这两个名称视为引用单个符号。  
  
    > [!NOTE]
    >  如果不遵循下面概述的标准符号名方案（ID*_[关键字]），并且符号名恰好与资源脚本编译器已知的关键字相同，则尝试生成资源脚本文件会导致看似难以进行诊断的随机错误生成。 若要防止出现此情况，请遵循标准命名方案。  
  
 符号名具有描述性前缀，可指示它们所表示的资源或对象的类型。 这些描述性前缀以文本组合 ID 开头。 Microsoft 基础类库 (MFC) 使用下表中所示的符号命名约定。  
  
|类别|前缀|使用|  
|--------------|------------|---------|  
|资源|IDR_ IDD_ IDC_ IDI_ IDB_|加速器或菜单（以及关联或自定义资源） 对话框 光标 图标 位图|  
|菜单项|ID_|Menu item|  
|命令|ID_|命令|  
|控件和子窗口|IDC_|控件|  
|字符串|IDS_|字符串表中的字符串|  
|MFC|AFX_|为预定义 MFC 符号保留|  
  
## <a name="requirements"></a>要求  
 Win32  
  
## <a name="see-also"></a>请参阅  
 [更改符号或符号名 (ID)](../windows/changing-a-symbol-or-symbol-name-id.md)   
 [符号值限制](../windows/symbol-value-restrictions.md)   
 [预定义的符号 ID](../windows/predefined-symbol-ids.md)