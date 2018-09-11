---
title: 목록 항목의 UI 자동화 요소 찾기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: b569b43d83e8a7f1b0fa82b79bc1fc40977b72ba
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2018
ms.locfileid: "44364769"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a>목록 항목의 UI 자동화 요소 찾기
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. 에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]를 참조 하세요 [Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746)합니다.  
  
 이 항목에서는 검색 하는 방법을 보여 줍니다.는 <xref:System.Windows.Automation.AutomationElement> 항목의 인덱스 라고 하는 경우 목록 내의 항목에 대 한 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 지정 된 항목을 사용 하 여 목록에서 검색 하는 두 가지 <xref:System.Windows.Automation.TreeWalker> 및 다른 사용 <xref:System.Windows.Automation.AutomationElement.FindAll%2A>합니다.  
  
 첫 번째 방법은 대 한 더 빠른 경향이 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 컨트롤 이지만 두 번째 Windows Presentation Foundation (WPF) 컨트롤에 대 한 더 빠릅니다.  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a>참고 항목  
 [UI 자동화 요소 가져오기](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
