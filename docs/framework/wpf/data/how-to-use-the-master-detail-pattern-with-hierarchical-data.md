---
title: "방법: 계층적 데이터에 마스터-세부 패턴 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e392b47682d1bf53dc31073920bdf212fb7d997
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a>방법: 계층적 데이터에 마스터-세부 패턴 사용
이 예에서는 마스터-세부 시나리오를 구현 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예  
 이 예제에서는 `LeagueList` 의 컬렉션인 `Leagues`합니다. 각 `League` 에 `Name` 의 컬렉션과 `Divisions`, 및 각 `Division` 에 이름 및 컬렉션을 `Teams`합니다. 각 `Team` 팀 이름이 있습니다.  
  
 [!code-xaml[MasterDetail#HowTo1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 예제 스크린샷은 다음과 같습니다. `Divisions` <xref:System.Windows.Controls.ListBox> 선택 항목을 자동으로 추적의 `Leagues` <xref:System.Windows.Controls.ListBox> 해당 데이터를 표시 합니다. `Teams` <xref:System.Windows.Controls.ListBox> 에 다른 두 가지 선택 항목을 추적 <xref:System.Windows.Controls.ListBox> 컨트롤입니다.  
  
 ![마스터 &#45; 세부 예제](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")  
  
 이 예에서 유념 해야 할 두 가지 사항은 다음과 같습니다.  
  
1.  세 개의 <xref:System.Windows.Controls.ListBox> 컨트롤 동일한 소스에 바인딩합니다. 설정한는 <xref:System.Windows.Data.Binding.Path%2A> 데이터 수준을 지정에 대 한 바인딩 속성은 <xref:System.Windows.Controls.ListBox> 표시 합니다.  
  
2.  설정 해야 합니다는 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 속성을 `true` 에 <xref:System.Windows.Controls.ListBox> 컨트롤은 추적 하는 선택 합니다. 이 속성을 설정 하면 선택한 항목은 항상으로 설정 된다는 <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>합니다. 또는 경우는 <xref:System.Windows.Controls.ListBox> 에서 데이터를 가져오는 <xref:System.Windows.Data.CollectionViewSource>, 선택 및 통화 자동으로 동기화 합니다.  
  
 사용 중인 경우 방법이 약간 다릅니다 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터입니다. 예를 들어 참조 [마스터-세부 패턴을 사용 하 여 계층적 XML 데이터로](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [선택에 따라 수집 및 표시 정보에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
