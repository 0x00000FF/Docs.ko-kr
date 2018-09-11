---
title: '방법: Viewport3D의 적중 테스트'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D visuals [WPF], hit-testing for
- hit tests [WPF], for 3-D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
ms.openlocfilehash: 297fe17b8844f7542255afcfe442fbf9b7a0d59d
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2018
ms.locfileid: "44352952"
---
# <a name="how-to-hit-test-in-a-viewport3d"></a><span data-ttu-id="4c8cc-102">방법: Viewport3D의 적중 테스트</span><span class="sxs-lookup"><span data-stu-id="4c8cc-102">How to: Hit Test in a Viewport3D</span></span>
<span data-ttu-id="4c8cc-103">적중 횟수의 3D 시각적 개체에 대 한 테스트 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Viewport3D>합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8cc-103">This example shows how to hit test for 3D Visuals in a <xref:System.Windows.Controls.Viewport3D>.</span></span>  
  
 <span data-ttu-id="4c8cc-104">때문에 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 2D 및 3D 정보를 반환 합니다만 3D 결과 읽습니다. 테스트 결과 반복 하는 것이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8cc-104">Because <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> returns 2D and 3D information, it is possible to iterate through the test results to read only 3D results.</span></span>  
  
 [!code-csharp[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
 [!code-vb[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]  
  
 <span data-ttu-id="4c8cc-105"><xref:System.Windows.Media.HitTestResultBehavior> 다음 코드에서 적중 횟수 테스트 결과 처리 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8cc-105">The <xref:System.Windows.Media.HitTestResultBehavior> in the following code determines how the hit test results are processed.</span></span>  <span data-ttu-id="4c8cc-106">`UpdateResultInfo` 및 `UpdateMaterial` 는 로컬로 정의 된 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="4c8cc-106">`UpdateResultInfo` and `UpdateMaterial` are locally defined methods.</span></span>  
  
 [!code-csharp[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
 [!code-vb[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]  
  
## <a name="see-also"></a><span data-ttu-id="4c8cc-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c8cc-107">See Also</span></span>  
 [<span data-ttu-id="4c8cc-108">3 차원 적중 테스트 샘플</span><span class="sxs-lookup"><span data-stu-id="4c8cc-108">3-D Hit Testing Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159959)
