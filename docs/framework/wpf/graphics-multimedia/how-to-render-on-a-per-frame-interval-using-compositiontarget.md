---
title: '방법: CompositionTarget을 사용하여 프레임별 간격에 렌더링'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CompositionTarget objects [WPF], rendering per frame
- rendering per frame using CompositionTarget objects [WPF]
ms.assetid: 701246cd-66b7-4d69-ada9-17b3b433d95d
ms.openlocfilehash: 00b416d423a4bdc8bab576add2d77fd305ea6e0f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008930"
---
# <a name="how-to-render-on-a-per-frame-interval-using-compositiontarget"></a>방법: CompositionTarget을 사용하여 프레임별 간격에 렌더링
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션 엔진은 프레임 기반 애니메이션을 만들기 위한 다양한 기능을 제공합니다. 그러나 프레임당 렌더링을 좀 더 미세하게 제어해야 하는 애플리케이션 시나리오도 있습니다. <xref:System.Windows.Media.CompositionTarget> 프레임당 콜백을 기준으로 사용자 지정 애니메이션을 만드는 기능을 제공 하는 개체입니다.  
  
 <xref:System.Windows.Media.CompositionTarget> 응용 프로그램이 그려지는 표시 화면을 나타내는 정적 클래스가입니다. <xref:System.Windows.Media.CompositionTarget.Rendering> 응용 프로그램 장면이 그려질 때마다 이벤트가 발생 합니다. 렌더링 프레임 속도는 장면이 초당 그려지는 횟수입니다.  
  
> [!NOTE]
>  사용 하 여 전체 코드 샘플 <xref:System.Windows.Media.CompositionTarget>를 참조 하세요 [CompositionTarget 샘플](https://go.microsoft.com/fwlink/?LinkID=160045)합니다.  
  
## <a name="example"></a>예제  
 합니다 <xref:System.Windows.Media.CompositionTarget.Rendering> 이벤트가 발생 하는 동안는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 렌더링 프로세스입니다. 다음 예에서는 등록 하는 방법을 보여 줍니다.는 <xref:System.EventHandler> 정적 위임할 <xref:System.Windows.Media.CompositionTarget.Rendering> 메서드를 <xref:System.Windows.Media.CompositionTarget>입니다.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget1)]
 [!code-vb[CompositionTargetSample#CompositionTarget1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget1)]  
  
 렌더링 이벤트 처리기 메서드를 사용하여 사용자 지정 그리기 콘텐츠를 만들 수 있습니다. 이 이벤트 처리기 메서드는 프레임마다 한 번씩 호출됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]가 시각적 트리의 지속되는 렌더링 데이터를 컴퍼지션 장면 그래프로 마샬링할 때마다 이벤트 처리기 메서드가 호출됩니다. 또한 시각적 트리를 변경할 때마다 컴퍼지션 장면 그래프가 강제로 업데이트될 경우에도 이벤트 처리기 메서드가 호출됩니다. 이벤트 처리기 메서드는 레이아웃이 계산된 후에 호출됩니다. 그러나 이벤트 처리기 메서드에서 레이아웃을 수정할 수 있습니다. 즉, 레이아웃은 렌더링 전에 한 번 더 계산됩니다.  
  
 다음 예제에서는 어떻게 제공할 수 있습니다 그리기 사용자 지정을 <xref:System.Windows.Media.CompositionTarget> 이벤트 처리기 메서드. 이 예에서 배경색을 <xref:System.Windows.Controls.Canvas> 마우스의 좌표 위치에 따라 색 값을 사용 하 여 그려집니다. 내에서 마우스를 이동 하는 경우는 <xref:System.Windows.Controls.Canvas>, 해당 배경색이 변합니다. 또한 현재 경과 시간 및 렌더링된 프레임의 총 수에 따라 평균 프레임 속도가 계산됩니다.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget2](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget2)]
 [!code-vb[CompositionTargetSample#CompositionTarget2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget2)]  
  
 여러 다른 컴퓨터에서 다른 속도로 사용자 지정 그리기를 실행하는 경우도 있습니다. 사용자 지정 그리기가 프레임 속도와 별개가 아니기 때문입니다. 실행 하는 시스템 및 해당 시스템의 작업에 따라는 <xref:System.Windows.Media.CompositionTarget.Rendering> 이벤트 초당 다른 횟수를 호출할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 실행하는 장치의 그래픽 하드웨어 기능과 성능 수준을 확인하는 방법에 대한 자세한 내용은 [그래픽 렌더링 계층](../advanced/graphics-rendering-tiers.md)을 참조하세요.  
  
 추가 또는 제거 렌더링 <xref:System.EventHandler> 대리자 이벤트가 발생 하는 동안 이벤트가 완료 된 후까지 지연 됩니다 발생 합니다. 이 일치 하는 방법 <xref:System.MulticastDelegate>-기반된 이벤트는 공용 언어 런타임 (CLR)에서 처리 됩니다. 또한 렌더링 이벤트가 반드시 특정 순서로 호출되는 것은 아닙니다. 여러 개인 경우 <xref:System.EventHandler> 대리자는 특정 순서에 의존 하는 단일 등록 해야 <xref:System.Windows.Media.CompositionTarget.Rendering> 올바른 대리자 주문 직접 이벤트를 반복 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Media.CompositionTarget>
- [WPF 그래픽 렌더링 개요](wpf-graphics-rendering-overview.md)
