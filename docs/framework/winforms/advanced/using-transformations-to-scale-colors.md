---
title: "변형을 사용하여 색의 비율 조정"
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
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7515f34858ef6f4b0495ac6fc545ae498d45c7f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="using-transformations-to-scale-colors"></a><span data-ttu-id="46ee4-102">변형을 사용하여 색의 비율 조정</span><span class="sxs-lookup"><span data-stu-id="46ee4-102">Using Transformations to Scale Colors</span></span>
<span data-ttu-id="46ee4-103">크기 조정 변환을 숫자는 네 가지 구성 요소 중 하나 이상을 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="46ee4-103">A scaling transformation multiplies one or more of the four color components by a number.</span></span> <span data-ttu-id="46ee4-104">다음 테이블에 확장을 나타내는 색 매트릭스 항목이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46ee4-104">The color matrix entries that represent scaling are given in the following table.</span></span>  
  
|<span data-ttu-id="46ee4-105">구성 요소 크기를 조정할 수</span><span class="sxs-lookup"><span data-stu-id="46ee4-105">Component to be scaled</span></span>|<span data-ttu-id="46ee4-106">행렬 항목</span><span class="sxs-lookup"><span data-stu-id="46ee4-106">Matrix entry</span></span>|  
|----------------------------|------------------|  
|<span data-ttu-id="46ee4-107">빨강</span><span class="sxs-lookup"><span data-stu-id="46ee4-107">Red</span></span>|<span data-ttu-id="46ee4-108">[0][0]</span><span class="sxs-lookup"><span data-stu-id="46ee4-108">[0][0]</span></span>|  
|<span data-ttu-id="46ee4-109">녹색</span><span class="sxs-lookup"><span data-stu-id="46ee4-109">Green</span></span>|<span data-ttu-id="46ee4-110">[1][1]</span><span class="sxs-lookup"><span data-stu-id="46ee4-110">[1][1]</span></span>|  
|<span data-ttu-id="46ee4-111">파랑</span><span class="sxs-lookup"><span data-stu-id="46ee4-111">Blue</span></span>|<span data-ttu-id="46ee4-112">[2][2]</span><span class="sxs-lookup"><span data-stu-id="46ee4-112">[2][2]</span></span>|  
|<span data-ttu-id="46ee4-113">알파</span><span class="sxs-lookup"><span data-stu-id="46ee4-113">Alpha</span></span>|<span data-ttu-id="46ee4-114">[3][3]</span><span class="sxs-lookup"><span data-stu-id="46ee4-114">[3][3]</span></span>|  
  
## <a name="scaling-one-color"></a><span data-ttu-id="46ee4-115">한 가지 색을 크기 조정</span><span class="sxs-lookup"><span data-stu-id="46ee4-115">Scaling One Color</span></span>  
 <span data-ttu-id="46ee4-116">다음 구성 예제는 <xref:System.Drawing.Image> ColorBars2.bmp 파일에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="46ee4-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="46ee4-117">그런 다음 코드는 2 배 이미지에 각 픽셀의 파란색 구성 요소를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="46ee4-117">Then the code scales the blue component of each pixel in the image by a factor of 2.</span></span> <span data-ttu-id="46ee4-118">변환된 된 이미지와 함께 원본 이미지를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="46ee4-118">The original image is drawn alongside the transformed image.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 <span data-ttu-id="46ee4-119">다음 그림에서는 오른쪽에서 왼쪽의 원본 이미지와 조정 된 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46ee4-119">The following illustration shows the original image on the left and the scaled image on the right.</span></span>  
  
 <span data-ttu-id="46ee4-120">![색의 배율을 조정](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")</span><span class="sxs-lookup"><span data-stu-id="46ee4-120">![Scale Colors](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")</span></span>  
  
 <span data-ttu-id="46ee4-121">다음 표에서 앞과 뒤 파란색 크기 조정 막대 네 개에 대 한 색 벡터를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="46ee4-121">The following table lists the color vectors for the four bars before and after the blue scaling.</span></span> <span data-ttu-id="46ee4-122">네 번째 색 막대에 있는 파란색 구성 0.8 0.6을 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="46ee4-122">Note that the blue component in the fourth color bar went from 0.8 to 0.6.</span></span> <span data-ttu-id="46ee4-123">때문 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 결과의 소수 부분에만 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="46ee4-123">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] retains only the fractional part of the result.</span></span> <span data-ttu-id="46ee4-124">예를 들어 (2)(0.8) = 1.6은 0.6 1.6의 소수 부분 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="46ee4-124">For example, (2)(0.8) = 1.6, and the fractional part of 1.6 is 0.6.</span></span> <span data-ttu-id="46ee4-125">소수 부분이 그대로 유지 하 고 결과 항상 [0, 1] 간격을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="46ee4-125">Retaining only the fractional part ensures that the result is always in the interval [0, 1].</span></span>  
  
|<span data-ttu-id="46ee4-126">원래 색</span><span class="sxs-lookup"><span data-stu-id="46ee4-126">Original</span></span>|<span data-ttu-id="46ee4-127">배율 조정</span><span class="sxs-lookup"><span data-stu-id="46ee4-127">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="46ee4-128">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="46ee4-128">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="46ee4-129">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="46ee4-129">(0.4, 0.4, 0.8, 1)</span></span>|  
|<span data-ttu-id="46ee4-130">(0.4, 0.2, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="46ee4-130">(0.4, 0.2, 0.2, 1)</span></span>|<span data-ttu-id="46ee4-131">(0.4, 0.2, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="46ee4-131">(0.4, 0.2, 0.4, 1)</span></span>|  
|<span data-ttu-id="46ee4-132">(0.2, 0.4, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="46ee4-132">(0.2, 0.4, 0.2, 1)</span></span>|<span data-ttu-id="46ee4-133">(0.2, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="46ee4-133">(0.2, 0.4, 0.4, 1)</span></span>|  
|<span data-ttu-id="46ee4-134">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="46ee4-134">(0.4, 0.4, 0.8, 1)</span></span>|<span data-ttu-id="46ee4-135">(0.4, 0.4, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="46ee4-135">(0.4, 0.4, 0.6, 1)</span></span>|  
  
## <a name="scaling-multiple-colors"></a><span data-ttu-id="46ee4-136">여러 색 비율 조정</span><span class="sxs-lookup"><span data-stu-id="46ee4-136">Scaling Multiple Colors</span></span>  
 <span data-ttu-id="46ee4-137">다음 구성 예제는 <xref:System.Drawing.Image> ColorBars2.bmp 파일에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="46ee4-137">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="46ee4-138">그런 다음 코드는 이미지에 각 픽셀의 빨간색, 녹색 및 파랑 구성 요소를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="46ee4-138">Then the code scales the red, green, and blue components of each pixel in the image.</span></span> <span data-ttu-id="46ee4-139">빨간색 구성 요소는 25% 크기가 조정 되어, 녹색 구성 요소는 35% 크기가 조정 되어 및 파랑 구성 요소는 50%를 축소 합니다.</span><span class="sxs-lookup"><span data-stu-id="46ee4-139">The red components are scaled down 25 percent, the green components are scaled down 35 percent, and the blue components are scaled down 50 percent.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 <span data-ttu-id="46ee4-140">다음 그림에서는 오른쪽에서 왼쪽의 원본 이미지와 조정 된 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46ee4-140">The following illustration shows the original image on the left and the scaled image on the right.</span></span>  
  
 <span data-ttu-id="46ee4-141">![색의 배율을 조정](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")</span><span class="sxs-lookup"><span data-stu-id="46ee4-141">![Scale Colors](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")</span></span>  
  
 <span data-ttu-id="46ee4-142">다음 표에서 빨간색, 녹색 및 파란색 배율을 전후 막대 네 개에 대 한 색 벡터를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="46ee4-142">The following table lists the color vectors for the four bars before and after the red, green and blue scaling.</span></span>  
  
|<span data-ttu-id="46ee4-143">원래 색</span><span class="sxs-lookup"><span data-stu-id="46ee4-143">Original</span></span>|<span data-ttu-id="46ee4-144">배율 조정</span><span class="sxs-lookup"><span data-stu-id="46ee4-144">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="46ee4-145">(0.6, 0.6, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="46ee4-145">(0.6, 0.6, 0.6, 1)</span></span>|<span data-ttu-id="46ee4-146">(0.45, 0.39, 0.3, 1)</span><span class="sxs-lookup"><span data-stu-id="46ee4-146">(0.45, 0.39, 0.3, 1)</span></span>|  
|<span data-ttu-id="46ee4-147">(0, 1, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="46ee4-147">(0, 1, 1, 1)</span></span>|<span data-ttu-id="46ee4-148">(0, 0.65, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="46ee4-148">(0, 0.65, 0.5, 1)</span></span>|  
|<span data-ttu-id="46ee4-149">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="46ee4-149">(1, 1, 0, 1)</span></span>|<span data-ttu-id="46ee4-150">(0.75, 0.65, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="46ee4-150">(0.75, 0.65, 0, 1)</span></span>|  
|<span data-ttu-id="46ee4-151">(1, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="46ee4-151">(1, 0, 1, 1)</span></span>|<span data-ttu-id="46ee4-152">(0.75, 0, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="46ee4-152">(0.75, 0, 0.5, 1)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46ee4-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46ee4-153">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="46ee4-154">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="46ee4-154">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="46ee4-155">이미지 다시 칠하기</span><span class="sxs-lookup"><span data-stu-id="46ee4-155">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
