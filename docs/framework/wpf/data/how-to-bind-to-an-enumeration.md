---
title: '방법: 열거형 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 921f15a32eeb5ccb20e879466fcfee3233bbd29e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554949"
---
# <a name="how-to-bind-to-an-enumeration"></a>방법: 열거형 바인딩
이 예제에서는 열거형의 GetValues 메서드에 바인딩하여 열거형에 바인딩하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Controls.ListBox> 의 목록을 표시 <xref:System.Windows.HorizontalAlignment> 데이터 바인딩을 통해 열거형 값입니다. <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.Button> 변경할 수 있도록 바인딩된는 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 의 속성 값은 <xref:System.Windows.Controls.Button> 에 값을 선택 하 여는 <xref:System.Windows.Controls.ListBox>합니다.  
  
 [!code-xaml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>참고 항목  
 [메서드 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
