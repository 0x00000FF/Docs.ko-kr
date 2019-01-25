---
title: '방법: 이미지 색 변환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: 7a3ed1f3f6b3e89c8df160b7e753839e20acd877
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549761"
---
# <a name="how-to-translate-image-colors"></a><span data-ttu-id="29269-102">방법: 이미지 색 변환</span><span class="sxs-lookup"><span data-stu-id="29269-102">How to: Translate Image Colors</span></span>
<span data-ttu-id="29269-103">번역 네 가지 구성 요소 중 하나 이상에 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="29269-103">A translation adds a value to one or more of the four color components.</span></span> <span data-ttu-id="29269-104">번역을 나타내는 색 매트릭스 항목은 다음 표에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29269-104">The color matrix entries that represent translations are given in the following table.</span></span>  
  
|<span data-ttu-id="29269-105">변환 구성 요소</span><span class="sxs-lookup"><span data-stu-id="29269-105">Component to be translated</span></span>|<span data-ttu-id="29269-106">행렬 항목</span><span class="sxs-lookup"><span data-stu-id="29269-106">Matrix entry</span></span>|  
|--------------------------------|------------------|  
|<span data-ttu-id="29269-107">빨강</span><span class="sxs-lookup"><span data-stu-id="29269-107">Red</span></span>|<span data-ttu-id="29269-108">[4][0]</span><span class="sxs-lookup"><span data-stu-id="29269-108">[4][0]</span></span>|  
|<span data-ttu-id="29269-109">녹색</span><span class="sxs-lookup"><span data-stu-id="29269-109">Green</span></span>|<span data-ttu-id="29269-110">[4][1]</span><span class="sxs-lookup"><span data-stu-id="29269-110">[4][1]</span></span>|  
|<span data-ttu-id="29269-111">파랑</span><span class="sxs-lookup"><span data-stu-id="29269-111">Blue</span></span>|<span data-ttu-id="29269-112">[4][2]</span><span class="sxs-lookup"><span data-stu-id="29269-112">[4][2]</span></span>|  
|<span data-ttu-id="29269-113">알파</span><span class="sxs-lookup"><span data-stu-id="29269-113">Alpha</span></span>|<span data-ttu-id="29269-114">[4][3]</span><span class="sxs-lookup"><span data-stu-id="29269-114">[4][3]</span></span>|  
  
## <a name="example"></a><span data-ttu-id="29269-115">예제</span><span class="sxs-lookup"><span data-stu-id="29269-115">Example</span></span>  
 <span data-ttu-id="29269-116">다음 예제에서는 생성 된 <xref:System.Drawing.Image> ColorBars.bmp 파일에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="29269-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars.bmp.</span></span> <span data-ttu-id="29269-117">다음 코드는 이미지의 각 픽셀의 빨강 구성 요소를 0.75를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="29269-117">Then the code adds 0.75 to the red component of each pixel in the image.</span></span> <span data-ttu-id="29269-118">변환 된 이미지와 함께 원본 이미지를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="29269-118">The original image is drawn alongside the transformed image.</span></span>  
  
 <span data-ttu-id="29269-119">다음 그림에서는 오른쪽에서 왼쪽의 원래 이미지와 변환 된 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="29269-119">The following illustration shows the original image on the left and the transformed image on the right.</span></span>  
  
 <span data-ttu-id="29269-120">![색 변환](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")</span><span class="sxs-lookup"><span data-stu-id="29269-120">![Translate Colors](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")</span></span>  
  
 <span data-ttu-id="29269-121">다음 표에서 빨간색 번역 전후 4 개 막대에 대 한 색 벡터를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="29269-121">The following table lists the color vectors for the four bars before and after the red translation.</span></span> <span data-ttu-id="29269-122">Note 색 구성 요소에 대 한 최대값은 1 이므로 두 번째 행의 빨강 구성 요소 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29269-122">Note that because the maximum value for a color component is 1, the red component in the second row does not change.</span></span> <span data-ttu-id="29269-123">(마찬가지로 색 구성 요소에 대 한 최소값은 0입니다.)</span><span class="sxs-lookup"><span data-stu-id="29269-123">(Similarly, the minimum value for a color component is 0.)</span></span>  
  
|<span data-ttu-id="29269-124">원래 색</span><span class="sxs-lookup"><span data-stu-id="29269-124">Original</span></span>|<span data-ttu-id="29269-125">번역 언어</span><span class="sxs-lookup"><span data-stu-id="29269-125">Translated</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="29269-126">검은색 (0, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="29269-126">Black (0, 0, 0, 1)</span></span>|<span data-ttu-id="29269-127">(0.75, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="29269-127">(0.75, 0, 0, 1)</span></span>|  
|<span data-ttu-id="29269-128">빨강 (1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="29269-128">Red (1, 0, 0, 1)</span></span>|<span data-ttu-id="29269-129">(1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="29269-129">(1, 0, 0, 1)</span></span>|  
|<span data-ttu-id="29269-130">녹색 (0, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="29269-130">Green (0, 1, 0, 1)</span></span>|<span data-ttu-id="29269-131">(0.75, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="29269-131">(0.75, 1, 0, 1)</span></span>|  
|<span data-ttu-id="29269-132">(0, 0, 1, 1) 파랑</span><span class="sxs-lookup"><span data-stu-id="29269-132">Blue (0, 0, 1, 1)</span></span>|<span data-ttu-id="29269-133">(0.75, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="29269-133">(0.75, 0, 1, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="29269-134">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="29269-134">Compiling the Code</span></span>  
 <span data-ttu-id="29269-135">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="29269-135">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="29269-136">대체 `ColorBars.bmp` 있는 이미지 파일 이름 및 경로 시스템에서 사용할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="29269-136">Replace `ColorBars.bmp` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29269-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="29269-137">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="29269-138">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="29269-138">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="29269-139">이미지 다시 칠하기</span><span class="sxs-lookup"><span data-stu-id="29269-139">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
