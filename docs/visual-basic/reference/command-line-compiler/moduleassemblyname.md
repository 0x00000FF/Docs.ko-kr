---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 92fd068ef0ff892c8b76396edbf1d532a36e338c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2018
ms.locfileid: "50189513"
---
# <a name="-moduleassemblyname"></a>-moduleassemblyname
이 모듈이 속할 어셈블리의 이름을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`assembly_name`|이 모듈에 포함 될 어셈블리의 이름입니다.|  
  
## <a name="remarks"></a>설명  
 컴파일러 프로세스를 `-moduleassemblyname` 경우에만 옵션을 `-target:module` 옵션이 지정 되었습니다. 이렇게 하면 컴파일러는 모듈을 만듭니다. 컴파일러에서 생성 된 모듈은 지정 된 어셈블리에만 유효 합니다 `-moduleassemblyname` 옵션입니다. 다른 어셈블리에 모듈을 배치 하는 경우 런타임 오류가 발생 합니다.  
  
 `-moduleassemblyname` 옵션 다음에 해당할 경우에 필요 합니다.  
  
-   모듈의 데이터 형식에 대 한 액세스에 필요한를 `Friend` 참조 된 어셈블리의 형식입니다.  
  
-   참조 된 어셈블리에 모듈을 빌드는 어셈블리를 friend 어셈블리 액세스 권한을 부여한 합니다.  
  
 모듈을 만드는 방법에 대 한 자세한 내용은 참조 하세요. [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)합니다. Friend 어셈블리에 대 한 자세한 내용은 참조 하세요. [Friend 어셈블리](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)합니다.  
  
> [!NOTE]
>  `-moduleassemblyname` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없는 경우 즉, 사용할 수 있는 명령 프롬프트에서 컴파일할 때만 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 다중 파일 어셈블리 빌드](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [-main](../../../visual-basic/reference/command-line-compiler/main.md)  
 [-참조 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [어셈블리 및 전역 어셈블리 캐시](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Friend 어셈블리](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)
