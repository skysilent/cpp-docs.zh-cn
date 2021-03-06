---
title: CMFCRibbonEdit 类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CanBeStretched
- AFXRIBBONEDIT/CMFCRibbonEdit::CopyFrom
- AFXRIBBONEDIT/CMFCRibbonEdit::CreateEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::DestroyCtrl
- AFXRIBBONEDIT/CMFCRibbonEdit::DropDownList
- AFXRIBBONEDIT/CMFCRibbonEdit::EnableSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::GetCompactSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::GetIntermediateSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::GetWidth
- AFXRIBBONEDIT/CMFCRibbonEdit::HasCompactMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasFocus
- AFXRIBBONEDIT/CMFCRibbonEdit::HasLargeMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::IsHighlighted
- AFXRIBBONEDIT/CMFCRibbonEdit::OnAfterChangeRect
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDraw
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawLabelAndImage
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawOnList
- AFXRIBBONEDIT/CMFCRibbonEdit::OnEnable
- AFXRIBBONEDIT/CMFCRibbonEdit::OnHighlight
- AFXRIBBONEDIT/CMFCRibbonEdit::OnKey
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonDown
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonUp
- AFXRIBBONEDIT/CMFCRibbonEdit::OnRTLChanged
- AFXRIBBONEDIT/CMFCRibbonEdit::OnShow
- AFXRIBBONEDIT/CMFCRibbonEdit::Redraw
- AFXRIBBONEDIT/CMFCRibbonEdit::SetACCData
- AFXRIBBONEDIT/CMFCRibbonEdit::SetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::SetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::SetWidth
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CanBeStretched
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CopyFrom
- CMFCRibbonEdit [MFC], CreateEdit
- CMFCRibbonEdit [MFC], DestroyCtrl
- CMFCRibbonEdit [MFC], DropDownList
- CMFCRibbonEdit [MFC], EnableSpinButtons
- CMFCRibbonEdit [MFC], GetCompactSize
- CMFCRibbonEdit [MFC], GetEditText
- CMFCRibbonEdit [MFC], GetIntermediateSize
- CMFCRibbonEdit [MFC], GetTextAlign
- CMFCRibbonEdit [MFC], GetWidth
- CMFCRibbonEdit [MFC], HasCompactMode
- CMFCRibbonEdit [MFC], HasFocus
- CMFCRibbonEdit [MFC], HasLargeMode
- CMFCRibbonEdit [MFC], HasSpinButtons
- CMFCRibbonEdit [MFC], IsHighlighted
- CMFCRibbonEdit [MFC], OnAfterChangeRect
- CMFCRibbonEdit [MFC], OnDraw
- CMFCRibbonEdit [MFC], OnDrawLabelAndImage
- CMFCRibbonEdit [MFC], OnDrawOnList
- CMFCRibbonEdit [MFC], OnEnable
- CMFCRibbonEdit [MFC], OnHighlight
- CMFCRibbonEdit [MFC], OnKey
- CMFCRibbonEdit [MFC], OnLButtonDown
- CMFCRibbonEdit [MFC], OnLButtonUp
- CMFCRibbonEdit [MFC], OnRTLChanged
- CMFCRibbonEdit [MFC], OnShow
- CMFCRibbonEdit [MFC], Redraw
- CMFCRibbonEdit [MFC], SetACCData
- CMFCRibbonEdit [MFC], SetEditText
- CMFCRibbonEdit [MFC], SetTextAlign
- CMFCRibbonEdit [MFC], SetWidth
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 62a27548d51d3de1a27da0b765bd85439467c024
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850217"
---
# <a name="cmfcribbonedit-class"></a>CMFCRibbonEdit 类
在功能区栏上实现位于一个编辑控件。  
  
## <a name="syntax"></a>语法  
  
```  
class CMFCRibbonEdit : public CMFCRibbonButton  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|构造 `CMFCRibbonEdit` 对象。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[CMFCRibbonEdit::CanBeStretched](#canbestretched)|指示是否的高度`CMFCRibbonEdit`控件可以垂直方向上增加到功能区行的高度。|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|构造 `CMFCRibbonEdit` 对象。|  
|[CMFCRibbonEdit::CopyFrom](#copyfrom)|复制指定的状态`CMFCRibbonEdit`对象与当前`CMFCRibbonEdit`对象。|  
|[CMFCRibbonEdit::CreateEdit](#createedit)|创建一个新的文本框为`CMFCRibbonEdit`对象。|  
|[CMFCRibbonEdit::DestroyCtrl](#destroyctrl)|销毁`CMFCRibbonEdit`对象。|  
|[CMFCRibbonEdit::DropDownList](#dropdownlist)|下拉列表框。|  
|[CMFCRibbonEdit::EnableSpinButtons](#enablespinbuttons)|启用并设置文本框中按钮的数值调节钮的范围。|  
|[CMFCRibbonEdit::GetCompactSize](#getcompactsize)|检索的压缩大小`CFMCRibbonEdit`对象。|  
|[CMFCRibbonEdit::GetEditText](#getedittext)|检索在文本框中的文本。|  
|[CMFCRibbonEdit::GetIntermediateSize](#getintermediatesize)|检索的中间大小`CMFCRibbonEdit`对象。|  
|[CMFCRibbonEdit::GetTextAlign](#gettextalign)|检索在文本框中的文本的对齐方式。|  
|[CMFCRibbonEdit::GetWidth](#getwidth)|检索的宽度，以像素为单位的`CMFCRibbonEdit`控件。|  
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|指示是否显示大小调整为`CMFCRibbonEdit`控件可以 compact。|  
|[CMFCRibbonEdit::HasFocus](#hasfocus)|指示是否`CMFCRIbbonEdit`控件具有焦点。|  
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|指示是否显示大小调整为`CMFCRibbonEdit`控件可能会大。|  
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|指示文本框是否具有调节按钮。|  
|[CMFCRibbonEdit::IsHighlighted](#ishighlighted)|指示是否`CMFCRibbonEdit`突出显示的控件。|  
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|由框架调用时的显示矩形的尺寸`CMFCRibbonEdit`控件发生更改。|  
|[CMFCRibbonEdit::OnDraw](#ondraw)|由框架调用以绘制`CMFCRibbonEdit`控件。|  
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|由框架调用以绘制标签和图像的`CMFCRibbonEdit`控件。|  
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|由框架调用以绘制`CMFCRibbonEdit`命令列表框中的控件。|  
|[CMFCRibbonEdit::OnEnable](#onenable)|由框架调用以启用或禁用`CMFCRibbonEdit`控件。|  
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|鼠标指针进入或离开的边界时由框架调用`CMFCRibbonEdit`控件。|  
|[CMFCRibbonEdit::OnKey](#onkey)|在用户按快捷键提示时由框架调用和`CMFCRibbonEdit`控件具有焦点。|  
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|由框架调用以更新`CMFCRibbonEdit`控制用户在控件上按鼠标左键。|  
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|当用户释放鼠标按钮时由框架调用。|  
|[CMFCRibbonEdit::OnRTLChanged](#onrtlchanged)|由框架调用以更新`CMFCRibbonEdit`控制当布局更改方向。|  
|[CMFCRibbonEdit::OnShow](#onshow)|由框架调用以显示或隐藏`CMFCRibbonEdit`控件。|  
|[CMFCRibbonEdit::Redraw](#redraw)|更新的显示`CMFCRibbonEdit`控件。|  
|[CMFCRibbonEdit::SetACCData](#setaccdata)|设置的可访问性数据`CMFCRibbonEdit`对象。|  
|[CMFCRibbonEdit::SetEditText](#setedittext)|在文本框中设置的文本。|  
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|设置文本框中的文本对齐方式。|  
|[CMFCRibbonEdit::SetWidth](#setwidth)|设置文本框的宽度`CMFCRibbonEdit`控件。|  
  
## <a name="remarks"></a>备注  
  
## <a name="example"></a>示例  
 下面的示例演示如何构造`CMFCRibbonEdit`对象，显示数值调节钮按钮旁边的编辑控件，并设置在编辑控件的文本。 此代码片段属于[MS Office 2007 演示示例](../../visual-cpp-samples.md)。  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]  
  
## <a name="requirements"></a>要求  
 **标头：** afxRibbonEdit.h  
  
##  <a name="canbestretched"></a>  CMFCRibbonEdit::CanBeStretched  
 指示是否的高度[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)控件可以垂直方向上增加到功能区行的高度。  
  
```  
virtual BOOL CanBeStretched();
```  
  
### <a name="return-value"></a>返回值  
 始终返回 FALSE。  
  
### <a name="remarks"></a>备注  
  
##  <a name="cmfcribbonedit"></a>  CMFCRibbonEdit::CMFCRibbonEdit  
 构造[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)对象。  
  
```  
CMFCRibbonEdit(
    UINT nID,  
    int nWidth,  
    LPCTSTR lpszLabel = NULL,  
    int nImage = -1);

CMFCRibbonEdit();
```  
  
### <a name="parameters"></a>参数  
 [in]*nID*  
 命令 ID`CMFCRibbonEdit`控件。  
  
 [in]*nWidth*  
 宽度，以像素为单位的文本框`CMFCRibbonEdit`控件。  
  
 [in]*lpszLabel*  
 对于标签`CMFCRibbonEdit`控件。  
  
 [in]*nImage*  
 要使用的小图像索引`CMFCRibbonEdit`控件。 由父功能区类别进行维护的较小的图像集合。  
  
### <a name="remarks"></a>备注  
 `CMFCRibbonEdit`控件不使用大图像。  
  
##  <a name="copyfrom"></a>  CMFCRibbonEdit::CopyFrom  
 复制指定的状态[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)对象与当前[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)对象。  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>参数  
 [in]*src*  
 源 `CMFCRibbonEdit` 对象。  
  
### <a name="remarks"></a>备注  
 *Src*参数必须为类型`CMFCRibbonEdit`。  
  
##  <a name="createedit"></a>  CMFCRibbonEdit::CreateEdit  
 创建的一个新文本框[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)对象。  
  
```  
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,  
    DWORD dwEditStyle);
```  
  
### <a name="parameters"></a>参数  
 [in]*pWndParent*  
 向父窗口的指针`CMFCRibbonEdit`对象。  
  
 [in]*dwEditStyle*  
 指定文本框的样式。 你可以组合备注部分中列出的窗口样式[编辑控件样式](http://msdn.microsoft.com/library/windows/desktop/bb775464)的 Windows SDK 中所述。  
  
### <a name="return-value"></a>返回值  
 一个指向新的文本框中，如果该方法成功，则否则，为 NULL。  
  
### <a name="remarks"></a>备注  
 重写此方法在派生类以创建自定义文本框中。  
  
 可以将应用以下[的窗口样式](../../mfc/reference/styles-used-by-mfc.md#window-styles)的文本框：  
  
- **WS_CHILD**  
  
- **WS_VISIBLE**  
  
- **WS_DISABLED**  
  
- **WS_GROUP**  
  
- **WS_TABSTOP**  
  
##  <a name="destroyctrl"></a>  CMFCRibbonEdit::DestroyCtrl  
 销毁[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)对象。  
  
```  
virtual void DestroyCtrl();
```  
  
### <a name="remarks"></a>备注  
  
##  <a name="dropdownlist"></a>  CMFCRibbonEdit::DropDownList  
 下拉列表框。  
  
```  
virtual void DropDownList();
```  
  
### <a name="remarks"></a>备注  
 默认情况下此方法没有任何影响。 重写此方法以下拉列表框。  
  
##  <a name="enablespinbuttons"></a>  CMFCRibbonEdit::EnableSpinButtons  
 启用并设置文本框中按钮的数值调节钮的范围。  
  
```  
void EnableSpinButtons(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>参数  
 [in]*nMin*  
 调节按钮最小值。  
  
 [in]*最*  
 数值调节钮的最大值。  
  
### <a name="remarks"></a>备注  
 数值调节钮按钮显示向上和向下箭头，使用户能够浏览一组固定的值。  
  
##  <a name="getcompactsize"></a>  CMFCRibbonEdit::GetCompactSize  
 检索的压缩大小[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)对象。  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>参数  
 [in]*pDC*  
 指向设备上下文指针`CMFCRibbonEdit`对象。  
  
### <a name="return-value"></a>返回值  
 压缩大小`CMFCRibbonEdit`对象。  
  
### <a name="remarks"></a>备注  
  
##  <a name="getedittext"></a>  CMFCRibbonEdit::GetEditText  
 检索在文本框中的文本。  
  
```  
CString GetEditText() const;  
```  
  
### <a name="return-value"></a>返回值  
 在文本框中的文本。  
  
### <a name="remarks"></a>备注  
  
##  <a name="getintermediatesize"></a>  CMFCRibbonEdit::GetIntermediateSize  
 检索中间的大小[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)对象。  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>参数  
 [in]*pDC*  
 指向设备上下文指针`CMFCRibbonEdit`对象。  
  
### <a name="return-value"></a>返回值  
 中间的大小`CMFCRibbonEdit`对象。  
  
### <a name="remarks"></a>备注  
  
##  <a name="gettextalign"></a>  CMFCRibbonEdit::GetTextAlign  
 检索在文本框中的文本的对齐方式。  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>返回值  
 文本对齐方式枚举值。 请参阅备注部分中有关可能的值。  
  
### <a name="remarks"></a>备注  
 返回的值是以下的编辑控件样式之一：  
  
- **ES_LEFT**为左对齐  
  
- **ES_CENTER**为居中对齐  
  
- **ES_RIGHT**为右对齐  
  
 有关这些样式的详细信息，请参阅[编辑控件样式](http://msdn.microsoft.com/library/windows/desktop/bb775464)。  
  
##  <a name="getwidth"></a>  CMFCRibbonEdit::GetWidth  
 检索的宽度，以像素为单位， [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)控件。  
  
```  
int GetWidth(BOOL bInFloatyMode = FALSE) const;  
```  
  
### <a name="parameters"></a>参数  
 [in]*bInFloatyMode*  
 如果`CMFCRibbonEdit`控件是否处于浮动模式; 否则为 FALSE。  
  
### <a name="return-value"></a>返回值  
 宽度，以像素为单位的`CMFCRibbonEdit`控件。  
  
### <a name="remarks"></a>备注  
  
##  <a name="hascompactmode"></a>  CMFCRibbonEdit::HasCompactMode  
 指示是否显示大小调整为[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)控件可以 compact。  
  
```  
virtual BOOL HasCompactMode() const;  
```  
  
### <a name="return-value"></a>返回值  
 始终返回 TRUE。  
  
### <a name="remarks"></a>备注  
 默认情况下此方法始终返回 TRUE。 重写此方法，以指示是否显示大小可以为 compact。  
  
##  <a name="hasfocus"></a>  CMFCRibbonEdit::HasFocus  
 指示是否[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)控件具有焦点。  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>返回值  
 如果`CMFCRibbonEdit`控件具有焦点; 否则为 FALSE。  
  
### <a name="remarks"></a>备注  
  
##  <a name="haslargemode"></a>  CMFCRibbonEdit::HasLargeMode  
 指示是否显示大小调整为[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)控件可能会大。  
  
```  
virtual BOOL HasLargeMode() const;  
```  
  
### <a name="return-value"></a>返回值  
 始终返回 FALSE。  
  
### <a name="remarks"></a>备注  
 默认情况下此方法始终返回 FALSE。 重写此方法，以指示是否显示大小可以为大型。  
  
##  <a name="hasspinbuttons"></a>  CMFCRibbonEdit::HasSpinButtons  
 指示文本框是否具有调节按钮。  
  
```  
virtual BOOL HasSpinButtons() const;  
```  
  
### <a name="return-value"></a>返回值  
 如果文本框具有钮; 则为 TRUE否则为 FALSE。  
  
### <a name="remarks"></a>备注  
  
##  <a name="ishighlighted"></a>  CMFCRibbonEdit::IsHighlighted  
 指示是否[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)突出显示的控件。  
  
```  
virtual BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>返回值  
 如果`CMFCRibbonEdit`控件是突出显示; 否则为 FALSE。  
  
### <a name="remarks"></a>备注  
  
##  <a name="onafterchangerect"></a>  CMFCRibbonEdit::OnAfterChangeRect  
 由框架调用时的显示矩形的尺寸[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)控制更改。  
  
```  
virtual void OnAfterChangeRect(CDC* pDC);
```  
  
### <a name="parameters"></a>参数  
 [in]*pDC*  
 指向设备上下文指针`CMFCRibbonEdit`控件。  
  
### <a name="remarks"></a>备注  
  
##  <a name="ondraw"></a>  CMFCRibbonEdit::OnDraw  
 由框架调用以绘制[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)控件。  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>参数  
 [in]*pDC*  
 指向设备上下文指针`CMFCRibbonEdit`控件。  
  
### <a name="remarks"></a>备注  
  
##  <a name="ondrawlabelandimage"></a>  CMFCRibbonEdit::OnDrawLabelAndImage  
 由框架调用以绘制标签，并为图像[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)控件。  
  
```  
virtual void OnDrawLabelAndImage(CDC* pDC);
```  
  
### <a name="parameters"></a>参数  
 [in]*pDC*  
 指向设备上下文指针`CMFCRibbonEdit`控件。  
  
### <a name="remarks"></a>备注  
  
##  <a name="ondrawonlist"></a>  CMFCRibbonEdit::OnDrawOnList  
 由框架调用以绘制[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)命令列表框中的控件。  
  
```  
virtual void OnDrawOnList(
    CDC* pDC,  
    CString strText,  
    int nTextOffset,  
    CRect rect,  
    BOOL bIsSelected,  
    BOOL bHighlighted);
```  
  
### <a name="parameters"></a>参数  
 [in]*pDC*  
 指向设备上下文指针`CMFCRibbonEdit`控件。  
  
 [in]*strText*  
 显示文本[](../../mfc/reference/cmfcribbonedit-class.md "cmfcribbonedit 类")。  
  
 [in]*nTextOffset*  
 距离，以像素为单位，从左侧和右侧的显示文本的列表框。  
  
 [in]*rect*  
 显示矩形的`CMFCRibbonEdit`控件。  
  
 [in]*bIsSelected*  
 未使用此参数。  
  
 [in]*bHighlighted*  
 未使用此参数。  
  
### <a name="remarks"></a>备注  
 命令列表框中显示功能区控件使用户能够自定义快速访问工具栏。  
  
##  <a name="onenable"></a>  CMFCRibbonEdit::OnEnable  
 由框架调用以启用或禁用[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)控件。  
  
```  
virtual void OnEnable(BOOL bEnable);
```  
  
### <a name="parameters"></a>参数  
 [in]*bEnable*  
 为 true 以启用控件;如果为 FALSE 禁用控件。  
  
### <a name="remarks"></a>备注  
  
##  <a name="onhighlight"></a>  CMFCRibbonEdit::OnHighlight  
 鼠标指针进入或离开的边界时由框架调用[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)控件。  
  
```  
virtual void OnHighlight(BOOL bHighlight);
```  
  
### <a name="parameters"></a>参数  
 [in]*bHighlight*  
 如果指针的界限内`CMFCRibbonEdit`控件; 否则为 FALSE。  
  
### <a name="remarks"></a>备注  
  
##  <a name="onkey"></a>  CMFCRibbonEdit::OnKey  
 在用户按快捷键提示时由框架调用， [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)控件具有焦点。  
  
```  
virtual BOOL OnKey(BOOL bIsMenuKey);
```  
  
### <a name="parameters"></a>参数  
 [in]*bIsMenuKey*  
 如果快捷键提示会显示一个弹出菜单; 则为 TRUE否则为 FALSE。  
  
### <a name="return-value"></a>返回值  
 如果已处理的事件; 则为 TRUE否则为 FALSE。  
  
### <a name="remarks"></a>备注  
  
##  <a name="onlbuttondown"></a>  CMFCRibbonEdit::OnLButtonDown  
 由框架调用以更新[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)控制用户在控件上按鼠标左键。  
  
```  
virtual void OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>参数  
 [in]*点*  
 未使用此参数。  
  
### <a name="remarks"></a>备注  
  
##  <a name="onlbuttonup"></a>  CMFCRibbonEdit::OnLButtonUp  
 当用户释放鼠标按钮时由框架调用。  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>参数  
 [in]*点*  
 未使用此参数。  
  
### <a name="remarks"></a>备注  
  
##  <a name="onrtlchanged"></a>  CMFCRibbonEdit::OnRTLChanged  
 由框架调用以更新[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)控制当布局更改方向。  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>参数  
 [in]*bIsRTL*  
 如果布局是从右到左; 则为 TRUE如果布局是从左到右，则为 FALSE。  
  
### <a name="remarks"></a>备注  
  
##  <a name="onshow"></a>  CMFCRibbonEdit::OnShow  
 由框架调用以显示或隐藏[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)控件。  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>参数  
 [in]*bShow*  
 显示控件，则为 TRUE如果为 FALSE，则将隐藏该控件。  
  
### <a name="remarks"></a>备注  
  
##  <a name="redraw"></a>  CMFCRibbonEdit::Redraw  
 更新的显示[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)控件。  
  
```  
virtual void Redraw();
```  
  
### <a name="remarks"></a>备注  
 此方法将重新绘制的显示矩形`CMFCRibbonEdit`通过间接调用的对象[CWnd::RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911)与 RDW_INVALIDATE、 RDW_ERASE 和 RDW_UPDATENOW 标志设置。  
  
##  <a name="setaccdata"></a>  CMFCRibbonEdit::SetACCData  
 设置的可访问性数据[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)对象。  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>参数  
 *pParent*  
 向父窗口的指针`CMFCRibbonEdit`对象。  
  
 *data*  
 可访问性数据`CMFCRibbonEdit`对象。  
  
### <a name="return-value"></a>返回值  
 始终返回 TRUE。  
  
### <a name="remarks"></a>备注  
  
##  <a name="setedittext"></a>  CMFCRibbonEdit::SetEditText  
 在文本框中设置的文本。  
  
```  
void SetEditText(CString strText);
```  
  
### <a name="parameters"></a>参数  
 [in]*strText*  
 在文本框中的文本。  
  
##  <a name="settextalign"></a>  CMFCRibbonEdit::SetTextAlign  
 设置文本框中的文本对齐方式。  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>参数  
 [in]*nAlign*  
 文本对齐方式枚举值。 请参阅备注部分中有关可能的值。  
  
### <a name="remarks"></a>备注  
 将参数*nAlign*是一个以下编辑控件样式：  
  
- ES_LEFT 为左对齐的  
  
- ES_CENTER 为居中对齐的  
  
- ES_RIGHT 为右对齐的  
  
 有关这些样式的详细信息，请参阅[编辑控件样式](http://msdn.microsoft.com/library/windows/desktop/bb775464)。  
  
##  <a name="setwidth"></a>  CMFCRibbonEdit::SetWidth  
 设置文本框的宽度[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)控件。  
  
```  
void SetWidth(
    int nWidth,  
    BOOL bInFloatyMode = FALSE);
```  
  
### <a name="parameters"></a>参数  
 [in]*nWidth*  
 以像素为单位，文本框的宽度。  
  
 *bInFloatyMode*  
 若要将设置为浮动模式; 宽度如果为 FALSE，则若要设置的常规模式的宽度。  
  
### <a name="remarks"></a>备注  
 `CMFCRibbonEdit`控件具有两个宽度，具体取决于其的显示模式： 浮点模式和常规显示模式。  
  
## <a name="see-also"></a>请参阅  
 [层次结构图表](../../mfc/hierarchy-chart.md)   
 [类](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton 类](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonBar 类](../../mfc/reference/cmfcribbonbar-class.md)