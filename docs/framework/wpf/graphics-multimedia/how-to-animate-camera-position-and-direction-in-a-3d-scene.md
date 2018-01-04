---
title: "방법: 3차원 장면에서 카메라 위치 및 방향에 애니메이션 효과 주기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], camera position in 3-D scenes
- camera direction [WPF], animating in 3-D scenes
- 3-D scenes [WPF], animating camera position
- 3-D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3-D scenes
- animation [WPF], camera direction in 3-D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a8e80f1032e886d59240b74281c2ed87ad5743a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a><span data-ttu-id="adcda-102">방법: 3차원 장면에서 카메라 위치 및 방향에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="adcda-102">How to: Animate Camera Position and Direction in a 3D Scene</span></span>
<span data-ttu-id="adcda-103">다음 예제에서는 카메라의 위치 및 3D 장면에 가리키는지 방향에 애니메이션을 적용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="adcda-103">The following example shows how to animate the position of a camera and animate the direction it is pointing in a 3D scene.</span></span> <span data-ttu-id="adcda-104">사용 하 여 이렇게 <xref:System.Windows.Media.Animation.Point3DAnimation> 및 <xref:System.Windows.Media.Animation.Vector3DAnimation> 애니메이션 효과를 주는 <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> 및 <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> 각각의 속성은 <xref:System.Windows.Media.Media3D.PerspectiveCamera>합니다.</span><span class="sxs-lookup"><span data-stu-id="adcda-104">This is done by using <xref:System.Windows.Media.Animation.Point3DAnimation> and <xref:System.Windows.Media.Animation.Vector3DAnimation> to animate the <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> and <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> properties respectively of the <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="adcda-105">이벤트에 대 한 응답으로 장면의 보는 보기를 변경 하려면 다음과 같이 애니메이션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adcda-105">You might use an animation like this to change the onlooker's view of a scene in response to an event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adcda-106">예</span><span class="sxs-lookup"><span data-stu-id="adcda-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="adcda-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="adcda-107">See Also</span></span>  
 <xref:System.Windows.Media.Animation.Vector3DAnimation>  
 <xref:System.Windows.Media.Animation.Point3DAnimation>  
 [<span data-ttu-id="adcda-108">키 프레임을 사용하여 카메라 위치 및 방향에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="adcda-108">Animate Camera Position and Direction Using Key Frames</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-using-key-frames.md)  
 [<span data-ttu-id="adcda-109">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="adcda-109">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
