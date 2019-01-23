---
title: '방법: 그린된 텍스트 맞추기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
ms.openlocfilehash: 1cd6566e5eb5b60128206458c6e82b8eecf5492e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632376"
---
# <a name="how-to-align-drawn-text"></a><span data-ttu-id="593b9-102">방법: 그린된 텍스트 맞추기</span><span class="sxs-lookup"><span data-stu-id="593b9-102">How to: Align Drawn Text</span></span>
<span data-ttu-id="593b9-103">사용자 지정 그리기를 수행 하면 폼 이나 컨트롤에서 그린된 텍스트를 가운데 하려는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="593b9-103">When you perform custom drawing, you may often want to center drawn text on a form or control.</span></span> <span data-ttu-id="593b9-104">사용 하 여 그린 텍스트를 쉽게 맞출 수 있습니다 합니다 <xref:System.Drawing.Graphics.DrawString%2A> 또는 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 올바른 서식 지정 개체를 만들고 적절 한 형식 플래그를 설정 하 여 메서드.</span><span class="sxs-lookup"><span data-stu-id="593b9-104">You can easily align text drawn with the <xref:System.Drawing.Graphics.DrawString%2A> or <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods by creating the correct formatting object and setting the appropriate format flags.</span></span>  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a><span data-ttu-id="593b9-105">그릴 GDI + (DrawString)를 사용 하 여 텍스트를 가운데</span><span class="sxs-lookup"><span data-stu-id="593b9-105">To draw centered text with GDI+ (DrawString)</span></span>  
  
1.  <span data-ttu-id="593b9-106">사용 된 <xref:System.Drawing.StringFormat> 적절 한 <xref:System.Drawing.Graphics.DrawString%2A> 가운데 맞춤 된 텍스트를 지정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="593b9-106">Use a <xref:System.Drawing.StringFormat> with the appropriate <xref:System.Drawing.Graphics.DrawString%2A> method to specify centered text.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a><span data-ttu-id="593b9-107">그릴 GDI (DrawText)를 사용 하 여 텍스트를 가운데</span><span class="sxs-lookup"><span data-stu-id="593b9-107">To draw centered text with GDI (DrawText)</span></span>  
  
1.  <span data-ttu-id="593b9-108">사용 된 <xref:System.Windows.Forms.TextFormatFlags> 래핑 수 있을 뿐만 아니라 적절 한 텍스트를 가로 및 세로로 가운데 맞춤에 대 한 열거형 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="593b9-108">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration for wrapping as well as vertically and horizontally centering text with the appropriate <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="593b9-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="593b9-109">Compiling the Code</span></span>  
 <span data-ttu-id="593b9-110">앞의 코드 예제 Windows Forms에서 사용 하도록 설계 되었으며 필요할 <xref:System.Windows.Forms.PaintEventArgs> `e`의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="593b9-110">The preceding code examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="593b9-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="593b9-111">See also</span></span>
- [<span data-ttu-id="593b9-112">방법: GDI 사용 하 여 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="593b9-112">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="593b9-113">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="593b9-113">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
- [<span data-ttu-id="593b9-114">방법: 글꼴 패밀리 및 글꼴 만들기</span><span class="sxs-lookup"><span data-stu-id="593b9-114">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)
