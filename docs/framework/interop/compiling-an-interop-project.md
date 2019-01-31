---
title: Interop 프로젝트 컴파일
ms.date: 03/30/2017
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a1e6ea8a7a7e6869ca9bc6c1b635f30574ac97f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695196"
---
# <a name="compiling-an-interop-project"></a>Interop 프로젝트 컴파일

가져온 COM 형식이 포함된 하나 이상의 어셈블리를 참조하는 COM interop 프로젝트는 다른 관리되는 프로젝트와 마찬가지로 컴파일됩니다. Visual Studio 등의 개발 환경에서 interop 어셈블리를 참조하거나, 명령줄 컴파일러를 사용할 때 참조할 수 있습니다. 두 경우 모두, 제대로 컴파일하려면 interop 어셈블리가 다른 프로젝트 파일과 동일한 디렉터리에 있어야 합니다.

 Interop 어셈블리를 참조하는 방법에는 다음 두 가지가 있습니다.

-   포함 interop 형식: [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 및 Visual Studio 2010부터 interop 어셈블리의 형식 정보를 실행 파일에 포함하도록 컴파일러에 지시할 수 있습니다. 이것이 권장되는 방법입니다.

-   interop 어셈블리 배포: interop 어셈블리에 대한 표준 참조를 만들 수 있습니다. 이 경우 interop 어셈블리를 애플리케이션에 배포해야 합니다.

 이러한 두 방법 간의 차이점은 [관리 코드에서 COM 형식 사용](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))에서 자세히 설명합니다.

 Visual Studio에 interop 형식을 포함하는 방법은 [연습: Microsoft Office 어셈블리의 형식 정보 포함](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100)) 및 [연습: 관리되는 어셈블리의 형식 포함](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)을 참조하세요.

 명령줄 컴파일러를 사용하여 interop 어셈블리를 참조하고 실행 파일에 형식 정보를 포함하려면 [/link(C# 컴파일러 옵션)](../../csharp/language-reference/compiler-options/link-compiler-option.md) 또는 [/link(Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) 컴파일러 스위치를 사용하고 interop 어셈블리의 이름을 지정합니다.

> [!NOTE]
> Visual C++ 애플리케이션은 형식 정보를 포함할 수 없지만 포함하는 애플리케이션이나 추가 기능과 상호 운용할 수 있습니다.

 배포될 때 주 interop 어셈블리를 포함하는 애플리케이션을 컴파일하려면 **/reference** 컴파일러 스위치를 사용하고 interop 어셈블리의 이름을 지정합니다.

## <a name="see-also"></a>참고 항목

- [.NET Framework에 COM 구성 요소 노출](exposing-com-components.md)
- [언어 독립성 및 언어 독립적 구성 요소](../../standard/language-independence-and-language-independent-components.md)
- [관리 코드에서 COM 형식 사용](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))
- [연습: Microsoft Office 어셈블리의 형식 정보 포함](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100))
- [연습: 관리되는 어셈블리의 형식 포함](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)
- [형식 라이브러리를 어셈블리로 가져오기](importing-a-type-library-as-an-assembly.md)