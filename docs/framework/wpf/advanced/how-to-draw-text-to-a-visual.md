---
title: '방법: 시각적 요소에 텍스트 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
ms.openlocfilehash: bc7a4f989137ec2b021d27a6e112ff1aebd99d07
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523245"
---
# <a name="how-to-draw-text-to-a-visual"></a>방법: 시각적 요소에 텍스트 그리기
다음 예제에서는 텍스트를 그리는 방법에는 <xref:System.Windows.Media.DrawingVisual> 를 사용 하 여를 <xref:System.Windows.Media.DrawingContext> 개체입니다. 그리기 컨텍스트 호출에서 반환 되는 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> 메서드는 <xref:System.Windows.Media.DrawingVisual> 개체입니다. 그리기 컨텍스트에 그래픽 및 텍스트를 그릴 수 있습니다.  
  
 텍스트를 그리려면 그리기 컨텍스트에 사용 합니다 <xref:System.Windows.Media.DrawingContext.DrawText%2A> 메서드를 <xref:System.Windows.Media.DrawingContext> 개체입니다. 그리기 컨텍스트에 콘텐츠 그리기 작업을 완료 하는 경우 호출 된 <xref:System.Windows.Media.DrawingContext.Close%2A> 그리기 컨텍스트에 닫고 콘텐츠를 유지 하는 메서드.  
  
## <a name="example"></a>예제  
 [!code-csharp[DrawingVisualSample#110](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  위의 코드 예제가 발췌된 전체 코드 샘플을 보려면 [DrawingVisuals를 사용하여 적중 테스트 샘플](https://go.microsoft.com/fwlink/?LinkID=159994)을 참조하세요.
