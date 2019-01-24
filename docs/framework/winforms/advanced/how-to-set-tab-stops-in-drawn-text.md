---
title: '방법: 그린된 텍스트에 탭 정지 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: 4bf9328b63be88f487995f7b9691683167271c46
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635808"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a><span data-ttu-id="4aee3-102">방법: 그린된 텍스트에 탭 정지 설정</span><span class="sxs-lookup"><span data-stu-id="4aee3-102">How to: Set Tab Stops in Drawn Text</span></span>
<span data-ttu-id="4aee3-103">호출 하 여 텍스트에 대 한 탭 정지를 설정할 수 있습니다는 <xref:System.Drawing.StringFormat.SetTabStops%2A> 메서드를 <xref:System.Drawing.StringFormat> 개체와 전달 하는 <xref:System.Drawing.StringFormat> 개체를 <xref:System.Drawing.Graphics.DrawString%2A> 메서드를 <xref:System.Drawing.Graphics> 클래스.</span><span class="sxs-lookup"><span data-stu-id="4aee3-103">You can set tab stops for text by calling the <xref:System.Drawing.StringFormat.SetTabStops%2A> method of a <xref:System.Drawing.StringFormat> object and then passing that <xref:System.Drawing.StringFormat> object to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4aee3-104">합니다 <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> 사용을 중지할 기존 탭을 확장할 수 있지만 그린된 텍스트에 탭 정지를 추가 하는 지원 하지 않습니다는 <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="4aee3-104">The <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> does not support adding tab stops to drawn text, although you can expand existing tab stops using the <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4aee3-105">예제</span><span class="sxs-lookup"><span data-stu-id="4aee3-105">Example</span></span>  
 <span data-ttu-id="4aee3-106">다음 예제에서는 150, 250 및 350에 탭 정지를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4aee3-106">The following example sets tab stops at 150, 250, and 350.</span></span> <span data-ttu-id="4aee3-107">그런 다음 코드에는 이름 및 시험 점수의 탭된 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4aee3-107">Then, the code displays a tabbed list of names and test scores.</span></span>  
  
 <span data-ttu-id="4aee3-108">다음 그림에서는 탭된 텍스트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4aee3-108">The following illustration shows the tabbed text.</span></span>  
  
 <span data-ttu-id="4aee3-109">![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")</span><span class="sxs-lookup"><span data-stu-id="4aee3-109">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")</span></span>  
  
 <span data-ttu-id="4aee3-110">다음 코드는 두 개의 인수를 전달 합니다 <xref:System.Drawing.StringFormat.SetTabStops%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="4aee3-110">The following code passes two arguments to the <xref:System.Drawing.StringFormat.SetTabStops%2A> method.</span></span> <span data-ttu-id="4aee3-111">두 번째 인수는 탭 오프셋을 포함 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="4aee3-111">The second argument is an array that contains tab offsets.</span></span> <span data-ttu-id="4aee3-112">첫 번째 인수를 전달할 <xref:System.Drawing.StringFormat.SetTabStops%2A> 은 0, 0, 경계 사각형의 왼쪽된 가장자리의 위치에서 배열의 첫 번째 오프셋을 측정 하는 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4aee3-112">The first argument passed to <xref:System.Drawing.StringFormat.SetTabStops%2A> is 0, which indicates that the first offset in the array is measured from position 0, the left edge of the bounding rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4aee3-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="4aee3-113">Compiling the Code</span></span>  
  
-   <span data-ttu-id="4aee3-114">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4aee3-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aee3-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="4aee3-115">See also</span></span>
- [<span data-ttu-id="4aee3-116">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="4aee3-116">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
- [<span data-ttu-id="4aee3-117">방법: GDI 사용 하 여 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="4aee3-117">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
