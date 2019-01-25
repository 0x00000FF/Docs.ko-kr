---
title: '방법: 펜 색 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: d0402a7d6bb641ef6d97eb41bc25f3c59b3b4250
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569442"
---
# <a name="how-to-set-the-color-of-a-pen"></a><span data-ttu-id="bca3f-102">방법: 펜 색 설정</span><span class="sxs-lookup"><span data-stu-id="bca3f-102">How to: Set the Color of a Pen</span></span>
<span data-ttu-id="bca3f-103">이 예제에서는 기존 색이 달라 <xref:System.Drawing.Pen> 개체</span><span class="sxs-lookup"><span data-stu-id="bca3f-103">This example changes the color of a pre-existing <xref:System.Drawing.Pen> object</span></span>  
  
## <a name="example"></a><span data-ttu-id="bca3f-104">예제</span><span class="sxs-lookup"><span data-stu-id="bca3f-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bca3f-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="bca3f-105">Compiling the Code</span></span>  
 <span data-ttu-id="bca3f-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bca3f-106">This example requires:</span></span>  
  
-   <span data-ttu-id="bca3f-107">A <xref:System.Drawing.Pen> 개체인 `myPen`합니다.</span><span class="sxs-lookup"><span data-stu-id="bca3f-107">A <xref:System.Drawing.Pen> object named `myPen`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="bca3f-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="bca3f-108">Robust Programming</span></span>  
 <span data-ttu-id="bca3f-109">호출 해야 <xref:System.Drawing.Pen.Dispose%2A> 시스템 리소스를 사용 하는 개체에 (같은 <xref:System.Drawing.Pen> 개체)을 사용 하 여 작업을 마친 후 합니다.</span><span class="sxs-lookup"><span data-stu-id="bca3f-109">You should call <xref:System.Drawing.Pen.Dispose%2A> on objects that consume system resources (such as <xref:System.Drawing.Pen> objects) after you are finished using them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bca3f-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="bca3f-110">See also</span></span>
- <xref:System.Drawing.Pen>
- [<span data-ttu-id="bca3f-111">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="bca3f-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [<span data-ttu-id="bca3f-112">방법: 펜 만들기</span><span class="sxs-lookup"><span data-stu-id="bca3f-112">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
- [<span data-ttu-id="bca3f-113">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="bca3f-113">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="bca3f-114">GDI+의 펜, 선 및 사각형</span><span class="sxs-lookup"><span data-stu-id="bca3f-114">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
