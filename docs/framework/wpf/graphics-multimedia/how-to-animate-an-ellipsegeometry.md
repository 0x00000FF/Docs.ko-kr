---
title: '방법: EllipseGeometry에 애니메이션 효과 적용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], EllipseGeometry objects [WPF]
- EllipseGeometry objects [WPF], animating
- graphics [WPF], animation
ms.assetid: 767b9b6e-9cb7-482e-b6c2-fee7750c3995
ms.openlocfilehash: dd92de2cf32a11b81f991939b614a899a25ff4ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564996"
---
# <a name="how-to-animate-an-ellipsegeometry"></a>방법: EllipseGeometry에 애니메이션 효과 적용
애니메이션을 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Geometry> 내는 <xref:System.Windows.Shapes.Path> 요소입니다. 다음 예제에서는 <xref:System.Windows.Media.Animation.PointAnimation> 애니메이션을 적용 하는 데 사용 되는 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 의 <xref:System.Windows.Media.EllipseGeometry>.  
  
## <a name="example"></a>예제  
 [!code-xaml[animatepath_snip_XAML#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip_XAML/CS/EllipseGeometryExample.xaml#1)]  
  
 [!code-csharp[animatepath_snip#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip/CSharp/EllipseGeometryExample.cs#101)]  
  
 [!code-vb[animatepath_snip#201](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animatepath_snip/VisualBasic/EllipseGeometryExample.vb#201)]  
  
## <a name="see-also"></a>참고자료
- [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
