---
title: WPF 및 Windows Forms 상호 운용성
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- nester interoperation [WPF]
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid control [WPF interoperability]
ms.assetid: 9e8aa6b6-112c-4579-98d1-c974917df499
ms.openlocfilehash: 2e3390c3e387e75168958f946472a5a24a4bd440
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129274"
---
# <a name="wpf-and-windows-forms-interoperation"></a>WPF 및 Windows Forms 상호 운용성
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]에서는 응용 프로그램 인터페이스를 만들기 위한 두 개의 서로 다른 아키텍처를 제공합니다. <xref:System.Windows.Forms.Integration?displayProperty=nameWithType> 네임 스페이스는 일반 상호 운용성 시나리오를 사용 하도록 설정 하는 클래스를 제공 합니다. 상호 운용성 기능을 구현 하는 두 가지 주요 클래스는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 고 <xref:System.Windows.Forms.Integration.ElementHost>입니다. 이 항목에서는 지원되는 상호 운용성 시나리오와 지원되지 않는 시나리오를 설명합니다.  
  
> [!NOTE]
>  *하이브리드 컨트롤* 시나리오에는 특별 고려 사항이 제공됩니다. 하이브리드 컨트롤에서는 한 기술의 컨트롤이 다른 기술의 컨트롤에 중첩되어 있습니다. 이 특징은 *중첩된 상호 운용성*이라고도 합니다. *다단계 하이브리드 컨트롤*에는 두 개 이상의 하이브리드 컨트롤 중첩 수준이 있습니다. 다단계 중첩 상호 운용성의 예는 다른 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 포함하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 포함되어 있는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤입니다. 다단계 하이브리드 컨트롤은 지원되지 않습니다.  

<a name="Windows_Presentation_Foundation_Application_Hosting"></a>   
## <a name="hosting-windows-forms-controls-in-wpf"></a>WPF에서 Windows Forms 컨트롤 호스팅  
 다음 상호 운용성 시나리오는 지원 되는 때를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에 Windows Forms 컨트롤을 호스트:  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤은 XAML을 사용하여 하나 이상의 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 호스팅할 수 있습니다.  
  
-   코드를 사용하여 하나 이상의 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 호스팅할 수 있습니다.  
  
-   다른 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 포함하는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨테이너 컨트롤을 호스팅할 수 있습니다.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 마스터 및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 세부 정보를 사용하여 마스터/세부 정보 양식을 호스팅할 수 있습니다.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 마스터 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 세부 정보를 사용하여 마스터/세부 정보 양식을 호스팅할 수 있습니다.  
  
-   하나 이상의 [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] 컨트롤을 호스팅할 수 있습니다.  
  
-   하나 이상의 복합 컨트롤을 호스팅할 수 있습니다.  
  
-   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 사용하여 하이브리드 컨트롤을 호스팅할 수 있습니다.  
  
-   코드를 사용하여 하이브리드 컨트롤을 호스팅할 수 있습니다.  
  
### <a name="layout-support"></a>레이아웃 지원  
 다음과 같은 알려진된 제한 사항을 설명 할 때 합니다 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 호스 티 드 통합 하려고 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 시스템.  
  
-   경우에 따라 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 크기를 조정할 수 없거나 특정 차원으로만 크기를 조정할 수 있습니다. 예를 들어, 한 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox> 컨트롤은 컨트롤의 글꼴 크기에 의해 정의 된 단일 높이 지원 합니다. 에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 세로로 확장할는 요소 수를 호스트 하는 것으로 가정 하는 동적 레이아웃 <xref:System.Windows.Forms.ComboBox> 예상 대로 컨트롤이 늘어나지 것입니다.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 회전하거나 기울일 수 없습니다. 예를 들어, 사용자 인터페이스를 90도 회전하면 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 수직 위치를 유지합니다.  
  
-   대부분의 경우 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 서는 비례하여 크기 조정을 지원하지 않습니다. 컨트롤의 전체 크기는 조정할 수 있지만, 컨트롤의 구성 요소와 자식 컨트롤의 크기가 예상대로 조정되지 않을 수 있습니다. 이 제한 사항은 각 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에서 얼마나 효과적으로 크기 조정을 지원하는지에 따라 달라집니다.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용자 인터페이스에서 겹치는 동작을 제어하기 위해 요소의 z 순서를 변경할 수 있습니다. 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 개별 HWND에서 그려지므로 항상 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 위에 그려집니다.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 컨트롤 크기에 따라 자동 크기 조정을 지원합니다. 개별 요소의 크기는 동적으로 조정할 수 있지만 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용자 인터페이스에서 글꼴 크기를 변경해도 전체 레이아웃의 크기는 조정되지 않습니다.  
  
### <a name="ambient-properties"></a>앰비언트 속성  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤의 일부 앰비언트 속성에는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]에 해당하는 속성이 있습니다. 이러한 앰비언트 속성을 전파 하는 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤과에서 공용 속성으로 노출 된 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤입니다. <xref:System.Windows.Forms.Integration.WindowsFormsHost> 각 컨트롤 변환 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 앰비언트 속성에 해당 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 동일 합니다.  
  
 자세한 내용은 [Windows Forms 및 WPF 속성 매핑](windows-forms-and-wpf-property-mapping.md)을 참조하세요.  
  
### <a name="behavior"></a>동작  
 다음 테이블에서는 상호 운용성 동작을 설명합니다.  
  
|동작|지원함|지원되지 않음|  
|--------------|---------------|-------------------|  
|투명도|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 렌더링에서는 투명도를 지원합니다. 부모 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤의 배경이 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 배경이 될 수 있습니다.|일부 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에서는 투명도를 지원하지 않습니다. 예를 들어 합니다 <xref:System.Windows.Forms.TextBox> 하 고 <xref:System.Windows.Forms.ComboBox> 컨트롤에서 호스트 되는 경우 투명 하 게 됩니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.|  
|탭 이동|호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 탭 순서는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 기반 애플리케이션에서 해당 컨트롤을 호스팅할 때와 동일합니다.<br /><br /> Tab 키와 Shift+Tab을 사용하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에서 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤로 탭을 이동하는 기능은 정상적으로 작동합니다.<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 포함 된 컨트롤을 <xref:System.Windows.Forms.Control.TabStop%2A> 속성 값의 `false` 컨트롤을 통해 사용자가 탭 포커스를 받지 않습니다.<br /><br /> -각 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤에는 <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> 시기를 결정 하는 값을 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤이 포커스를 받는 합니다.<br />-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 내에 포함 된 컨트롤을 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨테이너에 지정 된 순서에 따라는 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성입니다. 마지막 탭 인덱스에서 탭 이동하면 다음 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤(있는 경우)에 포커스를 둡니다. 기타 포커스 가능 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 없으면, 탭 순서에서 첫 번째에 있는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 탭 이동이 반환됩니다.<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> 내에 있는 컨트롤에 대 한 값을 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 형제를 기준으로 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 포함 된를 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 제어 합니다.<br />-   탭 이동은 컨트롤별 동작을 준수합니다. 예를 들어에서 TAB 키를 누르면를 <xref:System.Windows.Forms.TextBox> 있는 컨트롤을 <xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A> 속성 값 `true` 포커스를 이동 하는 대신 텍스트 상자에 탭을 입력 합니다.|해당 사항 없음.|  
|화살표 키를 사용하여 탐색|탐색 화살표를 사용 하 여 키를 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤은 일반적인 동일 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨테이너 컨트롤: 위쪽 화살표 및 왼쪽 화살표 키는 이전 컨트롤을 선택 하 고 아래쪽 화살표 및 오른쪽 화살표 키를 다음 컨트롤을 선택 합니다.<br />-에 포함 된 첫 번째 컨트롤에서 화살표 및 왼쪽 화살표 키를 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤 SHIFT + TAB 바로 가기 키와 동일한 작업을 수행 합니다. 있으면 포커스 가능 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 외부 컨트롤에 포커스가 이동 된 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 제어 합니다. 이 동작은 표준에서 <xref:System.Windows.Forms.ContainerControl> 에 문제가 발생 하지 래핑 마지막 컨트롤입니다. 기타 포커스 가능 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 없으면, 탭 순서에서 마지막에 있는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 포커스가 반환됩니다.<br />-에 포함 된 마지막 컨트롤에서 화살표와 오른쪽 화살표 키를 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤 TAB 키와 동일한 작업을 수행 합니다. 있으면 포커스 가능 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 외부 컨트롤에 포커스가 이동 된 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 제어 합니다. 이 동작은 표준에서 <xref:System.Windows.Forms.ContainerControl> 동작 하는 첫 번째 컨트롤에 줄 바꿈 없음 발생 합니다. 기타 포커스 가능 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 없으면 탭 순서에서 첫 번째에 있는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 포커스가 반환됩니다.|해당 사항 없음.|  
|액셀러레이터|“지원되지 않음” 열에 명시된 경우를 제외하고는 액셀러레이터가 정상적으로 작동합니다.|기술 전체에서 중복된 액셀러레이터는 일반 중복 액셀러레이터처럼 작동하지 않습니다. 액셀러레이터가 기술 전체에 걸쳐 중복되어 있어, 하나 이상이 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 있고 다른 하나는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에 있으면 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에서 항상 액셀러레이터를 받습니다. 중복 액셀러레이터를 누르면 컨트롤 간에 포커스가 전환되지 않습니다.|  
|바로 가기 키|“지원되지 않음” 열에 명시된 경우를 제외하고는 바로 가기 키가 정상적으로 작동합니다.|전처리 단계에서 처리하는 -   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 바로 가기 키는 항상 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 바로 가기 키보다 우선합니다. 예를 들어 있는 경우는 <xref:System.Windows.Forms.ToolStrip> CTRL + S 바로 가기 키가 정의 사용 하 여 제어 하 고 있는지를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] CTRL + S에 바인딩된 명령을 <xref:System.Windows.Forms.ToolStrip> 컨트롤 처리기는 항상 먼저 호출 포커스에 관계 없이 합니다.<br />-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 처리 되는 바로 가기 키를 <xref:System.Windows.Forms.Control.KeyDown> 이벤트가 마지막으로 처리 됩니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다. 재정의 하 여이 동작을 방지할 수는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 <xref:System.Windows.Forms.Control.IsInputKey%2A> 메서드 또는 처리를 <xref:System.Windows.Forms.Control.PreviewKeyDown> 이벤트입니다. 반환 `true` 에서 <xref:System.Windows.Forms.Control.IsInputKey%2A> 메서드를의 값을 가져오거나 설정 합니다 <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=nameWithType> 속성을 `true` 에서 프로그램 <xref:System.Windows.Forms.Control.PreviewKeyDown> 이벤트 처리기입니다.|  
|AcceptsReturn, AcceptsTab 및 기타 컨트롤별 동작|라고 가정할 때 기본 키보드 동작을 변경 하는 속성 정상적으로 작동 합니다 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 재정의 제어 합니다 <xref:System.Windows.Forms.Control.IsInputKey%2A> 반환 하는 방법 `true`합니다.|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 키보드 동작을 처리 하 여 기본값을 변경 하는 컨트롤을 <xref:System.Windows.Forms.Control.KeyDown> 호스트의 이벤트는 마지막에 처리 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 제어 합니다. 이러한 컨트롤은 마지막으로 처리되므로 예기치 않은 동작이 발생할 수 있습니다.|  
|시작 및 종료 이벤트|포함 된 하지 포커스 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 입력 하 고 종료 이벤트는 일반적으로 단일에서 포커스가 변경 될 때 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 제어 합니다.|다음 포커스 변경이 발생하면 시작 및 종료 이벤트는 발생하지 않습니다.<br /><br /> 외부 내부를 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 제어 합니다.<br />내부에 외부를 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 제어 합니다.<br />-외부를 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 제어 합니다.<br />[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에서 호스트 되는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤을 <xref:System.Windows.Forms.Integration.ElementHost> 동일 내에서 호스팅되는 컨트롤 <xref:System.Windows.Forms.Integration.WindowsFormsHost>합니다.|  
|다중 스레딩|모든 종류의 다중 스레딩이 지원됩니다.|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기술에서는 단일 스레드 동시 모델을 가정합니다. 디버깅 중에 다른 스레드에서 프레임워크 개체를 호출하면 이 요구 사항을 적용하기 위해 예외가 발생합니다.|  
|보안|모든 상호 운용성 시나리오에는 완전 신뢰가 필요합니다.|부분 신뢰에서는 상호 운용성 시나리오가 허용되지 않습니다.|  
|액세스 가능성|모든 접근성 시나리오가 지원됩니다. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 모두 포함된 하이브리드 응용 프로그램에 사용될 때 보조 기술 제품이 올바르게 작동합니다.|해당 사항 없음.|  
|클립보드|모든 클립보드 작업이 정상적으로 작동합니다. 이 작업에는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 간에 잘라내기 및 붙여넣기가 포함됩니다.|해당 사항 없음.|  
|끌어서 놓기 기능|끌어서 놓기 작업이 모두 정상적으로 작동합니다. 이 작업에는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 간의 작업이 포함됩니다.|해당 사항 없음.|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>   
## <a name="hosting-wpf-controls-in-windows-forms"></a>Windows Forms에서 WPF 컨트롤 호스팅  
 다음 상호 운용성 시나리오는 경우 Windows Forms 컨트롤 호스트 지는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 제어:  
  
-   코드를 사용하여 하나 이상의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 호스팅.  
  
-   속성 시트를 호스팅된 하나 이상의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤과 연결.  
  
-   양식에서 하나 이상의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지 호스팅.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 창 시작.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 마스터와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 세부 정보를 사용하여 마스터/세부 정보 호스팅.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 마스터와 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 세부 정보를 사용하여 마스터/세부 정보 호스팅.  
  
-   사용자 지정 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 호스팅.  
  
-   하이브리드 컨트롤 호스팅.  
  
### <a name="ambient-properties"></a>앰비언트 속성  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 일부 앰비언트 속성에는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 해당하는 속성이 있습니다. 이러한 앰비언트 속성을 전파 하는 호스팅된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤과에서 공용 속성으로 노출 된 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤입니다. <xref:System.Windows.Forms.Integration.ElementHost> 각 컨트롤 변환 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 앰비언트 속성을 해당 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 동일 합니다.  
  
 자세한 내용은 [Windows Forms 및 WPF 속성 매핑](windows-forms-and-wpf-property-mapping.md)을 참조하세요.  
  
### <a name="behavior"></a>동작  
 다음 테이블에서는 상호 운용성 동작을 설명합니다.  
  
|동작|지원함|지원되지 않음|  
|--------------|---------------|-------------------|  
|투명도|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 렌더링에서는 투명도를 지원합니다. 부모 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 배경이 호스팅된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤의 배경이 될 수 있습니다.|해당 사항 없음.|  
|다중 스레딩|모든 종류의 다중 스레딩이 지원됩니다.|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기술에서는 단일 스레드 동시 모델을 가정합니다. 디버깅 중에 다른 스레드에서 프레임워크 개체를 호출하면 이 요구 사항을 적용하기 위해 예외가 발생합니다.|  
|보안|모든 상호 운용성 시나리오에는 완전 신뢰가 필요합니다.|부분 신뢰에서는 상호 운용성 시나리오가 허용되지 않습니다.|  
|액세스 가능성|모든 접근성 시나리오가 지원됩니다. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 모두 포함된 하이브리드 응용 프로그램에 사용될 때 보조 기술 제품이 올바르게 작동합니다.|해당 사항 없음.|  
|클립보드|모든 클립보드 작업이 정상적으로 작동합니다. 이 작업에는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 간에 잘라내기 및 붙여넣기가 포함됩니다.|해당 사항 없음.|  
|끌어서 놓기 기능|끌어서 놓기 작업이 모두 정상적으로 작동합니다. 이 작업에는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 간의 작업이 포함됩니다.|해당 사항 없음.|  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [연습: WPF에서 Windows Forms 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Windows Forms 및 WPF 속성 매핑](windows-forms-and-wpf-property-mapping.md)
