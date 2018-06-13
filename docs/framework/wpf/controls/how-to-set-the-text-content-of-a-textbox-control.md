---
title: '방법: TextBox 컨트롤의 텍스트 내용 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: 37d636a5e35e9c52ca35ae558b60b5f32d63cabe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551728"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="86449-102">방법: TextBox 컨트롤의 텍스트 내용 설정</span><span class="sxs-lookup"><span data-stu-id="86449-102">How to: Set the Text Content of a TextBox Control</span></span>
<span data-ttu-id="86449-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.TextBox.Text%2A> 속성의 초기 텍스트 콘텐츠를 설정 하는 <xref:System.Windows.Controls.TextBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="86449-103">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 <span data-ttu-id="86449-104">**참고** 있지만 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제의 버전에서 사용할 수는 `<TextBox.Text>` 각 단추의 텍스트 태그 <xref:System.Windows.Controls.TextBox> 콘텐츠, 필요 하지 않습니다 때문에 <xref:System.Windows.Controls.TextBox> 적용 되는 <xref:System.Windows.Markup.ContentPropertyAttribute> 특성을 <xref:System.Windows.Controls.TextBox.Text%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="86449-104">**Note** Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="86449-105">자세한 내용은 참조 [XAML 개요 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="86449-105">For more information, see [XAML Overview (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="86449-106">예제</span><span class="sxs-lookup"><span data-stu-id="86449-106">Example</span></span>  
 [!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]  
  
## <a name="example"></a><span data-ttu-id="86449-107">예제</span><span class="sxs-lookup"><span data-stu-id="86449-107">Example</span></span>  
 [!code-csharp[TextBox_MiscCode#_TextBoxSetText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
 [!code-vb[TextBox_MiscCode#_TextBoxSetText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]  
  
## <a name="see-also"></a><span data-ttu-id="86449-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86449-108">See Also</span></span>  
 [<span data-ttu-id="86449-109">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="86449-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="86449-110">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="86449-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
