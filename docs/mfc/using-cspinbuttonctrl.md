---
title: 使用 CSpinButtonCtrl |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CSpinButtonCtrl
dev_langs:
- C++
helpviewer_keywords:
- up-down controls [MFC], spin button control
- up-down controls
- spin button control
- CSpinButtonCtrl class [MFC], using
ms.assetid: a91db36b-e11e-42ef-8e89-51915cc486d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bea2f2f51ed3b012ee9b5afe2572b2a6be9e0d57
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955477"
---
# <a name="using-cspinbuttonctrl"></a>使用 CSpinButtonCtrl
*数值调节钮*控件 (也称为*上下*控制) 提供了一对用户可以单击来调整值的箭头。 此值称为*当前位置*。 此位置位于数值调节钮的范围内。 当用户单击向上箭头，位置将朝着最大值移动；当用户单击向下箭头，位置将朝着最小值移动。  
  
 数值调节钮控件表示在 MFC 中由[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)类。  
  
> [!NOTE]
>  默认情况下，数值调节钮的范围最大设置为零 (0)，最小设置为 100。 由于最大值小于最小值，因此单击上箭头将降低位置，单击下箭头将增高位置。 使用[cspinbuttonctrl:: Setrange](../mfc/reference/cspinbuttonctrl-class.md#setrange)来调整这些值。  
  
 通常，当前位置显示在附带控件中。 附带控件称为*合作者窗口*。 数值调节钮控件的图例，请参阅[有关 Up-down 控件](http://msdn.microsoft.com/library/windows/desktop/bb759889)Windows SDK 中。  
  
 若要在 Visual Studio 中创建数值调节钮控件和编辑控件合作者窗口，请先将编辑控件拖至对话框或窗口，然后拖动数值调节钮控件。 选择数值调节钮控件并设置其**Auto Buddy**和**设置 Buddy Integer**属性设置为**True**。 此外设置**对齐**属性;**右对齐**最典型。 在这些设置中，编辑控件将设置为合作者窗口，因为合作者窗口将直接按选项卡顺序位于编辑控件前。 编辑控件将显示整数，数值调节钮控件将嵌入编辑控件右侧。 （可选） 可以通过使用设置数值调节钮控件的有效范围内[cspinbuttonctrl:: Setrange](../mfc/reference/cspinbuttonctrl-class.md#setrange)方法。 在数值调节钮控件与合作者窗口之间通信无需任何事件处理程序，因为它们直接交换数据。 如果因其他目的使用数值调节钮控件，例如，为了浏览一系列窗口或对话框，然后添加的处理程序 UDN_DELTAPOS 消息并执行自定义操作。  
  
## <a name="what-do-you-want-to-know-more-about"></a>你想进一步了解什么  
  
-   [调节按钮样式](../mfc/spin-button-styles.md)  
  
-   [调节按钮成员函数](../mfc/spin-button-member-functions.md)  
  
## <a name="see-also"></a>请参阅  
 [控件](../mfc/controls-mfc.md)

