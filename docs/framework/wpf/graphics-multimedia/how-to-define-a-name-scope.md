---
title: "방법: 이름 범위 정의"
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
helpviewer_keywords:
- name scope [WPF], defining
- Storyboards [WPF], animating in procedural code
- animation [WPF], Storyboards [WPF], in procedural code
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3007088f849f40e4e9b4f1846c19c98c33e95c17
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-name-scope"></a>방법: 이름 범위 정의
로 애니메이션 효과를 <xref:System.Windows.Media.Animation.Storyboard> 코드를 만들어야 합니다는 <xref:System.Windows.NameScope> 하 고 해당 이름 범위를 소유 하는 요소는 대상 개체의 이름을 등록 합니다. 다음 예제에서는 <xref:System.Windows.NameScope> 만들어집니다 `myMainPanel`합니다. 두 개의 단추 `button1` 및 `button2`, 패널과 이름을 등록에 추가 됩니다. 여러 개의 애니메이션 및 <xref:System.Windows.Media.Animation.Storyboard> 만들어집니다. 스토리 보드의 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드는 애니메이션을 시작 하는 데 사용 됩니다.  
  
 때문에 `button1`, `button2`, 및 `myMainPanel` 동일한 이름 범위를 공유 하는 모든, 그 중 하나를 사용할 수 있습니다는 <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 애니메이션을 시작 합니다.  
  
## <a name="example"></a>예  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## <a name="see-also"></a>참고 항목  
 [Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
