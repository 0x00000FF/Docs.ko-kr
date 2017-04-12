---
title: "방법: 명령줄 (Visual Basic)를 사용 하 여 어셈블리 만들기 및 사용 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 363bca806736e5540165ea96e9b4fe60d0968098
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a>방법: 명령줄 (Visual Basic)를 사용 하 여 어셈블리 만들기 및 사용
어셈블리 또는 동적 연결 라이브러리 (DLL)는 런타임 시 프로그램에 연결 됩니다. 빌드 및 DLL 사용을 보여 주기 위해 다음 시나리오를 고려 합니다.  
  
-   `MathLibrary.DLL`런타임 시 호출 되는 메서드가 포함 된: 라이브러리 파일입니다. 이 예제에서는 DLL 포함, 두 메서드는 `Add` 및 `Multiply`합니다.  
  
-   `Add`메서드를 포함 하는 소스 파일: `Add`합니다. 해당 매개 변수의 합계를 반환합니다. 클래스 `AddClass` 메서드가 있는 `Add` 네임 스페이스의 멤버인 `UtilityMethods`합니다.  
  
-   `Mult`메서드를 포함 하는 소스 코드: `Multiply`합니다. 매개 변수의 곱을 반환합니다. 클래스 `MultiplyClass` 메서드가 있는 `Multiply` 네임 스페이스의 멤버 이기도 `UtilityMethods`합니다.  
  
-   `TestCode`: 포함 된 파일은 `Main` 메서드. 합계 및 제품의 런타임 인수를 계산 하는 DLL 파일의 메서드 사용 합니다.  
  
## <a name="example"></a>예제  
  
```vb  
' File: Add.vb   
Namespace UtilityMethods  
    Public Class AddClass  
        Public Shared Function Add(ByVal i As Long, ByVal j As Long) As Long  
            Return i + j  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: Mult.vb  
Namespace UtilityMethods  
    Public Class MultiplyClass  
        Public Shared Function Multiply(ByVal x As Long, ByVal y As Long) As Long  
            Return x * y  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: TestCode.vb  
  
Imports UtilityMethods  
  
Module Test  
  
    Sub Main(ByVal args As String())  
  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:")  
  
        If args.Length <> 2 Then  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>")  
            Return  
        End If  
  
        Dim num1 As Long = Long.Parse(args(0))  
        Dim num2 As Long = Long.Parse(args(1))  
  
        Dim sum As Long = AddClass.Add(num1, num2)  
        Dim product As Long = MultiplyClass.Multiply(num1, num2)  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum)  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product)  
  
    End Sub  
  
End Module  
  
' Output (assuming 1234 and 5678 are entered as command-line arguments):  
' Calling methods from MathLibrary.DLL:  
' 1234 + 5678 = 6912  
' 1234 * 5678 = 7006652  
```  
  
 이 파일에 DLL 메서드를 사용 하는 알고리즘 `Add` 및 `Multiply`합니다. 명령줄에 입력 된 구문 분석 `num1` 및 `num2`합니다. 사용 하 여 합계를 계산한 다음는 `Add` 메서드를는 `AddClass` 클래스 및 사용 하 여 제품의 `Multiply` 메서드를는 `MultiplyClass` 클래스입니다.  
  
 다음에 유의 `Imports` 파일의 시작 부분에 문을 컴파일할 때 DLL 메서드를 다음과 같이 참조를 정규화 되지 않은 클래스 이름을 사용할 수 있습니다.  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 그렇지 않은 경우 다음과 같이 정규화 된 이름을 사용 해야 합니다.  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a>실행  
 프로그램을 실행 하려면 다음과 같이 두 개의 숫자를 다음 EXE 파일의 이름을 입력 합니다.  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 파일을 빌드하려면 `MathLibrary.DLL`, 두 개의 파일을 컴파일할 `Add` 및 `Mult` 다음 명령줄을 사용 하 여 합니다.  
  
```vb  
vbc /target:library /out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 [/target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) 컴파일러 옵션 EXE 파일 대신 DLL을 출력 하도록 지시 합니다. [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) 파일 이름이 옵니다 컴파일러 옵션은 DLL 파일 이름을 지정 하는 데 사용 됩니다. 컴파일러는 첫 번째 파일을 사용 하는 그렇지 않은 경우 (`Add.vb`) DLL의 이름으로 합니다.  
  
 실행 파일을 빌드합니다 `TestCode.exe`, 다음 명령줄을 사용 합니다.  
  
```vb  
vbc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.vb  
```  
  
 **/출력** 컴파일러 옵션 EXE 파일을 출력 하도록 컴파일러에 지시 하 고 출력 파일의 이름을 지정 합니다 (`TestCode.exe`). 이 컴파일러 옵션은 선택 사항입니다. [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) 컴파일러 옵션에이 프로그램을 사용 하는 DLL 파일을 지정 합니다.  
  
 명령줄에서 빌드에 대 한 자세한 내용은 참조 및 [명령줄에서 빌드](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그래밍 개념](../../../../visual-basic/programming-guide/concepts/index.md)   
 [어셈블리 및 전역 어셈블리 캐시 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [DLL 함수가 포함 된 클래스 만들기](http://msdn.microsoft.com/library/e08e4c34-0223-45f7-aa55-a3d8dd979b0f)
