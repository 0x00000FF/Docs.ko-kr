---
title: WPF 창 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], displaying content via
- XAML pages [WPF], displaying
- content [WPF], displaying via XAML
- window objects [WPF]
- hosting [WPF], applications
- managing windows [WPF]
- dialog boxes [WPF]
- Page object [WPF]
- NavigationWindow objects [WPF]
- applications [WPF], hosting
- content [WPF], displaying
- events [WPF]
- content [WPF], displaying via procedural code
- modal windows [WPF]
- procedural code [WPF], displaying content via
- displaying content via procedural code [WPF]
- window management [WPF]
- displaying content [WPF]
- window events [WPF]
- windows [WPF]
- modal dialog boxes [WPF]
- displaying XAML pages [WPF]
ms.assetid: 737d04ec-8861-46c3-8d44-fa11d3528d23
ms.openlocfilehash: ad7d5225dbaaae544ab463a8f4f16bc43bdf4098
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558124"
---
# <a name="wpf-windows-overview"></a>WPF 창 개요
사용자가 windows 통해 독립 실행형 응용 프로그램을 Windows Presentation Foundation (WPF)와 상호 작용 합니다. 창의 기본 용도는 데이터를 시각화하는 콘텐츠를 호스트하고 사용자가 데이터와 상호 작용할 수 있도록 하는 것입니다. 독립 실행형 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램은 고유 창을 사용 하 여 제공 된 <xref:System.Windows.Window> 클래스입니다. 이 항목에서는 소개 <xref:System.Windows.Window> 독립 실행형 응용 프로그램에는 창을 만들고 관리의 기본 개념을 다루기 전에 합니다.  
  
> [!NOTE]
>  브라우저에서 호스팅되 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램을 만들 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 및 느슨한 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 페이지가 고유 창을 제공 하지 않습니다. 제공 하는 창에서 호스트 되는 대신, [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]합니다. 참조 [WPF XAML 브라우저 응용 프로그램 개요](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)합니다.  
  
  
<a name="TheWindowClass"></a>   
## <a name="the-window-class"></a>Window 클래스  
 다음 그림에서는 창을 구성하는 부분을 보여 줍니다.  
  
 ![창 요소](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure1.PNG "WindowOverviewFigure1")  
  
 창은 비클라이언트 영역과 클라이언트 영역의 두 영역으로 나뉩니다.  
  
 *비클라이언트 영역* 창에 의해 구현 됩니다 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 다음을 포함 한 대부분의 창을에 공통 된 창의 각 부분을 포함 합니다.  
  
-   테두리.  
  
-   제목 표시줄.  
  
-   아이콘.  
  
-   최소화, 최대화 및 복원 단추.  
  
-   닫기 단추.  
  
-   사용자가 창을 최소화, 최대화, 복원, 이동, 크기 조정 및 닫을 수 있는 메뉴 항목이 들어 있는 시스템 메뉴.  
  
 *클라이언트 영역* 창의 창의 비클라이언트 영역 내에서 영역 및 개발자가 컨트롤, 메뉴 모음 및 도구 모음 등의 응용 프로그램 관련 콘텐츠를 추가 하는 데 사용 됩니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], 창에 의해 캡슐화 됩니다는 <xref:System.Windows.Window> 에서 다음을 수행 하는 데 사용 하는 클래스:  
  
-   창을 표시합니다.  
  
-   창의 크기, 위치 및 모양을 구성합니다.  
  
-   응용 프로그램별 콘텐츠를 호스팅합니다.  
  
-   창의 수명을 관리합니다.  
  
<a name="DefiningAWindow"></a>   
## <a name="implementing-a-window"></a>창 구현  
 일반적인 창 구현의 모양과 동작을 구성 됩니다. 여기서 *모양* 사용자에 게 창이 표시 되는 모양을 정의 하 고 *동작* 창 함수 사용자가 조작 하는 방법을 정의 함께 합니다. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], 모양을 구현할 수 있습니다 및 동작을 사용 하 여 창을 코딩 하거나 또는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그입니다.  
  
 그러나 일반적으로 창의 모양을 사용 하 여 구현 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그 및 해당 동작은 구현 됩니다 코드 숨김을 사용 하 여 다음 예제와 같이 합니다.  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 사용 하도록 설정 하려면 한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 마크업 파일 및 코드 숨김 파일을 함께 사용 하려면 다음이 필요 합니다.  
  
-   태그에서는 `Window` 요소 포함 되어야 합니다는 `x:Class` 특성입니다. 응용 프로그램을 빌드할 때 `x:Class` 파일 사용 하면 태그에서 [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] 만들려는 `partial` 에서 파생 된 클래스 <xref:System.Windows.Window> 변수로 지정 된 이름을 가진는 `x:Class` 특성입니다. 이 위해서는 추가 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 에 대 한 네임 스페이스 선언을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 스키마 ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ). 생성 된 `partial` 클래스가 구현 하는 `InitializeComponent` 메서드를 이벤트를 등록 하 고 태그에서 구현 되는 속성을 설정 하기 위해 호출 됩니다.  
  
-   코드 숨김 클래스 여야 합니다는 `partial` 변수로 지정 된 동일한 이름의 클래스는 `x:Class` 태그에서 특성에서 파생 되어야 <xref:System.Windows.Window>합니다. 이렇게 하면 연결 된 코드 숨김 파일이 `partial` 응용 프로그램이 빌드될 때 마크업 파일에 대해 생성 되는 클래스 (참조 [WPF 응용 프로그램 빌드](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)).  
  
-   코드 숨김에서 <xref:System.Windows.Window> 클래스가 호출 하는 생성자를 구현 해야 합니다는 `InitializeComponent` 메서드. `InitializeComponent` 구현 파일에서 생성 된 태그에서 `partial` 클래스를 이벤트 등록 및 태그에 정의 된 속성을 설정 합니다.  
  
> [!NOTE]
>  추가 하는 경우 새 <xref:System.Windows.Window> 를 사용 하 여 프로젝트에 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], <xref:System.Windows.Window> 태그와 코드 숨김을 사용 하 여 구현 되 고으로 태그와 코드 숨김 파일 간의 연결을 만드는 데 필요한 구성을 포함 여기에서 설명 합니다.  
  
 이 구성을 사용 모양을 정의 하 고 창에 집중할 수 있습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그와 코드 숨김의 동작을 구현 합니다. 다음 예제에서 구현 되는 단추가 있는 창 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그 및 단추에 대 한 이벤트 처리기 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 코드 숨김에서 구현 된 이벤트입니다.  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>   
## <a name="configuring-a-window-definition-for-msbuild"></a>MSBuild에 대해 창 정의 구성  
 사용자가 창을 구현 하는 방법은 구성에 대 한 결정 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]합니다. 모두 사용 하 여 정의 된 창에 대 한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그 및 코드 숨김:  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그 파일으로 구성 된 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` 항목입니다.  
  
-   코드 숨김 파일으로 구성 된 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Compile` 항목입니다.  
  
 다음에는 나타내지 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] 프로젝트 파일입니다.  
  
```xml  
<Project ...  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 빌드에 대 한 내용은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램 참조 [WPF 응용 프로그램 빌드](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)합니다.  
  
<a name="WindowLifetime"></a>   
## <a name="window-lifetime"></a>창 수명  
 다른 클래스와 마찬가지로 창에는 창이 열린 후 처음 인스턴스화될 때 시작하여, 열린 후 활성화 및 비활성화되고 최종적으로 닫힐 때까지의 기간인 수명이 있습니다.  
  
  
<a name="Opening_a_Window"></a>   
### <a name="opening-a-window"></a>창 열기  
 창을 열려면 먼저 다음 예제에서 설명하는 것처럼 창의 인스턴스를 만듭니다.  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 이 예제에서는 `MarkupAndCodeBehindWindow` 응용 프로그램이 시작 되 면 발생 하는 경우 인스턴스화될 때는 <xref:System.Windows.Application.Startup> 이벤트가 발생 합니다.  
  
 에 대 한 참조에서 관리 되는 창의 목록에 자동으로 추가 됩니다 창이 인스턴스화되면는 <xref:System.Windows.Application> 개체 (참조 <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>). 또한 인스턴스화할 첫 번째 창, 기본적으로 설정 하 여 <xref:System.Windows.Application> 주 응용 프로그램 창으로 (참조 <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>).  
  
 마지막 호출 하 여는 <xref:System.Windows.Window.Show%2A> 메서드가 결과 다음 그림에 나와 있습니다.  
  
 ![Window.Show 호출로 열린 창](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure8.png "WindowOverviewFigure8")  
  
 호출 하 여 열려 있는 창을 <xref:System.Windows.Window.Show%2A> 는 모덜리스 창 응용 프로그램을 사용자가 동일한 응용 프로그램에서 다른 창을 활성화를 허용 하는 모드에서 작동 하는 것을 의미 합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Window.ShowDialog%2A> 예: 대화 상자 창이 열리며 해당 모달 형식으로 호출 됩니다. 참조 [대화 상자 개요](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md) 자세한 정보에 대 한 합니다.  
  
 때 <xref:System.Windows.Window.Show%2A> 은 호출 창이 초기화 작업을 수행한 사용자 입력을 받을 수 있는 인프라를 설정 표시 되기 전에 합니다. 창이 초기화 될 때는 <xref:System.Windows.Window.SourceInitialized> 이벤트가 발생 하 고 창을 표시 합니다.  
  
 가기로 <xref:System.Windows.Application.StartupUri%2A> 응용 프로그램이 시작 될 때 자동으로 열려 있는 첫 번째 창을 지정로 설정할 수 있습니다.  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 응용 프로그램이 시작 되 면 값에 의해 지정 된 창의 <xref:System.Windows.Application.StartupUri%2A> 열릴 호출 하 여 창을 열려면 모덜리스; 내부적으로 해당 <xref:System.Windows.Window.Show%2A> 메서드.  
  
<a name="Ownership"></a>   
#### <a name="window-ownership"></a>창 소유권  
 사용 하 여 열려 있는 창에서 <xref:System.Windows.Window.Show%2A> 메서드를 만든 창에는 암시적 관계가 설정 되어 있지 않으면 사용자가 다른 상관 없이 두 창 중 하나에서 다음을 수행할 수 있도록 즉 어느 창 상호 작용할 수 있습니다.  
  
-   다른 처리 (창 중 하나에 없는 경우 해당 <xref:System.Windows.Window.Topmost%2A> 속성이로 설정 `true`).  
  
-   다른 창에 영향을 주지 않고 최소화, 최대화 및 복원합니다.  
  
 일부 창은 해당 창을 여는 창과의 관계를 필요로 합니다. 예를 들어 한 [!INCLUDE[TLA#tla_ide](../../../../includes/tlasharptla-ide-md.md)] 속성 창과 도구 창 생성에 사용 되는 창에 일반적인 동작은 해당 응용 프로그램 열 수 있습니다. 또한 이러한 창은 항상 해당 창을 만든 창과 함께 닫히고, 최소화되고, 최대화되고, 복원되어야 합니다. 창을 두 개를 늘려 이러한 관계를 설정할 수 *자체* 다른, 설정 하 여 및는 <xref:System.Windows.Window.Owner%2A> 속성의는 *창을 소유* 에 대 한 참조는 *소유자 창*합니다. 다음 예제에서 이를 확인할 수 있습니다.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 소유권이 설정된 후:  
  
-   소유 창을의 값을 검사 하 여 해당 소유자 창을 참조할 수는 <xref:System.Windows.Window.Owner%2A> 속성입니다.  
  
-   소유자 창이 소유한의 값을 검사 하 여 모든 창을 검색할 수는 <xref:System.Windows.Window.OwnedWindows%2A> 속성입니다.  
  
<a name="Preventing"></a>   
#### <a name="preventing-window-activation"></a>창 활성화 방지  
 예: 인터넷 메신저 스타일 응용 프로그램의 대화 창, 전자 메일 응용 프로그램의 알림 창이 표시 될 때 windows를 활성화 하지 않아야 여기서 시나리오가 있습니다.  
  
 응용 프로그램에 표시 될 때 활성화 하지 않아야 하는 창을 경우 설정할 수 있습니다는 <xref:System.Windows.Window.ShowActivated%2A> 속성을 `false` 호출 하기 전에 <xref:System.Windows.Window.Show%2A> 메서드를 처음으로 합니다. 이렇게 하면 다음과 같은 결과가 나타납니다.  
  
-   창이 활성화되지 않습니다.  
  
-   창의 <xref:System.Windows.Window.Activated> 이벤트가 발생 하지 않습니다.  
  
-   현재 활성 창이 활성 상태로 유지됩니다.  
  
 그러나 사용자가 클라이언트 영역이나 비클라이언트 영역을 클릭하여 창을 활성화하면 해당 창이 활성화됩니다. 이 경우:  
  
-   창이 활성화됩니다.  
  
-   창의 <xref:System.Windows.Window.Activated> 이벤트가 발생 합니다.  
  
-   이전에 활성 상태였던 창이 비활성화됩니다.  
  
-   창의 <xref:System.Windows.Window.Deactivated> 및 <xref:System.Windows.Window.Activated> 사용자 작업에 대 한 응답에서 예상 대로 이벤트 이후에 발생 합니다.  
  
<a name="Window_Activation"></a>   
### <a name="window-activation"></a>창 활성화  
 활성 창 창이 처음 열릴 때 됩니다 (으로 경우를 제외 <xref:System.Windows.Window.ShowActivated%2A> 로 설정 `false`). *활성 창* 현재 키 입력 및 마우스 클릭 등의 사용자 입력을 캡처하고 창입니다. 창이 활성화 되 면 발생는 <xref:System.Windows.Window.Activated> 이벤트입니다.  
  
> [!NOTE]
>  창이 처음 열릴 때의 <xref:System.Windows.FrameworkElement.Loaded> 및 <xref:System.Windows.Window.ContentRendered> 후에 발생 하는 <xref:System.Windows.Window.Activated> 이벤트가 발생 합니다. 이 점을 고려 창을 간주할 수 있습니다 때 열리는 <xref:System.Windows.Window.ContentRendered> 발생 합니다.  
  
 창이 활성 창이 되면 사용자는 같은 응용 프로그램의 다른 창을 활성화하거나 다른 응용 프로그램을 활성화할 수 있습니다. 현재 활성 창의 비활성화 되 고 시킵니다에 도달 하면는 <xref:System.Windows.Window.Deactivated> 이벤트입니다. 마찬가지로, 사용자가 현재 비활성화 창 선택, 창 다시 활성화 되 고 <xref:System.Windows.Window.Activated> 발생 합니다.  
  
 처리 하는 일반적인 이유 중 하나 <xref:System.Windows.Window.Activated> 및 <xref:System.Windows.Window.Deactivated> 가 구현 창이 활성화 된 경우에 실행할 수 있는 기능을 사용 하지 않도록 설정 합니다. 예를 들어 일부 창은 게임 및 비디오 플레이어를 포함하여 지속적인 사용자의 입력이나 주의가 필요한 대화식 콘텐츠를 표시합니다. 다음 예제는 간단한 비디오 플레이어를 처리 하는 방법을 보여 주는 <xref:System.Windows.Window.Activated> 및 <xref:System.Windows.Window.Deactivated> 이 동작을 구현 합니다.  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 다른 형식의 응용 프로그램은 창이 비활성화되었을 때 계속 백그라운드에서 코드를 실행할 수 있습니다. 예를 들어 메일 클라이언트는 사용자가 다른 응용 프로그램을 사용하고 있을 때 메일 서버를 계속 폴링할 수 있습니다. 이러한 응용 프로그램에는 기본 창이 비활성화되었을 때 다른 동작 또는 추가 동작을 제공하기도 합니다. 메일 프로그램의 경우에 이것은 새 메일 항목을 받은 편지함에 추가하고 시스템 트레이에 알림 아이콘을 추가하는 작업을 의미할 수 있습니다. 알림 아이콘 메일 창이 검사 하 여 확인할 수 있는 활성 상태가 아닐 때에 표시 하면는 <xref:System.Windows.Window.IsActive%2A> 속성입니다.  
  
 창을 호출 하 여 더 신속 사용자에 게 할 수는 백그라운드 작업이 완료 되 면 <xref:System.Windows.Window.Activate%2A> 메서드. 사용자가 상호 작용 하는 경우 다른 응용 프로그램 활성화 <xref:System.Windows.Window.Activate%2A> 창의 작업 표시줄 단추가 깜박이 호출 됩니다. 사용자가 현재 응용 프로그램 상호 작용을 하는 경우 호출 <xref:System.Windows.Window.Activate%2A> 창을를 포그라운드로 전환 됩니다.  
  
> [!NOTE]
>  응용 프로그램 범위 활성화를 사용 하 여 처리할 수 있습니다는 <xref:System.Windows.Application.Activated?displayProperty=nameWithType> 및 <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> 이벤트입니다.  
  
<a name="Closing_a_Window"></a>   
### <a name="closing-a-window"></a>창 닫기  
 창의 수명은 사용자가 창을 닫을 때 끝나게 됩니다. 창은 다음을 포함하여 비클라이언트 영역의 요소를 사용하여 닫을 수 있습니다.  
  
-   **닫기** 의 항목은 **시스템** 메뉴.  
  
-   ALT+F4 누르기.  
  
-   키를 누르면는 **닫기** 단추입니다.  
  
 클라이언트 영역에 창을 닫기 위한 추가적인 메커니즘을 제공할 수 있으며 이 메커니즘에는 일반적으로 다음이 포함됩니다.  
  
-   **종료** 항목에 **파일** 일반적으로 기본 응용 프로그램 창에 대 한 메뉴입니다.  
  
-   A **닫기** 항목에 **파일** 보조 응용 프로그램 창에 일반적으로 메뉴.  
  
-   A **취소** 단추, 일반적으로 모달 대화 상자.  
  
-   A **닫기** 단추, 일반적으로 모덜리스 대화 상자.  
  
 호출 해야 이러한 사용자 지정 메커니즘 중 하나에 대 한 응답에서 창의 닫으려면는 <xref:System.Windows.Window.Close%2A> 메서드. 다음 예제에서는 선택 하 여 창을 닫을 수 있는 기능을 구현 하는 **종료** 에 **파일** 메뉴.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 두 개의 이벤트를 발생 창이 닫히면: <xref:System.Windows.Window.Closing> 및 <xref:System.Windows.Window.Closed>합니다.  
  
 <xref:System.Windows.Window.Closing> 창이 닫히고 창을 여 닫기를 방지할 수 있는 메커니즘을 제공 하기 전에 발생 합니다. 대개 창이 닫히면 안 되는 한 가지 이유는 창 콘텐츠에 수정된 데이터가 있는 경우입니다. 이 경우에는 <xref:System.Windows.Window.Closing> 데이터가 커밋되지 않았는지 여부와 데이터를 저장 하지 않고 창을 닫고 계속할 것인지 아니면 창 닫기를 취소를 사용자에 게 하려는 경우를 결정 하는 이벤트를 처리할 수 있습니다. 다음 예제에서는 처리의 주요 측면은 <xref:System.Windows.Window.Closing>합니다.  
  
 [!code-csharp[WindowClosingSnippets](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  
 
  
 <xref:System.Windows.Window.Closing> 이벤트 처리기가 전달는 <xref:System.ComponentModel.CancelEventArgs>, 구현 하는 `Boolean` <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 로 설정 하는 속성 `true` 창을 닫는 하지 못하도록 합니다.  
  
 경우 <xref:System.Windows.Window.Closing> 처리 되지 않은 또는 처리는 되었지만 취소 되지 않은, 창이 닫힙니다. 창이 실제로 닫히기 바로 전에 <xref:System.Windows.Window.Closed> 발생 합니다. 이 시점에서는 창 닫기를 방지할 수 없습니다.  
  
> [!NOTE]
>  기본 응용 프로그램 창을 닫을 때 자동으로 종료 하도록 응용 프로그램을 구성할 수 있습니다 (참조 <xref:System.Windows.Application.MainWindow%2A>) 또는 마지막 창이 닫힙니다. 자세한 내용은 <xref:System.Windows.Application.ShutdownMode%2A>를 참조하세요.  
  
 창의 클라이언트 및 비클라이언트 영역에서 제공 하는 메커니즘을 통해 명시적으로 닫을 수 있지만, 창의 닫을 수도 있습니다 암시적으로 응용 프로그램의 다른 부분에는 동작의 결과로 또는 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], 다음을 포함 하 여:  
  
-   사용자가 로그 오프 하거나 Windows를 종료 합니다.  
  
-   창의 소유자 닫습니다 (참조 <xref:System.Windows.Window.Owner%2A>).  
  
-   기본 응용 프로그램 창이 닫혀 있는 및 <xref:System.Windows.Application.ShutdownMode%2A> 은 <xref:System.Windows.ShutdownMode.OnMainWindowClose>합니다.  
  
-   <xref:System.Windows.Application.Shutdown%2A>가 호출된 경우  
  
> [!NOTE]
>  창을 닫은 뒤에는 다시 열 수 없습니다.  
  
<a name="Window_Lifetime_Events"></a>   
### <a name="window-lifetime-events"></a>창 수명 이벤트  
 다음 그림에서는 창의 수명에서 발생하는 주요 이벤트를 순서대로 보여 줍니다.  
  
 ![창 수명](../../../../docs/framework/wpf/app-development/media/windowlifetimeevents.png "WindowLifetimeEvents")  
  
 다음 그림 않고 표시 하는 창 유효 기간에는 주요 이벤트 시퀀스를 보여 줍니다 (<xref:System.Windows.Window.ShowActivated%2A> 로 설정 되어 `false` 창이 표시 되기 전에).  
  
 ![창 수명 &#40;Window.ShowActivated &#61; False&#41;](../../../../docs/framework/wpf/app-development/media/windowlifetimenoact.png "WindowLifetimeNoAct")  
  
<a name="WindowLocation"></a>   
## <a name="window-location"></a>창 위치  
 창은 열릴 때 바탕 화면에 상대적인 x 및 y 크기의 위치를 가집니다. 이 위치를 검사 하 여 확인할 수 있습니다는 <xref:System.Windows.Window.Left%2A> 및 <xref:System.Windows.Window.Top%2A> 속성을 각각. 이 속성을 설정하여 창의 위치를 변경할 수 있습니다.  
  
 초기 위치를 지정할 수도 있습니다는 <xref:System.Windows.Window> 처음 나타날 때 설정 하 여는 <xref:System.Windows.Window.WindowStartupLocation%2A> 다음 중 하나를 사용 하 여 속성 <xref:System.Windows.WindowStartupLocation> 열거형 값:  
  
-   <xref:System.Windows.WindowStartupLocation.CenterOwner>(기본값)  
  
-   <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
-   <xref:System.Windows.WindowStartupLocation.Manual>  
  
 시작 위치로 지정 된 경우 <xref:System.Windows.WindowStartupLocation.Manual>, 및 <xref:System.Windows.Window.Left%2A> 및 <xref:System.Windows.Window.Top%2A> 속성이 설정 되지 않은 <xref:System.Windows.Window> 위치에 대 한 기간에 게 표시 합니다.  
  
<a name="Topmost_Windows_and_Z_Order"></a>   
### <a name="topmost-windows-and-z-order"></a>최상위 창 및 Z 순서  
 창에는 x 및 y 위치 이외에도 다른 창과 상대적인 수직 위치를 결정하는 z 차원의 위치도 있습니다. 이를 창의 z 순서라고 하며 여기에는 일반 z 순서와 최상위 z 순서의 두 가지 유형이 있습니다. 창의 위치는 *일반 z 순서* 현재 활성 상태 인지 여부에 의해 결정 됩니다. 기본적으로 창은 일반 z 순서로 배치됩니다. 창의 위치는 *최상위 z 순서* 현재 활성화 되었는지 여부에 따라 결정 됩니다. 최상위 z 수준의 창은 항상 일반 z 순서 창의 위에 위치합니다. 설정 하 여 창의 맨 위 z 순서에 있는 해당 <xref:System.Windows.Window.Topmost%2A> 속성을 `true`합니다.  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 각 z 순서 안에서는 현재 활성화된 창이 같은 z 순서를 가진 다른 모든 창 위에 나타납니다.  
  
<a name="WindowSize"></a>   
## <a name="window-size"></a>창 크기  
 바탕 화면 위치 이외 창에 다양 한 width 및 height 속성을 포함 하 여 여러 속성에 의해 결정 되는 크기 및 <xref:System.Windows.Window.SizeToContent%2A>합니다.  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A><xref:System.Windows.FrameworkElement.Width%2A>, 및 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 창 수명 동안 있을 수 있습니다 및 다음 예제와 같이 구성 된 너비의 범위를 관리 하는 데 사용 됩니다.  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 관리 하는 창 높이 <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, 및 <xref:System.Windows.FrameworkElement.MaxHeight%2A>, 다음 예제와 같이 구성 됩니다.  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 다양한 너비 값과 높이 값이 각각 범위를 지정하고 있기 때문에, 크기 조정 가능한 창의 너비와 높이는 지정한 범위 내에서 임의의 크기로 설정될 수 있습니다. 현재 너비 및 높이 검색 하려면 검사 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 및 <xref:System.Windows.FrameworkElement.ActualHeight%2A>각각.  
  
 너비와 높이 창의 원하는 경우 창 크기에 맞는 크기의 콘텐츠를 사용할 수 있습니다는 <xref:System.Windows.Window.SizeToContent%2A> 속성에는 다음 값입니다.  
  
-   <xref:System.Windows.SizeToContent.Manual>. 아무런 영향이 없습니다(기본값).  
  
-   <xref:System.Windows.SizeToContent.Width>. 콘텐츠 너비에 맞추기 <xref:System.Windows.FrameworkElement.MinWidth%2A> 및 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 콘텐츠의 너비입니다.  
  
-   <xref:System.Windows.SizeToContent.Height>. 콘텐츠 높이 맞게 <xref:System.Windows.FrameworkElement.MinHeight%2A> 및 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 콘텐츠의 높이입니다.  
  
-   <xref:System.Windows.SizeToContent.WidthAndHeight>. 콘텐츠 너비와 높이 모두 설정 것과 동일한 결과가에 맞추기 <xref:System.Windows.FrameworkElement.MinHeight%2A> 및 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 내용 및 설정을의 높이 <xref:System.Windows.FrameworkElement.MinWidth%2A> 및 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 콘텐츠 너비에 있습니다.  
  
 다음 예는 창이 처음 표시될 때 콘텐츠에 맞도록 수직 및 수평으로 크기를 자동으로 조정하는 창을 보여 줍니다.  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 설정 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Window.SizeToContent%2A> 창의 내용에 맞게 크기 조정 하는 방법을 지정 하는 코드에서 속성입니다.
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>   
## <a name="order-of-precedence-for-sizing-properties"></a>크기 조정 속성에 대한 우선 순위 순서  
 기본적으로 창의 다양한 크기 속성이 결합되어 크기 조정 가능한 창의 너비와 높이의 범위가 정의됩니다. 유효한 범위는 유지 관리 하려면 <xref:System.Windows.Window> 의 우선 순위는 다음 순서를 사용 하 여 크기 속성의 값을 평가 합니다.  
  
 **높이 속성:**  
  
1.  <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType> >  
  
2.  <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType> >  
  
3.  <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType> >  
  
4.  <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>  
  
 **너비 속성:**  
  
1.  <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType> >  
  
2.  <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType> >  
  
3.  <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType> >  
  
4.  <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>  
  
 우선 순위는 창 크기를 확인할 수도 최대화 되었을으로 관리 되는 경우는 <xref:System.Windows.Window.WindowState%2A> 속성입니다.  
  
<a name="WindowState"></a>   
## <a name="window-state"></a>창 상태  
 크기 조정 가능한 창의 수명은 표준, 최소화 및 최대화의 세 가지 상태를 가질 수 있습니다. 포함 된 창이 *일반* 상태가 창의 기본 상태입니다. 크기 조정 가능 창이 표준 상태인 경우 사용자는 크기 조정 그립이나 테두리를 사용하여 창을 이동하고 크기 조정할 수 있습니다.  
  
 포함 된 창이 *최소화* 상태 작업 표시줄 단추를 축소 경우 <xref:System.Windows.Window.ShowInTaskbar%2A> 로 설정 되어 `true`, 그렇지 않으면 축소 가능한 최소 크기를 수 있으며 바탕 화면의 왼쪽 아래 모퉁이에 스스로 재배치 되 합니다. 이러한 최소화된 창 유형은 테두리나 크기 조정 그립을 사용하여 크기 조정할 수 없습니다. 하지만 작업 표시줄에 표시되지 않은 최소화된 창은 바탕 화면에서 끌 수 있습니다.  
  
 포함 된 창이 *최대화* 정도로 될 수 있습니다 최대 크기로 확장 상태가 해당 <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, 및 <xref:System.Windows.Window.SizeToContent%2A> 속성에 지정 합니다. 최소화된 창과 마찬가지로 최대화된 창은 크기 조정 그립을 사용하거나 테두리를 끌어서 크기 조정할 수 없습니다.  
  
> [!NOTE]
>  값은 <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, 및 <xref:System.Windows.FrameworkElement.Height%2A> 창이 현재 최대화 또는 최소화 하는 경우에 항상 정상 상태에 대 한 값을 나타내는 창의 속성입니다.  
  
 창의 상태를 설정 하 여 구성할 수 있습니다는 <xref:System.Windows.Window.WindowState%2A> 속성에서 다음 중 하나를 가질 수 있는 <xref:System.Windows.WindowState> 열거형 값:  
  
-   <xref:System.Windows.WindowState.Normal>(기본값)  
  
-   <xref:System.Windows.WindowState.Maximized>  
  
-   <xref:System.Windows.WindowState.Minimized>  
  
 다음 예제에서는 열릴 때 최대화되어 표시되는 창을 만드는 방법을 보여 줍니다.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 일반적으로 설정 해야 <xref:System.Windows.Window.WindowState%2A> 창의 초기 상태를 구성할 수 있습니다. 크기 조정 가능한 창이 표시되면 사용자는 창의 제목 표시줄에서 최소화, 최대화 및 복원 단추를 눌러 창 상태를 변경할 수 있습니다.  
  
<a name="WindowAppearance"></a>   
## <a name="window-appearance"></a>창 모양  
 단추, 레이블 및 텍스트 상자와 같은 창 특정 콘텐츠를 창에 추가하여 창의 클라이언트 영역의 모양을 변경할 수 있습니다. 비클라이언트 영역을 구성 하려면 <xref:System.Windows.Window> 포함 하는 몇 가지 속성이 제공 <xref:System.Windows.Window.Icon%2A> 창의 아이콘을 설정 하 고 <xref:System.Windows.Window.Title%2A> 제목을 설정 하 합니다.  
  
 또한 창의 크기 조정 모드, 창 스타일 및 바탕 화면 작업 표시줄에 단추로 표시될 것인지 여부를 구성하여 비클라이언트 영역 테두리의 모양과 동작을 변경할 수도 있습니다.  
  
  
<a name="Resize_Mode"></a>   
### <a name="resize-mode"></a>크기 조정 모드  
 에 따라는 <xref:System.Windows.Window.WindowStyle%2A> 제어할 수 속성을 어떻게 (및 경우) 사용자가 창의 크기를 조정할 수 있습니다. 사용자는 창 테두리를 끌어 마우스를 사용 하는지 여부는 다양 한 창 스타일 여부가 **최소화**, **최대화**, 및 **크기를 조정** 단추 비클라이언트 영역에 표시 하 고, 나타나는 경우, 사용할 수 있는지 여부.  
  
 설정 하 여 창 크기 조정 하는 방법을 구성할 수 있습니다는 <xref:System.Windows.Window.ResizeMode%2A> 다음 중 하나일 수 있는 속성 <xref:System.Windows.ResizeMode> 열거형 값:  
  
-   <xref:System.Windows.ResizeMode.NoResize>  
  
-   <xref:System.Windows.ResizeMode.CanMinimize>  
  
-   <xref:System.Windows.ResizeMode.CanResize>(기본값)  
  
-   <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 와 마찬가지로 <xref:System.Windows.Window.WindowStyle%2A>, 창 크기 조정 모드에서 설정 가능성이 합니다 즉의 수명 동안 변경 될 가능성이 없는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그입니다.  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 창이 최대화 되었는지 여부를 감지할 수는 최소화 또는 검사 하 여 복원 된 <xref:System.Windows.Window.WindowState%2A> 속성입니다.  
  
<a name="Window_Style"></a>   
### <a name="window-style"></a>창 스타일  
 창의 비클라이언트 영역에서 노출되는 테두리는 대부분의 응용 프로그램에 적합합니다. 하지만 창의 유형에 따라 다른 유형의 테두리가 필요하거나 테두리가 전혀 필요 없는 경우가 있습니다.  
  
 창 테두리의 유형을 제어 하려면 가져옵니다, 설정한 해당 <xref:System.Windows.Window.WindowStyle%2A> 의 다음 값 중 하나를 사용 하 여 속성의 <xref:System.Windows.WindowStyle> 열거형:  
  
-   <xref:System.Windows.WindowStyle.None>  
  
-   <xref:System.Windows.WindowStyle.SingleBorderWindow>(기본값)  
  
-   <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
-   <xref:System.Windows.WindowStyle.ToolWindow>  
  
 이러한 창 스타일의 효과는 다음 그림에서 볼 수 있습니다.  
  
 ![창 스타일](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure6.PNG "WindowOverviewFigure6")  
  
 설정할 수 있습니다 <xref:System.Windows.Window.WindowStyle%2A> 중 하나를 사용 하 여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그 또는 코드가; 창의 수명 동안 변경 될 가능성이 없기 때문에 대개 구성한를 사용 하 여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그입니다.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a>사각형이 아닌 창 스타일  
 경우가 있을 있는 테두리 스타일 <xref:System.Windows.Window.WindowStyle%2A> 사용 하면 권한이 없는 사용할 수 있습니다. 예를 들어 응용 프로그램을 만드는 사각형이 아닌 테두리가 있는 같은 경우가 [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 사용 합니다.  
  
 예를 들어 다음 그림과 같은 말 상자 창을 고려해 보겠습니다.  
  
 ![사각형이 아닌 창](../../../../docs/framework/wpf/app-development/media/nonrectangularwindowfigure.PNG "NonRectangularWindowFigure")  
  
 이러한 형식의 설정 하 여 만들 수 있습니다는 <xref:System.Windows.Window.WindowStyle%2A> 속성을 <xref:System.Windows.WindowStyle.None>, 특별 한를 사용 하 여이 지원 하 고 <xref:System.Windows.Window> 에 투명도 대 한 합니다.  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 값을 조합하여 사용하면 창이 완전히 투명하게 렌더링됩니다. 이 상태에서는 창의 비클라이언트 영역 표시(닫기 메뉴, 최소화, 최대화 및 복원 단추 등)를 사용할 수 없습니다. 따라서 직접 제공해야 합니다.  
  
<a name="Task_Bar_Presence"></a>   
### <a name="task-bar-presence"></a>작업 표시줄 표시  
 창의 기본 모양에는 다음 그림에서 볼 수 있는 것처럼 작업 표시줄 단추가 포함됩니다.  
  
 ![작업 표시줄 단추가 있는 창](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure7.PNG "WindowOverviewFigure7")  
  
 일부 유형의 windows 메시지 상자 대화 상자 등의 작업 표시줄 단추가 없는 (참조 [대화 상자 개요](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)). 설정 하 여 창의 작업 표시줄 단추가 표시 되는지 여부를 제어할 수 있습니다는 <xref:System.Windows.Window.ShowInTaskbar%2A> 속성 (`true` 기본적으로).  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations"></a>보안 고려 사항  
 <xref:System.Windows.Window> 필요한 `UnmanagedCode` 인스턴스화할 수 있는 보안 권한이 있습니다. 로컬 시스템에 설치되어 실행되는 응용 프로그램의 경우에는 응용 프로그램에 허용된 권한 집합에 속합니다.  
  
 그러나이 벗어난 인터넷 또는 로컬 인트라넷 영역 사용 하 여 실행 응용 프로그램에 부여 된 권한 집합이 [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)]합니다. 사용자가을 받을 따라서는 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 보안 경고의 권한 집합을 완전 신뢰 응용 프로그램을 승격 해야 합니다.  
  
 또한 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 기본적으로 창 또는 대화 상자를 표시할 수 없습니다. 독립 실행형 응용 프로그램에 대 한 보안 고려 사항에 논의 알려면 [WPF 보안 전략-플랫폼 보안](../../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)합니다.  
  
<a name="Other_Types_of_Windows"></a>   
## <a name="other-types-of-windows"></a>다른 유형의 창  
 <xref:System.Windows.Navigation.NavigationWindow> 탐색 가능한 콘텐츠를 호스트 하도록 설계 된 창이입니다. 자세한 내용은 참조 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)).  
  
 대화 상자는 기능 수행을 위해 사용자로부터 정보를 수집할 때 많이 사용됩니다. 예를 들어 사용자가을 경우 파일을 열는 **파일 열기** 대화 상자가 사용자 로부터 파일 이름을 가져올 응용 프로그램에서 일반적으로 표시 됩니다. 자세한 내용은 [대화 상자 개요](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Window>  
 <xref:System.Windows.MessageBox>  
 <xref:System.Windows.Navigation.NavigationWindow>  
 <xref:System.Windows.Application>  
 [대화 상자 개요](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)  
 [WPF 응용 프로그램 빌드](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)
