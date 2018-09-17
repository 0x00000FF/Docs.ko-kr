---
title: '방법: 폼의 클라이언트 영역 인쇄(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- client area [Visual Basic], printing
ms.assetid: c06c9c0e-bc07-48cd-9596-e29a2ff96236
ms.openlocfilehash: b2f13d1ec151a5fd1967b522a601e0e19de04cbb
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2018
ms.locfileid: "45689225"
---
# <a name="how-to-print-the-client-area-of-a-form-visual-basic"></a><span data-ttu-id="cff5e-102">방법: 폼의 클라이언트 영역 인쇄(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cff5e-102">How to: Print the Client Area of a Form (Visual Basic)</span></span>
<span data-ttu-id="cff5e-103"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소를 사용하면 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 사용하지 않고 폼 이미지를 빠르게 인쇄할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cff5e-103">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component enables you to quickly print an image of a form without using a <xref:System.Drawing.Printing.PrintDocument> component.</span></span> <span data-ttu-id="cff5e-104">다음 절차에서는 제목 표시줄, 테두리 및 스크롤 막대 없이 폼의 클라이언트 영역만 인쇄하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cff5e-104">The following procedure shows how to print just the client area of a form, without the title bar, borders, and scroll bars.</span></span>  
  
 <span data-ttu-id="cff5e-105">PowerPack 컨트롤은 더 이상 Visual Studio에 포함 되었지만 이러한에서 다운로드할 수 없습니다 합니다 [다운로드 센터](https://www.microsoft.com/en-us/download/details.aspx?id=25169)합니다.</span><span class="sxs-lookup"><span data-stu-id="cff5e-105">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
### <a name="to-print-the-client-area-of-a-form"></a><span data-ttu-id="cff5e-106">폼의 클라이언트 영역을 인쇄하려면</span><span class="sxs-lookup"><span data-stu-id="cff5e-106">To print the client area of a form</span></span>  
  
1.  <span data-ttu-id="cff5e-107">**도구 상자**에서 **Visual Basic PowerPacks** 탭을 클릭하고 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소를 폼으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="cff5e-107">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="cff5e-108"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소가 구성 요소 트레이에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="cff5e-108">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="cff5e-109">**속성** 창에서 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> 속성을 <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cff5e-109">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span></span>  
  
3.  <span data-ttu-id="cff5e-110">`Click` 인쇄 **용**`Button`이벤트 처리기와 같은 적절한 이벤트 처리기에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cff5e-110">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.ClientAreaOnly)  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="cff5e-111">일부 운영 체제에서는 <xref:System.Drawing.Graphics> 메서드로 그려진 텍스트나 그래픽이 제대로 인쇄되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cff5e-111">On some operating systems, text or graphics drawn by <xref:System.Drawing.Graphics> methods may not print correctly.</span></span> <span data-ttu-id="cff5e-112">이 경우 호환되는 인쇄 메서드를 사용합니다. `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption CompatibleModeClientAreaOnly).`</span><span class="sxs-lookup"><span data-stu-id="cff5e-112">In this case, use the compatible printing method: `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption CompatibleModeClientAreaOnly).`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cff5e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cff5e-113">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 [<span data-ttu-id="cff5e-114">PrintForm 구성 요소</span><span class="sxs-lookup"><span data-stu-id="cff5e-114">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)  
 [<span data-ttu-id="cff5e-115">방법: 폼의 클라이언트 영역 및 비클라이언트 영역 인쇄</span><span class="sxs-lookup"><span data-stu-id="cff5e-115">How to: Print Client and Non-Client Areas of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)  
 [<span data-ttu-id="cff5e-116">방법: 스크롤 가능 폼 인쇄</span><span class="sxs-lookup"><span data-stu-id="cff5e-116">How to: Print a Scrollable Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
