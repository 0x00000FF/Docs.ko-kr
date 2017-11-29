---
title: "GDI+의 영역"
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
helpviewer_keywords:
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0525e7b58353909d41e5367aa52a17aa56bcd77c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="regions-in-gdi"></a><span data-ttu-id="449ca-102">GDI+의 영역</span><span class="sxs-lookup"><span data-stu-id="449ca-102">Regions in GDI+</span></span>
<span data-ttu-id="449ca-103">영역에는 출력 장치의 표시 영역의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-103">A region is a portion of the display area of an output device.</span></span> <span data-ttu-id="449ca-104">영역 (단일 사각형) 단순 또는 복합 (다각형 및 폐곡선 조합) 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-104">Regions can be simple (a single rectangle) or complex (a combination of polygons and closed curves).</span></span> <span data-ttu-id="449ca-105">다음 그림에는 두 개의 영역을 보여 줍니다: 하나는 사각형에서 구현 되 고 다른 경로에서 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-105">The following illustration shows two regions: one constructed from a rectangle, and the other constructed from a path.</span></span>  
  
 <span data-ttu-id="449ca-106">![영역](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span><span class="sxs-lookup"><span data-stu-id="449ca-106">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span></span>  
  
## <a name="using-regions"></a><span data-ttu-id="449ca-107">영역 사용</span><span class="sxs-lookup"><span data-stu-id="449ca-107">Using Regions</span></span>  
 <span data-ttu-id="449ca-108">영역은 자주 클리핑에 사용 및 적중 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-108">Regions are often used for clipping and hit testing.</span></span> <span data-ttu-id="449ca-109">클리핑은 그리기의 표시 영역을 업데이트 해야 하는 부분 일반적으로 특정 영역으로 제한 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-109">Clipping involves restricting drawing to a certain region of the display area, usually the portion that needs to be updated.</span></span> <span data-ttu-id="449ca-110">적중 테스트는 마우스 단추를 누를 때 커서 화면의 특정 영역에 인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-110">Hit testing involves checking to determine whether the cursor is in a certain region of the screen when a mouse button is pressed.</span></span>  
  
 <span data-ttu-id="449ca-111">사각형 또는 경로에서 영역을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-111">You can construct a region from a rectangle or a path.</span></span> <span data-ttu-id="449ca-112">기존 영역을 결합 하 여 복잡 한 영역을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-112">You can also create complex regions by combining existing regions.</span></span> <span data-ttu-id="449ca-113"><xref:System.Drawing.Region> 영역을 결합 하기 위한 다음 메서드를 제공 하는 클래스: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, 및 <xref:System.Drawing.Region.Complement%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-113">The <xref:System.Drawing.Region> class provides the following methods for combining regions: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, and <xref:System.Drawing.Region.Complement%2A>.</span></span>  
  
 <span data-ttu-id="449ca-114">두 지역의 교집합 영역 모두에 속하는 모든 데이터 요소 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-114">The intersection of two regions is the set of all points belonging to both regions.</span></span> <span data-ttu-id="449ca-115">Union은 하나 또는 다른 또는 두 지역에 속한 모든 데이터 요소 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-115">The union is the set of all points belonging to one or the other or both regions.</span></span> <span data-ttu-id="449ca-116">영역의 보수는 지역에 있지 않은 모든 데이터 요소 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-116">The complement of a region is the set of all points that are not in the region.</span></span> <span data-ttu-id="449ca-117">다음 그림에서는 교차와 앞의 그림에 표시 된 두 개의 영역의 합집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-117">The following illustration shows the intersection and union of the two regions shown in the preceding illustration.</span></span>  
  
 <span data-ttu-id="449ca-118">![영역](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span><span class="sxs-lookup"><span data-stu-id="449ca-118">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span></span>  
  
 <span data-ttu-id="449ca-119"><xref:System.Drawing.Region.Xor%2A> 메서드를 쌍의 영역에 적용 한 지역 또는 서로 다르다는 것에 속해 있는 모든 점을 포함 하는 영역을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-119">The <xref:System.Drawing.Region.Xor%2A> method, applied to a pair of regions, produces a region that contains all points that belong to one region or the other, but not both.</span></span> <span data-ttu-id="449ca-120"><xref:System.Drawing.Region.Exclude%2A> 메서드를 쌍의 영역에 적용 된 첫 번째 지역에 두 번째 지역에 있지 않은 모든 점을 포함 하는 영역을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-120">The <xref:System.Drawing.Region.Exclude%2A> method, applied to a pair of regions, produces a region that contains all points in the first region that are not in the second region.</span></span> <span data-ttu-id="449ca-121">다음 그림에는 적용 지역이 표시는 <xref:System.Drawing.Region.Xor%2A> 및 <xref:System.Drawing.Region.Exclude%2A> 메서드를이 항목의 시작 부분에 표시 된 두 개의 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-121">The following illustration shows the regions that result from applying the <xref:System.Drawing.Region.Xor%2A> and <xref:System.Drawing.Region.Exclude%2A> methods to the two regions shown at the beginning of this topic.</span></span>  
  
 <span data-ttu-id="449ca-122">![영역](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span><span class="sxs-lookup"><span data-stu-id="449ca-122">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span></span>  
  
 <span data-ttu-id="449ca-123">영역을 채울 필요는 <xref:System.Drawing.Graphics> 개체는 <xref:System.Drawing.Brush> 개체 및 <xref:System.Drawing.Region> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-123">To fill a region, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Brush> object, and a <xref:System.Drawing.Region> object.</span></span> <span data-ttu-id="449ca-124"><xref:System.Drawing.Graphics> 개체 제공는 <xref:System.Drawing.Graphics.FillRegion%2A> 메서드, 및 <xref:System.Drawing.Brush> 개체 특성 채우기 색 또는 패턴을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-124">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.FillRegion%2A> method, and the <xref:System.Drawing.Brush> object stores attributes of the fill, such as color or pattern.</span></span> <span data-ttu-id="449ca-125">다음 예제를 단색으로 영역을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="449ca-125">The following example fills a region with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="449ca-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="449ca-126">See Also</span></span>  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [<span data-ttu-id="449ca-127">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="449ca-127">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="449ca-128">영역 사용</span><span class="sxs-lookup"><span data-stu-id="449ca-128">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)
