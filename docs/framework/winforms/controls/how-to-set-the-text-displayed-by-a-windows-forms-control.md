---
title: "如何：设置 Windows 窗体控件所显示的文本"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a81c2202400968b4d4c95b40de7476fbd68d6182
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a>如何：设置 Windows 窗体控件所显示的文本
Windows 窗体控件通常会显示一些与控件的主要功能相关的文本。 例如，<xref:System.Windows.Forms.Button> 控件通常会显示一个题注，用于指示单击按钮时将执行的操作。 对于所有控件而言，都可通过使用 <xref:System.Windows.Forms.Control.Text%2A> 属性来设置或返回文本。 可以使用 <xref:System.Windows.Forms.Control.Font%2A> 属性更改字体。 还可使用设计器来设置文本。  另请参阅[如何： 创建访问键的 Windows 窗体控件使用设计器](http://msdn.microsoft.com/library/ms233673\(v=vs.110\))，[如何： 设置 Windows 窗体控件使用文本显示设计器](http://msdn.microsoft.com/library/ms233665\(v=vs.110\))，[如何： 设置图像通过显示 Windows 窗体控件使用设计器](http://msdn.microsoft.com/library/ms233656\(v=vs.110\))。  
  
### <a name="to-set-the-text-displayed-by-a-control-programmatically"></a>以编程方式设置控件所显示的文本  
  
1.  将 <xref:System.Windows.Forms.Control.Text%2A> 属性设置为字符串。  
  
     若要创建一个带下划线的访问键，请使将成为访问键的字母前包含一个 & 号 (&)。  
  
2.  将 <xref:System.Windows.Forms.Control.Font%2A> 属性设置为类型 <xref:System.Drawing.Font> 的对象。  
  
    ```vb  
    Button1.Text = "Click here to save changes"  
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)  
    ```  
  
    ```csharp  
    button1.Text = "Click here to save changes";  
    button1.Font = new Font("Arial", 10, FontStyle.Bold,  
       GraphicsUnit.Point);  
    ```  
  
    ```cpp  
    button1->Text = "Click here to save changes";  
    button1->Font = new System::Drawing::Font("Arial",  
       10, FontStyle::Bold, GraphicsUnit::Point);  
    ```  
  
    > [!NOTE]
    >  可使用转义符来显示用户界面元素中的特殊字符，通常对这些元素（如菜单项）有着不同的解释。 例如，下面的代码行将菜单项的文本设置为“现读取完全不同的内容”：  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
    ```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>  
 [如何：创建 Windows 窗体控件的访问键](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [如何：响应 Windows 窗体 Button 控件单击](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
