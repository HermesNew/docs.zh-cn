---
title: 如何：检测鼠标指针何时在 ToolStripItem 上
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: f01a9acb3a566be40d65fb075c8487d4e9cb6e73
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623643"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a>如何：检测鼠标指针何时在 ToolStripItem 上
使用以下过程来检测鼠标指针位于时<xref:System.Windows.Forms.ToolStripItem>。  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a>若要检测鼠标指针何时悬停在 toolstripitem 之上  
  
- 使用<xref:System.Windows.Forms.ToolStripItem.Selected%2A>属性中的项<xref:System.Windows.Forms.ToolStripItem.CanSelect%2A>是`true`。  
  
     这将阻止你无需同步<xref:System.Windows.Forms.ToolStripItem.MouseEnter>和<xref:System.Windows.Forms.ToolStripItem.MouseLeave>事件。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
