---
title: "방법: foreach를 사용하여 명령줄 인수 액세스(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 557e72342901fab8bbe66e9cc3405cb4b2d9c1e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a>방법: foreach를 사용하여 명령줄 인수 액세스(C# 프로그래밍 가이드)
배열을 반복하는 또 다른 방법은 이 예제에 표시된 대로 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 문을 사용하는 것입니다. `foreach` 문은 배열, .NET Framework 컬렉션 클래스 또는 <xref:System.Collections.IEnumerable> 인터페이스를 구현하는 임의의 클래스나 구조체를 반복하는 데 사용할 수 있습니다.  
  
> [!NOTE]
>  Visual Studio에서 응용 프로그램을 실행할 경우 [프로젝트 디자이너, 디버그 페이지](/visualstudio/ide/reference/debug-page-project-designer)에서 명령줄 인수를 지정할 수 있습니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `foreach`를 사용하여 명령줄을 출력하는 방법을 보여 줍니다.  
  
 [!code-csharp[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]  
  
 [!code-csharp[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Array>  
 <xref:System.Collections>  
 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)  
 [Main()과 명령줄 인수](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [방법: 명령줄 인수 표시](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
 [Main() 반환 값](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
