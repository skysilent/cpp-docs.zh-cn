---
title: 将命令添加到菜单 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.menu
dev_langs:
- C++
helpviewer_keywords:
- menu items, adding to menus
- menus, adding items
- commands, adding to menus
- commands
- menu items
ms.assetid: 1523a755-0ab5-42f8-9e98-bb9881564431
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c0c744e920c71b74d9296e6961add704435658fe
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644724"
---
# <a name="adding-commands-to-a-menu"></a>将命令添加到菜单
### <a name="to-add-commands-to-a-menu"></a>将命令添加到菜单  
  
1.  [创建菜单](../windows/creating-a-menu.md)。  
  
2.  单击菜单名，例如**文件**。  
  
     每个菜单都将展开，并显示一个新项框让你输入命令。 例如，可以将命令添加**新建**，**打开**，并**关闭**到**文件**菜单。  
  
3.  在新项框中，键入新菜单命令的名称。  
  
    > [!NOTE]
    >  键入的文本将同时出现在 **菜单** 编辑器 以及 **属性窗口** 中的 [“标题”](/visualstudio/ide/reference/properties-window)框中。 你可以在任一位置编辑新菜单的属性。  
  
    > [!TIP]
    >  你可以定义一个允许用户选择菜单命令的助记键（热键）。 输入与号 (`&`) 若要指定为助记键的某个字母前。 用户可以通过键入该字母来选择菜单命令。  
  
4.  在中**属性**窗口中，选择菜单命令适用的属性。 有关详细信息，请参阅[菜单命令属性](../windows/menu-command-properties.md)。  
  
5.  在中**提示符**框中**属性**窗口中，键入你想要在应用程序的状态栏中显示的提示字符串。  
  
     这将在字符串表中创建一个条目，该条目的资源标识符与你创建的菜单命令相同。  
  
    > [!NOTE]
    >  提示只能应用于菜单项**Popup**的属性**True**。 例如，包含子菜单项的顶级菜单项可以有提示。 目的**提示**用于指示会发生什么情况是如果用户单击菜单项。  
  
6.  按**Enter**完成菜单命令。  
  
     将选定新项框，让你可以创建其他菜单命令。  
  
## <a name="requirements"></a>要求  
 Win32  
  
## <a name="see-also"></a>请参阅  
 [菜单编辑器](../windows/menu-editor.md)   