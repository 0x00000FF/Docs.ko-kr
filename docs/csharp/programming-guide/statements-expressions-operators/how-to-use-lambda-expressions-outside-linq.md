---
title: '방법: LINQ 외부에 람다 식 사용(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], outside LINQ
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
ms.openlocfilehash: a7b7d25adab7ce1fc777b3bdbe581666ab952413
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-lambda-expressions-outside-linq-c-programming-guide"></a>방법: LINQ 외부에 람다 식 사용(C# 프로그래밍 가이드)
람다 식은 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리로 제한되지 않습니다. 대리자 값이 필요한 곳, 즉 무명 메서드를 사용할 수 있는 곳이면 어디서나 람다 식을 사용할 수 있습니다. 다음 예제에서는 Windows Forms 이벤트 처리기에 람다 식을 사용하는 방법을 보여 줍니다. 입력 형식(<xref:System.Object> 및 <xref:System.Windows.Forms.MouseEventArgs>)은 컴파일러에서 유추되며 람다 입력 매개 변수에서 명시적으로 지정되지 않아도 됩니다.  
  
## <a name="example"></a>예  
  
```  
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
        // Use a lambda expression to define an event handler.  
       this.Click += (s, e) => { MessageBox.Show(((MouseEventArgs)e).Location.ToString());};  
    }  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
 [무명 메서드](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
 [LINQ(Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)
