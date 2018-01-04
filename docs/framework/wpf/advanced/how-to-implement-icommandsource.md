---
title: "방법: ICommandSource 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d82a211f59fbdecdc932b7e57b242274e91cd5b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-icommandsource"></a>방법: ICommandSource 구현
구현 하 여 명령 소스를 만드는 방법을 보여 주는이 예제 <xref:System.Windows.Input.ICommandSource>합니다.  명령 소스는 명령을 호출 하는 방법을 알고 있는 개체입니다.  <xref:System.Windows.Input.ICommandSource> 세 멤버를 노출 하는 인터페이스: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>, 및 <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>합니다.  <xref:System.Windows.Input.ICommandSource.Command%2A>호출 되는 명령이입니다. <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> 명령 소스 명령을 처리 하는 메서드에 전달 되는 사용자 정의 데이터 형식입니다. <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> 명령이 실행 되는 개체입니다.  
  
 이 예제에서는 클래스가 만들어질 서브클래싱하는 <xref:System.Windows.Controls.Slider> 컨트롤과 구현 <xref:System.Windows.Input.ICommandSource>합니다.  
  
## <a name="example"></a>예  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]다양 한 구현 하는 클래스를 제공 <xref:System.Windows.Input.ICommandSource>와 같은 <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, 및 <xref:System.Windows.Controls.ListBoxItem>합니다.  명령 소스가 명령을 호출 하는 방법을 정의 합니다.   <xref:System.Windows.Controls.Button>및 <xref:System.Windows.Controls.MenuItem> 명령을 클릭할 때 호출 합니다.  A <xref:System.Windows.Controls.ListBoxItem> 명령을 두 번 클릭할 때 호출 합니다. 이러한 클래스에만 명령이 될 때 원본 자신의 <xref:System.Windows.Input.ICommandSource.Command%2A> 속성을 설정 합니다.  
  
 슬라이더를 이동 하면 명령을 호출이 예제에 대 한 더 정확 하 게 때는 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 속성을 변경 합니다.  
  
 다음은 클래스 정의 합니다.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]  
  
 다음 단계를 구현 하는 것은 <xref:System.Windows.Input.ICommandSource> 멤버입니다.  이 예제에서는 속성으로 구현 됩니다 <xref:System.Windows.DependencyProperty> 개체입니다.  이렇게 하면 데이터 바인딩을 사용 하 여 속성.  에 대 한 자세한 내용은 <xref:System.Windows.DependencyProperty> 클래스를 참조 하십시오.는 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)합니다.  데이터 바인딩에 대 한 자세한 내용은 참조는 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)합니다.  
  
 만 <xref:System.Windows.Input.ICommandSource.Command%2A> 속성은 같습니다.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
 다음은는 <xref:System.Windows.DependencyProperty> 콜백 변경 합니다.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]  
  
 다음 단계를 추가 및 제거 명령 소스와 연결 되는 명령입니다.  <xref:System.Windows.Input.ICommandSource.Command%2A> 속성 단순히 덮어쓸 수 없는 새 명령을 추가 되 면 이전 명령과 사용 하 여 이벤트 처리기 연결 되었기 때문에 하나만 있는 경우, 먼저 제거 해야 합니다.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]  
  
 마지막 단계에 대 한 논리를 만드는 것은 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 처리기 및 <xref:System.Windows.Input.ICommand.Execute%2A> 메서드.  
  
 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 이벤트의 현재 명령 대상에서 실행할 명령 기능이 변경 될 수 있습니다 명령 소스를에 알립니다.  일반적으로 호출 명령 소스가이 이벤트를 받을 경우는 <xref:System.Windows.Input.ICommand.CanExecute%2A> 명령에는 메서드.  현재 명령 대상에서 명령을 실행할 수 없습니다, 명령 소스가 일반적으로 비활성화 됩니다.  현재 명령 대상에서 명령을 실행할 수, 하는 경우 명령 소스는 일반적으로 자체으로 활성화 됩니다.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]  
  
 마지막 단계는 <xref:System.Windows.Input.ICommand.Execute%2A> 메서드.  명령이 있는 경우는 <xref:System.Windows.Input.RoutedCommand>, <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> 메서드 호출, 되지 않았으면는 <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> 메서드를 호출 합니다.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
 [!code-vb[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Input.ICommandSource>  
 <xref:System.Windows.Input.ICommand>  
 <xref:System.Windows.Input.RoutedCommand>  
 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)
