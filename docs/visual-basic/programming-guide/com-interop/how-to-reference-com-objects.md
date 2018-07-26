---
title: '방법: Visual Basic에서 COM 개체 참조'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
ms.openlocfilehash: 49f3da396ca5cd48b0cf454ce1ecd5422c28e38f
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39199367"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>방법: Visual Basic에서 COM 개체 참조
Visual basic의 경우 형식 라이브러리가 포함 된 COM 개체에 대 한 참조를 추가 합니다. COM 라이브러리에 대 한 interop 어셈블리를 만들이 필요 합니다. COM 개체의 멤버에 대 한 참조는 interop 어셈블리에 라우팅되어 실제 COM 개체에 전달 됩니다. Interop 어셈블리에 COM 개체의 응답은 라우팅되고 전달할 프로그램 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 응용 프로그램입니다.  
  
 .NET 어셈블리에 COM 개체에 대 한 형식 정보를 포함 하 여 interop 어셈블리를 사용 하지 않고 COM 개체를 참조할 수 있습니다. 형식 정보를 포함 하려면 설정 합니다 `Embed Interop Types` 속성을 `True` COM 개체에 대 한 참조에 대 한 합니다. 명령줄 컴파일러를 사용 하 여 컴파일할 경우 사용 된 `/link` COM 라이브러리를 참조 하는 옵션입니다. 자세한 내용은 [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md)합니다.  
  
 통합된 개발 환경 (IDE)에서 형식 라이브러리에 대 한 참조를 추가 하면 Visual Basic interop 어셈블리를 자동으로 만듭니다. 명령줄에서 작업을 하는 경우 interop 어셈블리를 수동으로 만들려면 Tlbimp 유틸리티를 사용할 수 있습니다.  
  
### <a name="to-add-references-to-com-objects"></a>COM 개체에 대 한 참조를 추가 하려면  
  
1.  에 **프로젝트** 메뉴 선택 **참조 추가** 클릭 하 고는 **COM** 대화 상자에서 탭 합니다.  
  
2.  COM 개체의 목록에서 사용 하려는 구성 요소를 선택 합니다.  
  
3.  Interop 어셈블리에 대 한 액세스를 간소화 하려면 추가 `Imports` 문을 클래스 또는는 COM 개체를 사용 하는 모듈의 맨 위로 이동 합니다. 예를 들어, 다음 코드 예제에서는 네임 스페이스를 가져옵니다 `INKEDLib` 에서 참조 되는 개체는 `Microsoft InkEdit Control 1.0` 라이브러리입니다.  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a>Tlbimp를 사용 하 여 interop 어셈블리를 만들려면  
  
1.  이미 속하지 않는의 검색 경로 및 현재 위치한 디렉터리 하지 않는 경우 검색 경로에 Tlbimp의 위치를 추가 합니다.  
  
2.  다음 정보를 제공 하는 명령 프롬프트에서 Tlbimp를 호출 합니다.  
  
    -   형식 라이브러리를 포함 하는 DLL의 이름 및 위치  
  
    -   이름 및 네임 스페이스 정보를 배치할 위치  
  
    -   대상 interop 어셈블리의 이름 및 위치  
  
     다음 코드는 예제를 제공합니다.  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     Tlbimp를 사용 하 여 등록 되지 않은 COM 개체에 대해서도 형식 라이브러리에 대 한 interop 어셈블리를 만들 수 있습니다. 그러나 COM 개체에서 interop 어셈블리 참조 되는 데 사용할 컴퓨터에 제대로 등록 되어야 합니다. Windows 운영 체제에 포함 된 Regsvr32 유틸리티를 사용 하 여 COM 개체를 등록할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Tlbimp.exe(형식 라이브러리 가져오기)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [Tlbexp.exe(형식 라이브러리 내보내기)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [연습: COM 개체를 사용한 상속 구현](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [상호 운용성 문제 해결](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [Imports 문(.NET 네임스페이스 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
