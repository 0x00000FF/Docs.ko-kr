---
title: '방법: 서명 되지 않은 Friend 어셈블리 (Visual Basic) 만들기'
ms.date: 03/14/2018
ms.assetid: 5735eb79-9729-4c46-ac1f-537ada3acaa7
ms.openlocfilehash: 814c2584ea9e1e14c3af003a0515166f53b6d913
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819387"
---
# <a name="how-to-create-unsigned-friend-assemblies-visual-basic"></a>방법: 서명 되지 않은 Friend 어셈블리 (Visual Basic) 만들기
이 예제에서는 서명되지 않은 어셈블리와 함께 friend 어셈블리를 사용하는 방법을 보여 줍니다.  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a>어셈블리 및 friend 어셈블리를 만들려면  
  
1.  명령 프롬프트를 엽니다.  
  
2.  Visual Basic 파일을 만듭니다 `friend_signed_A.` 다음 코드를 포함 하는 합니다. 코드에서는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성을 사용하여 friend_signed_B를 friend 어셈블리로 선언합니다.  
  
    ```vb  
    ' friend_unsigned_A.vb  
    ' Compile with:   
    ' vbc -target:library friend_unsigned_A.vb  
    Imports System.Runtime.CompilerServices  
    Imports System  
  
    <Assembly: InternalsVisibleTo("friend_unsigned_B")>   
  
    ' Friend type.  
    Friend Class Class1  
        Public Sub Test()  
            Console.WriteLine("Class1.Test")  
        End Sub  
    End Class  
  
    ' Public type with Friend member.  
    Public Class Class2  
        Friend Sub Test()  
            Console.WriteLine("Class2.Test")  
        End Sub  
    End Class  
    ```  
  
3.  다음 명령을 사용하여 friend_signed_A를 컴파일하고 서명합니다.  
  
    ```console  
    vbc -target:library friend_unsigned_A.vb  
    ```  
  
4.  Visual Basic 파일을 만듭니다 `friend_unsigned_B` 다음 코드를 포함 하는 합니다. friend_unsigned_A는 friend_unsigned_B를 friend 어셈블리로 지정하기 때문에 friend_unsigned_B의 코드는 friend_unsigned_A의 `Friend` 형식과 멤버에 액세스할 수 있습니다.  
  
    ```vb  
    ' friend_unsigned_B.vb  
    ' Compile with:   
    ' vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb  
    Module Module1  
        Sub Main()  
            ' Access a Friend type.  
            Dim inst1 As New Class1()  
            inst1.Test()  
  
            Dim inst2 As New Class2()  
            ' Access a Friend member of a public type.  
            inst2.Test()  
  
            System.Console.ReadLine()  
        End Sub  
    End Module  
    ```  
  
5.  다음 명령을 사용하여 friend_signed_B를 컴파일합니다.  
  
    ```console
    vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb  
    ```  
  
     컴파일러에서 생성된 어셈블리 이름은 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성에 전달된 friend 어셈블리 이름과 일치해야 합니다. 사용 하 여 어셈블리를 명시적으로 설정할 수는 `/out` 컴파일러 옵션입니다.  
  
6.  friend_signed_B.exe 파일을 실행합니다.  
  
     프로그램이 두 문자열을 표시합니다. “Class1.Test” 및 “Class2.Test”가 출력됩니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성과 <xref:System.Security.Permissions.StrongNameIdentityPermission> 클래스 간에는 유사점이 있습니다. 주요 차이점은 <xref:System.Security.Permissions.StrongNameIdentityPermission>은 코드의 특정 섹션을 실행하는 보안 권한을 요구할 수 있는 반면, <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성은 `Friend` 형식 및 멤버의 표시 유형을 제어한다는 것입니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [.NET 어셈블리](../../../../standard/assembly/index.md)
- [Friend 어셈블리](../../../../standard/assembly/friend-assemblies.md)
- [방법: 서명 된 Friend 어셈블리 (Visual Basic) 만들기](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [프로그래밍 가이드 개념](../../../../visual-basic/programming-guide/concepts/index.md)
