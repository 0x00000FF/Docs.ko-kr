---
title: '방법: 단일 B를 그리는&#233;zier 스플라인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: 32fc09c7525b40daea8c8705c43100cea0c052bc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676460"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="82646-102">방법: 단일 B를 그리는&#233;zier 스플라인</span><span class="sxs-lookup"><span data-stu-id="82646-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="82646-103">베 지 어 스플라인을 4 개의 점으로 정의: 시작점, 두 개의 제어점 및 끝점.</span><span class="sxs-lookup"><span data-stu-id="82646-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82646-104">예제</span><span class="sxs-lookup"><span data-stu-id="82646-104">Example</span></span>  
 <span data-ttu-id="82646-105">다음 예제에서는 (10, 100) 시작점 및 끝점 (200, 100)를 사용 하 여 베 지 어 스플라인을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="82646-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="82646-106">컨트롤은 (100, 10) 및 (150, 150)을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="82646-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="82646-107">다음 그림에서는 결과 베 지 어 스플라인을와 해당 시작 지점, 제어점, 끝점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="82646-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="82646-108">그림에는 또한 직선을 사용 하 여 4 개의 점을 연결 하 여 형성 된 다각형 스플라인의 볼록 다각형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="82646-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 <span data-ttu-id="82646-109">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span><span class="sxs-lookup"><span data-stu-id="82646-109">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="82646-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="82646-110">Compiling the Code</span></span>  
 <span data-ttu-id="82646-111">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="82646-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82646-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="82646-112">See also</span></span>
- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [<span data-ttu-id="82646-113">GDI+의 3차원 곡선 스플라인</span><span class="sxs-lookup"><span data-stu-id="82646-113">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)
- [<span data-ttu-id="82646-114">방법: 일련의 3 차원 곡선 스플라인 그리기</span><span class="sxs-lookup"><span data-stu-id="82646-114">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
