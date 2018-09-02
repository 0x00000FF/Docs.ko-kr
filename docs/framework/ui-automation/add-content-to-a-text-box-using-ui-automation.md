---
title: UI 자동화를 사용하여 텍스트 상자에 콘텐츠 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: aff0e8c6831e44185f1cb77507febf8ccbc86e99
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43418883"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="a0191-102">UI 자동화를 사용하여 텍스트 상자에 콘텐츠 추가</span><span class="sxs-lookup"><span data-stu-id="a0191-102">Add Content to a Text Box Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="a0191-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a0191-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a0191-104">에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]를 참조 하세요 [Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746)합니다.</span><span class="sxs-lookup"><span data-stu-id="a0191-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="a0191-105">이 항목에 사용 하는 방법을 보여 주는 예제 코드가 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 한 줄 텍스트 상자에 텍스트를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0191-105">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="a0191-106">여러 줄 및 서식 있는 텍스트 컨트롤에 대 한 대체 방법을 제공 됩니다 여기서 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0191-106">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="a0191-107">비교를 위해이 예제에서는 동일한 결과 위해 Win32 메서드를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0191-107">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0191-108">예제</span><span class="sxs-lookup"><span data-stu-id="a0191-108">Example</span></span>  
 <span data-ttu-id="a0191-109">대상 응용 프로그램에서 텍스트 컨트롤의 시퀀스에서 다음 예제.</span><span class="sxs-lookup"><span data-stu-id="a0191-109">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="a0191-110">각 텍스트 컨트롤을 하는지 테스트를 <xref:System.Windows.Automation.ValuePattern> 를 사용 하 여 개체를 얻을 수를 <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="a0191-110">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="a0191-111">텍스트 컨트롤에서 지원 <xref:System.Windows.Automation.ValuePattern>, <xref:System.Windows.Automation.ValuePattern.SetValue%2A> 메서드 사용 하 여 텍스트 컨트롤에 사용자 정의 문자열을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0191-111">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="a0191-112">그렇지 않은 경우는 <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0191-112">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="a0191-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0191-113">See Also</span></span>  
 [<span data-ttu-id="a0191-114">TextPattern Insert 텍스트 샘플</span><span class="sxs-lookup"><span data-stu-id="a0191-114">TextPattern Insert Text Sample</span></span>](https://msdn.microsoft.com/library/67353f93-7ee2-42f2-ab76-5c078cf6ca16)
