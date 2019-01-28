---
title: '방법: 파생 클래스에서 기본 클래스 이벤트 발생 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
ms.openlocfilehash: 6d6e84861ec48be5bccbc050624b0843947cb727
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539866"
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a>방법: 파생 클래스에서 기본 클래스 이벤트 발생(C# 프로그래밍 가이드)
다음 간단한 예제에서는 파생 클래스에서도 발생할 수 있도록 기본 클래스에서 이벤트를 선언하는 표준 방법을 보여 줍니다. 이 패턴은 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 클래스 라이브러리의 Windows Forms 클래스에서 광범위하게 사용됩니다.  
  
 다른 클래스의 기본 클래스로 사용할 수 있는 클래스를 만드는 경우 이벤트가 해당 이벤트를 선언한 클래스 내에서만 호출할 수 있는 특수 유형의 대리자라는 사실을 고려해야 합니다. 파생 클래스는 기본 클래스 내에서 선언된 이벤트를 직접 호출할 수 없습니다. 기본 클래스에서만 발생할 수 있는 이벤트를 원하는 경우도 있지만 대부분의 경우 파생 클래스가 기본 클래스 이벤트를 호출할 수 있도록 해야 합니다. 이렇게 하려면 이벤트를 래핑하는 기본 클래스에서 보호된 호출 메서드를 만듭니다. 이 호출 메서드를 호출하거나 재정의하면 파생 클래스에서 간접적으로 이벤트를 호출할 수 있습니다.  
  
> [!NOTE]
>  기본 클래스에서 가상 이벤트를 선언하지 말고 파생 클래스에서 재정의합니다. C# 컴파일러는 이러한 이벤트를 올바르게 처리하지 않으며, 파생 이벤트의 구독자가 실제로 기본 클래스 이벤트를 구독할지 여부를 예측할 수 없습니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[csProgGuideEvents#1](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-raise-base-class-events-in-derived-classes_1.cs)]  
  
## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)
- [이벤트](../../../csharp/programming-guide/events/index.md)
- [대리자](../../../csharp/programming-guide/delegates/index.md)
- [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
- [Windows Forms에서 이벤트 처리기 만들기](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
