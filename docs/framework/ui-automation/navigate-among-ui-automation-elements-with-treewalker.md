---
title: TreeWalker를 사용하여 UI 자동화 요소 간 탐색
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, TreeWalker
- TreeWalker class
- elements, navigating among
- UI Automation, navigating among elements
ms.assetid: afcd21dc-2ffa-48c9-9332-51269f44b7e9
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 6a44cd16513bffa47e56064ea7e0e05692cb78a7
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2018
ms.locfileid: "45676748"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a>TreeWalker를 사용하여 UI 자동화 요소 간 탐색
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. 에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]를 참조 하세요 [Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746)합니다.  
  
 이 항목 간에 이동 하는 방법을 보여 주는 예제 코드가 포함 되어 있습니다 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 를 사용 하 여 요소를 <xref:System.Windows.Automation.TreeWalker> 클래스입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Automation.TreeWalker.GetParent%2A> 를 탐색 하려면는 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 트리 루트 요소 또는 데스크톱을 찾습니다. 바로 아래에 있는 요소에 지정 된 요소의 부모 창입니다.  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> 하 고 <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> 만들려면를 <xref:System.Windows.Forms.TreeView> 의 전체 하위 트리를 보여 주는 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 컨트롤 보기에 있는 요소입니다.  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a>참고 항목  
 [UI 자동화 요소 가져오기](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
