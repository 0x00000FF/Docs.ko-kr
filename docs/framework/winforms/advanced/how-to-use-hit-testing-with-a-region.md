---
title: '방법: 영역을 사용하여 적중 테스트'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 40297fada3d042aee8c317eb787de03662f86cfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523090"
---
# <a name="how-to-use-hit-testing-with-a-region"></a><span data-ttu-id="d584a-102">방법: 영역을 사용하여 적중 테스트</span><span class="sxs-lookup"><span data-stu-id="d584a-102">How to: Use Hit Testing with a Region</span></span>
<span data-ttu-id="d584a-103">적중 횟수 테스트의 목적은 커서가 아이콘 또는 단추와 같은 특정된 개체 위에 있는지 여부를 결정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d584a-103">The purpose of hit testing is to determine whether the cursor is over a given object, such as an icon or a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d584a-104">예제</span><span class="sxs-lookup"><span data-stu-id="d584a-104">Example</span></span>  
 <span data-ttu-id="d584a-105">다음 예제에서는 두 개의 사각형 영역 결합 하 여 더하기 모양의 영역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d584a-105">The following example creates a plus-shaped region by forming the union of two rectangular regions.</span></span> <span data-ttu-id="d584a-106">가정 변수 `point` 가장 최근에 클릭 위치를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="d584a-106">Assume that the variable `point` holds the location of the most recent click.</span></span> <span data-ttu-id="d584a-107">확인 하는 코드 있는지 여부를 `point` 더하기 모양의 지역에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d584a-107">The code checks to see whether `point` is in the plus-shaped region.</span></span> <span data-ttu-id="d584a-108">지점이 (적중) 지역에 있으면 빨간색 불투명 브러시는 지역이 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="d584a-108">If the point is in the region (a hit), the region is filled with an opaque red brush.</span></span> <span data-ttu-id="d584a-109">그렇지 않으면 지역 빨간색 반투명 브러시를 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="d584a-109">Otherwise, the region is filled with a semitransparent red brush.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d584a-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="d584a-110">Compiling the Code</span></span>  
 <span data-ttu-id="d584a-111">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d584a-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d584a-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d584a-112">See Also</span></span>  
 <xref:System.Drawing.Region>  
 [<span data-ttu-id="d584a-113">GDI+의 영역</span><span class="sxs-lookup"><span data-stu-id="d584a-113">Regions in GDI+</span></span>](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)  
 [<span data-ttu-id="d584a-114">방법: 영역을 사용하여 클리핑</span><span class="sxs-lookup"><span data-stu-id="d584a-114">How to: Use Clipping with a Region</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)
