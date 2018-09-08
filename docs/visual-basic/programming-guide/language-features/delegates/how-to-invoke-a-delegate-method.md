---
title: '방법: 대리자 메서드 호출(Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: c50a32d300aaf52efe0c55cef69d5793a98305ac
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44204608"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>방법: 대리자 메서드 호출(Visual Basic)
이 예제에서는 대리자를 사용 하 여 메서드를 연결할 대리자를 통해 해당 메서드를 호출 하는 방법을 보여 줍니다.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>대리자 및 일치 하는 프로시저 만들기  
  
1.  명명 된 대리자를 만드는 `MySubDelegate`합니다.  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  대리자와 동일한 시그니처가 있는 메서드를 포함 하는 클래스를 선언 합니다.  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  대리자의 인스턴스를 만들고 기본 제공을 호출 하 여 대리자를 사용 하 여 연결 된 메서드를 호출 하는 메서드를 정의 `Invoke` 메서드.  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a>참고자료

- [Delegate 문](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
- [대리자](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
- [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)  
- [다중 스레드 응용 프로그램](../../../../standard/threading/using-threads-and-threading.md)
