---
title: "방법: TextBox 컨트롤을 읽기 전용으로 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 36116346b389dac7e9783e69d9bcd79573b4bf75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-a-textbox-control-read-only"></a><span data-ttu-id="b867e-102">방법: TextBox 컨트롤을 읽기 전용으로 설정</span><span class="sxs-lookup"><span data-stu-id="b867e-102">How to: Make a TextBox Control Read-Only</span></span>
<span data-ttu-id="b867e-103">구성 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.TextBox> 컨트롤을 사용자 입력 또는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b867e-103">This example shows how to configure a <xref:System.Windows.Controls.TextBox> control to not allow user input or modification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b867e-104">예제</span><span class="sxs-lookup"><span data-stu-id="b867e-104">Example</span></span>  
 <span data-ttu-id="b867e-105">내용을 수정 하지 못하게 하려면는 <xref:System.Windows.Controls.TextBox> 제어, 설정 된 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> 특성을 **true**합니다.</span><span class="sxs-lookup"><span data-stu-id="b867e-105">To prevent users from modifying the contents of a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <span data-ttu-id="b867e-106"><xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> 특성에 사용자 입력에만 영향을 줍니다;에 설정 된 텍스트에는 영향을 주지 않습니다는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 설명은 <xref:System.Windows.Controls.TextBox> 컨트롤 또는 통해 프로그래밍 방식으로 설정 된 텍스트는 <xref:System.Windows.Controls.TextBox.Text%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b867e-106">The <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute affects user input only; it does not affect text set in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] description of a <xref:System.Windows.Controls.TextBox> control, or text set programmatically through the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="b867e-107">기본값 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> 은 **false**합니다.</span><span class="sxs-lookup"><span data-stu-id="b867e-107">The default value of <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> is **false**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b867e-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b867e-108">See Also</span></span>  
 [<span data-ttu-id="b867e-109">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="b867e-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="b867e-110">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="b867e-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
