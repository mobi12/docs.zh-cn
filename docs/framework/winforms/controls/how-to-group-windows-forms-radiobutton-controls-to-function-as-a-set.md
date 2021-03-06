---
title: "如何：按功能分组 Windows 窗体 RadioButton 控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 37d8571624272f62c6ce327b0ed25e082c5cf713
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>如何：按功能分组 Windows 窗体 RadioButton 控件
Windows 窗体<xref:System.Windows.Forms.RadioButton>控制机制旨在让用户在两个或多个设置，其中只有一个可以分配给过程或对象之间进行选择。 例如，一组<xref:System.Windows.Forms.RadioButton>控件可能会显示一个选择的包的订单的承运人，但会使用承运人之一。 因此只有一个<xref:System.Windows.Forms.RadioButton>一次可以选择，即使它是功能组的一部分。  
  
 单选按钮分组通过如容器内绘制它们<xref:System.Windows.Forms.Panel>控件，<xref:System.Windows.Forms.GroupBox>控件或窗体。 直接添加到窗体成为一个组的所有单选按钮。 若要添加单独的组，必须将它们放在面板或分组框中。 有关面板或分组框的详细信息，请参阅[Panel 控件概述](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)或[GroupBox 控件概述](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)。  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>与组单选按钮控件作为一个设置为独立于其他集函数  
  
1.  拖动<xref:System.Windows.Forms.GroupBox>或<xref:System.Windows.Forms.Panel>控件从**Windows 窗体**选项卡上**工具箱**拖到窗体。  
  
2.  绘制<xref:System.Windows.Forms.RadioButton>上的控件<xref:System.Windows.Forms.GroupBox>或<xref:System.Windows.Forms.Panel>控件。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.RadioButton>  
 [RadioButton 控件概述](../../../../docs/framework/winforms/controls/radiobutton-control-overview-windows-forms.md)  
 [Panel 控件概述](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [GroupBox 控件概述](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)  
 [CheckBox 控件概述](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [RadioButton 控件](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)
