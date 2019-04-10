---
title: UI 자동화를 사용하여 텍스트 상자에 콘텐츠 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
ms.openlocfilehash: 9183aecdc47d54aef26d5cdca8ea11d8398be732
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226510"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a>UI 자동화를 사용하여 텍스트 상자에 콘텐츠 추가
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. 에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]를 참조 하세요 [Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746)합니다.  
  
 이 항목에 사용 하는 방법을 보여 주는 예제 코드가 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 한 줄 텍스트 상자에 텍스트를 삽입 합니다. 여러 줄 및 서식 있는 텍스트 컨트롤에 대 한 대체 방법을 제공 됩니다 여기서 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 적용 되지 않습니다. 비교를 위해이 예제에서는 동일한 결과 위해 Win32 메서드를 사용 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 대상 응용 프로그램에서 텍스트 컨트롤의 시퀀스에서 다음 예제. 각 텍스트 컨트롤을 하는지 테스트를 <xref:System.Windows.Automation.ValuePattern> 를 사용 하 여 개체를 얻을 수를 <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> 메서드. 텍스트 컨트롤에서 지원 <xref:System.Windows.Automation.ValuePattern>, <xref:System.Windows.Automation.ValuePattern.SetValue%2A> 메서드 사용 하 여 텍스트 컨트롤에 사용자 정의 문자열을 삽입 합니다. 그렇지 않은 경우는 <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> 메서드를 사용 합니다.  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a>참고자료

- [TextPattern Insert 텍스트 샘플](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))
