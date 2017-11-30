---
title: "상호 운용성 문제 해결(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interop, deploying assemblies
- assemblies [Visual Basic]
- interop, installing assemblies that share components
- COM objects, troubleshooting
- interop, sharing components
- troubleshooting interoperability [Visual Basic]
- interoperability, troubleshooting
- COM interop [Visual Basic], troubleshooting
- assemblies [Visual Basic], deploying
- troubleshooting Visual Basic, interoperability
- interop assemblies
- interoperability, sharing components
- shared components, using with assemblies
ms.assetid: b324cc1e-b03c-4f39-aea6-6a6d5bfd0e37
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 988d07fe08a6a78ae295d13f694c55a3b8f9d2e4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-interoperability-visual-basic"></a>상호 운용성 문제 해결(Visual Basic)
COM과의 관리 코드 상호 운용할 때는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], 다음과 같은 일반적인 문제 중 하나 이상을 발생할 수 있습니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor1"></a>Interop 마샬링  
 되지 않는 데이터 형식을 사용 해야 하는 시간에 속하지는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]합니다. Interop 어셈블리가 대부분의 COM 개체에 대 한 작업을 처리 하지만 관리 되는 개체는 COM에 노출 하는 경우 사용 되는 데이터 형식을 제어 해야 할 수 있습니다. 예를 들어 클래스 라이브러리의 구조 지정 해야 합니다는 `BStr` 관리 되지 않은 형식에서 Visual Basic 6.0 및 이전 버전에서 만든 COM 개체로 전송 되는 문자열입니다. 이러한 경우에 사용할 수 있습니다는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 관리 되는 형식을 관리 되지 않는 형식으로 노출 되어야 합니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor2"></a>고정 길이 문자열 비관리 코드 내보내기  
 Visual Basic 6.0 및 이전 버전에서 문자열은 null 종결 문자 없이 바이트 시퀀스도 COM 개체에 내보내집니다. 다른 언어와 호환성을 위해 문자열을 내보낼 때 Visual Basic.NET 종결 문자를 포함 합니다. 이 호환성 문제를 해결 하는 가장 좋은 방법은 배열의 종결 문자가 없는 문자열을 내보내려면 `Byte` 또는 `Char`합니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor3"></a>상속 계층 구조 내보내기  
 클래스는 COM 개체로 노출 될 때 계층 결합을 관리 합니다. 예를 들어, 멤버를 사용한 기본 클래스를 정의한 다음 기본 클래스를 COM 개체로 노출 되는 파생된 클래스에서 상속 하는 경우 COM 개체에서 파생된 된 클래스를 사용 하는 클라이언트는 상속 된 멤버를 사용할 수 없습니다. 기본 클래스 멤버는 기본 클래스의 인스턴스로 서만 COM 개체에서 액세스할 수 있습니다 다음 기본 클래스는 COM 개체로 생성 하는 경우에 합니다.  
  
## <a name="overloaded-methods"></a>오버로드된 메서드  
 오버 로드 된 메서드를 만들 수는 있지만 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], com 지원 되지 않습니다 오버 로드 된 메서드를 포함 하는 클래스를 COM 개체로 노출 되는 오버 로드 된 메서드에 대 한 새 메서드 이름이 생성 됩니다.  
  
 예를 들어 두 개의 오버 로드가 있는 클래스는 `Synch` 메서드. 새로 생성 된 메서드 이름이 될 수는 클래스를 COM 개체로 노출 되는 경우 `Synch` 및 `Synch_2`합니다.  
  
 이름 바꾸기 COM 개체의 소비자에 대 한 두 가지 문제가 발생할 수 있습니다.  
  
1.  클라이언트에서 생성 된 메서드 이름을 예측할 수 없습니다.  
  
2.  새 오버 로드는 클래스 또는 해당 기본 클래스에 추가 될 때 COM 개체로 노출 클래스에서 생성 된 메서드 이름을 변경할 수 있습니다. 이 버전 관리 문제가 발생할 수 있습니다.  
  
 두 가지 문제를 해결 하기 위해 각 메서드에 오버 로딩을 COM 개체로 노출 하는 개체를 개발할 때 사용 하는 대신 고유 이름을 제공 합니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor4"></a>Interop 어셈블리를 통해 COM 개체 사용  
 나타내는 COM 개체에 대 한 관리 코드 대체는 마치 거의 interop 어셈블리를 사용 합니다. 그러나 래퍼 및 실제로 COM 개체 이므로, interop 어셈블리와 표준 어셈블리를 사용 하 여 몇 가지 차이점은 합니다. 클래스 및 매개 변수 및 반환 값에 대 한 데이터 형식을 노출을 포함 하는 차이점을이 보입니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor5"></a>두 인터페이스 모두으로 노출 하는 클래스 및 클래스  
 표준 어셈블리의 클래스와 달리 COM 클래스는 인터페이스 및 COM 클래스를 나타내는 클래스를 둘 다로 interop 어셈블리에 노출 됩니다. 인터페이스의 이름이 COM 클래스의 동일 합니다. Interop 클래스의 이름은 원래 COM 클래스의와 동일 하지만 "Class" 라는 단어가 있는 추가 합니다. 예를 들어, COM 개체에 대 한 interop 어셈블리에 대 한 참조를 사용 하 여 프로젝트를 있다고 가정 합니다. COM 클래스의 이름이 `MyComClass`, IntelliSense 및 개체 브라우저 표시 이라는 인터페이스 `MyComClass` 라는 클래스 및 `MyComClassClass`합니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor6"></a>.NET Framework 클래스의 인스턴스 만들기  
 인스턴스를 만들 일반적으로 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 클래스 사용의 `New` 클래스 이름으로 문을 합니다. Interop 어셈블리를 나타내는 COM 클래스 사용은 사용할 수 있는 한 가지 경우는 `New` 인터페이스를 사용 하 여 문을 합니다. 사용 하 여 COM 클래스를 사용 하는 경우는 `Inherits` 문을 클래스와 마찬가지로 인터페이스를 사용할 수 있습니다. 다음 코드를 만드는 방법을 보여는 `Command` Microsoft ActiveX 데이터 개체 2.8 라이브러리 COM 개체에 대 한 참조가 있는 프로젝트의 개체:  
  
 [!code-vb[VbVbalrInterop#20](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_1.vb)]  
  
 그러나 파생된 클래스에 대 한 기반으로 COM 클래스를 사용 하는 경우 다음 코드 에서처럼 COM 클래스를 나타내는 interop 클래스를 사용 해야 합니다.  
  
 [!code-vb[VbVbalrInterop#21](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_2.vb)]  
  
> [!NOTE]
>  Interop 어셈블리는 암시적으로 COM 클래스를 나타내는 인터페이스를 구현 합니다. 사용 하려고 하면는 `Implements` 오류가 또는 이러한 인터페이스를 구현 하는 문을 발생 합니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor7"></a>매개 변수 및 반환 값에 대 한 데이터 형식  
 를 표준 어셈블리의 멤버와는 달리 interop 어셈블리 멤버에는 원래 개체 선언에 사용 된 것과 다른 데이터 형식을 사용할 수 있습니다. Interop 어셈블리는 호환 공용 언어 런타임 형식에 COM 형식을 암시적으로 변환, 하더라도 런타임 오류를 방지 하려면 양쪽 모두에서 사용 되는 데이터 형식에는 주의 기울여야 합니다. 예를 들어 Visual Basic 6.0 및 이전 버전에서는 형식의 값에서 생성 된 COM 개체에서에서 `Integer` 가정은 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 해당 하는 형식을 `Short`합니다. 개체 브라우저를 사용 하 여 사용 하기 전에 가져온된 멤버의 특성을 검토 하는 것이 좋습니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor8"></a>모듈 수준 COM 메서드  
 대부분 COM 개체를 사용 하 여 사용 하 여 COM 클래스의 인스턴스를 만들어는 `New` 키워드와 다음 개체의 메서드를 호출 합니다. 이 규칙의 한 가지 예외를 포함 하는 COM 개체를 포함 `AppObj` 또는 `GlobalMultiUse` COM 클래스입니다. 이러한 클래스와 Visual Basic.NET 클래스의 모듈 수준 메서드와를 비슷합니다. Visual Basic 6.0 및 이전 버전 암시적으로 만들 이러한 개체의 인스턴스 수의 메서드 중 하나를 호출 하는 처음으로 합니다. 예를 들어 Visual Basic 6.0에서 추가할 수 있습니다는 Microsoft DAO 3.6 개체 라이브러리와 호출에 대 한 참조는 `DBEngine` 첫 번째 인스턴스를 만들지 않고 메서드:  
  
```vb  
Dim db As DAO.Database  
' Open the database.  
Set db = DBEngine.OpenDatabase("C:\nwind.mdb")  
' Use the database object.  
```  
  
 Visual Basic.NET에서는 항상 만들어야 COM 개체의 인스턴스 해당 메서드를 사용할 수 있습니다. Visual Basic에서 이러한 메서드를 사용 하려면 원하는 클래스의 변수를 선언 하 고 새 키워드를 사용 하 여 개체 변수에 개체를 할당 합니다. `Shared` 있는지 확인 하려는 경우에 키워드를 사용할 수 있습니다는 클래스의 인스턴스를 하나만 생성 됩니다.  
  
 [!code-vb[VbVbalrInterop#23](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_3.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor9"></a>이벤트 처리기에서 처리 되지 않은 오류  
 한 가지 공통적인 interop 문제는 COM 개체에서 발생 한 이벤트를 처리 하는 이벤트 처리기에 오류가 포함 됩니다. 구체적으로 사용 하 여 오류에 대 한 확인 되지 않으면 이러한 오류가 무시 됩니다 `On Error` 또는 `Try...Catch...Finally` 문. 예를 들어 다음 예제에서는 Microsoft ActiveX 데이터 개체 2.8 라이브러리 COM 개체에 대 한 참조가 있는 Visual Basic.NET 프로젝트에서입니다.  
  
 [!code-vb[VbVbalrInterop#24](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_4.vb)]  
  
 이 예제에서는 예상 대로 오류가 발생 합니다. 그러나 없이 동일한 예제를 실행 하는 경우는 `Try...Catch...Finally` 사용한 경우 처럼 블록, 오류는 무시 됩니다는 `OnError Resume Next` 문. 오류 처리 하지 않을 경우 0으로 나누기는 자동으로 실패 합니다. 되기 때문에 이러한 오류가 처리 되지 않은 예외가 오류 발생 시 키, 특정 형태의 COM 개체에서 이벤트를 처리 하는 이벤트 처리기에서 예외 처리를 사용 하는 것이 중요 합니다.  
  
### <a name="understanding-com-interop-errors"></a>COM interop 오류 이해  
 오류를 처리 하지 interop 호출 종종 적은 양의 정보를 제공 하는 오류를 생성 합니다. 가능 하면 항상 구조적된 오류 발생 시 문제에 대 한 자세한 정보를 제공 하는 처리를 사용 합니다. 이 응용 프로그램을 디버깅 하는 경우에 특히 유용 합니다. 예:  
  
 [!code-vb[VbVbalrInterop#25](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_5.vb)]  
  
 예외 개체의 내용을 검사 하 여 오류 설명, HRESULT 및 COM 오류의 출처와 같은 정보를 찾을 수 있습니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor10"></a>ActiveX 컨트롤 문제  
 Visual Basic 6.0을 사용 하는 대부분의 ActiveX 컨트롤 Visual Basic.NET과 함께 문제 없이 작동 합니다. 중요 한 예외는 컨테이너 컨트롤 또는 다른 컨트롤을 시각적으로 포함 하는 컨트롤입니다. 이전 버전에서 올바르게 작동 하지 않는 컨트롤의 몇 가지 예 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 은 다음과 같습니다.  
  
-   Microsoft Forms 2.0 프레임 제어  
  
-   Up-down 컨트롤을 라고도 spin 컨트롤  
  
-   Sheridan 탭 컨트롤  
  
 지원 되지 않는 ActiveX 컨트롤 문제에 대 한 몇 가지 대안만 있습니다. 에 기존 컨트롤을 마이그레이션할 수 있습니다 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 원래 소스 코드를 소유 하는 경우. 그렇지 않은 경우 업데이트에 대 한 소프트웨어 공급 업체에 확인할 수 있습니다. NET 호환 버전을 대체 하는 컨트롤의 ActiveX 컨트롤을 지원 되지 않습니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor11"></a>ByRef 컨트롤의 읽기 전용 속성에 전달  
 Visual Basic.NET "오류 0x800A017F CTL_E_SETNOTSUPPORTED"와 같은 COM 오류를 전달 하는 경우 때로는 발생 `ReadOnly` 으로 오래 된 일부 ActiveX 컨트롤의 속성 `ByRef` 다른 프로시저에 매개 변수입니다. Visual Basic 6.0에서 유사한 프로시저 호출에서 오류가 발생 하지 않습니다 및 매개 변수는 값으로 전달 된 것 처럼 처리 됩니다. Visual Basic.NET 오류 메시지 표시 속성 하지 않은 속성을 변경 하려는 `Set` 프로시저입니다.  
  
 호출 되는 프로시저에 대 한 액세스를 사용 하는 경우 사용 하 여이 오류를 방지할 수 있습니다는 `ByVal` 키워드를 허용 하는 매개 변수를 선언 `ReadOnly` 속성입니다. 예:  
  
 [!code-vb[VbVbalrInterop#26](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_6.vb)]  
  
 호출 되는 프로시저에 대 한 소스 코드에 액세스할 수 없는 경우에 속성을 호출 하는 프로시저 주위에 대괄호를 추가 하 여 값으로 전달 되도록 강제할 수 있습니다. 예를 들어 Microsoft ActiveX 데이터 개체 2.8 라이브러리 COM 개체에 대 한 참조가 있는 프로젝트에서 사용할 수 있습니다.  
  
 [!code-vb[VbVbalrInterop#27](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_7.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor12"></a>Interop을 노출 하는 어셈블리 배포  
 몇 가지 고유한 문제가 표시 COM 인터페이스를 노출 하는 어셈블리를 배포 합니다. 예를 들어 별도 응용 프로그램에서는 동일한 COM 어셈블리 참조는 잠재적인 문제가 발생 합니다. 이 경우가 어셈블리의 새 버전을 설치 하 고 다른 응용 프로그램은 이전 버전의 어셈블리를 사용 하 여 여전히 일반적입니다. DLL을 공유 하는 어셈블리를 제거 하는 경우 있습니다 수 하지 못할 다른 어셈블리에 있습니다.  
  
 이 문제를 방지 하려면 공유 어셈블리를 전역 어셈블리 캐시 (GAC)에 설치 하 고 구성 요소에 대 한 MergeModule을 사용 해야 합니다. GAC에 응용 프로그램을 설치할 수 없으면, CommonFilesFolder를 버전별 하위 디렉터리에 설치 되어야 합니다.  
  
 공유 되지 않는 어셈블리 호출 응용 프로그램을 사용 하 여 디렉터리에 함께 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Tlbimp.exe(형식 라이브러리 가져오기)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)  
 [Tlbexp.exe(형식 라이브러리 내보내기)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [연습: COM 개체를 사용한 상속 구현](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [Inherits 문](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [전역 어셈블리 캐시](../../../framework/app-domains/gac.md)
