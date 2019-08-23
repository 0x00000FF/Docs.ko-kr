---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 75c3e5842447a8f0812d5a90d7157f7a6a496936
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962440"
---
# <a name="-bugreport"></a>-bugreport
버그 보고서를 작성할 때 사용할 수 있는 파일을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`file`|필수 요소. 버그 보고서를 포함할 파일의 이름입니다. 이름에 공백이 포함 된 경우 파일 이름을 따옴표 ("")로 묶습니다.|  
  
## <a name="remarks"></a>설명  
 에 `file`추가 되는 정보는 다음과 같습니다.  
  
- 컴파일할 때 모든 소스 코드 파일의 복사본입니다.  
  
- 컴파일에 사용 된 컴파일러 옵션 목록입니다.  
  
- 컴파일러, 공용 언어 런타임 및 운영 체제에 대 한 버전 정보입니다.  
  
- 컴파일러 출력입니다(있는 경우).  
  
- 메시지가 표시 되는 문제에 대 한 설명입니다.  
  
- 문제를 해결 하는 방법에 대 한 설명입니다.  
  
 모든 소스 코드 파일의 복사본은에 `file`포함 되어 있으므로 가능한 짧은 프로그램에서 (의심 스러운) 코드 결함을 재현할 수 있습니다.  
  
> [!IMPORTANT]
> 옵션 `-bugreport` 은 잠재적으로 중요 한 정보를 포함 하는 파일을 생성 합니다. 여기에는 현재 시간, 컴파일러 버전, .NET Framework 버전, OS 버전, 사용자 이름, 컴파일러가 실행 된 명령줄 인수, 모든 소스 코드, 참조 된 어셈블리의 이진 형식 등이 포함 됩니다. ASP.NET 응용 프로그램의 서버 쪽 컴파일에 대해 web.config 파일에서 명령줄 옵션을 지정 하 여이 옵션에 액세스할 수 있습니다. 이를 방지 하려면 machine.config 파일을 수정 하 여 사용자가 서버에서 컴파일하지 못하도록 합니다.  
  
 , `-errorreport:prompt` `file` 또는 와`-errorreport:send`함께이 옵션을 사용 하는 경우 응용 프로그램에 내부 컴파일러 오류가 발생 하면의 정보가 Microsoft Corporation에 전송 됩니다. `-errorreport:queue` 이 정보는 Microsoft 엔지니어가 오류의 원인을 파악 하는 데 도움이 되며 Visual Basic의 다음 릴리스를 개선 하는 데 도움이 될 수 있습니다. 기본적으로 Microsoft로 전송 되는 정보는 없습니다. 그러나 기본적으로 사용 되는를 사용 `-errorreport:queue`하 여 응용 프로그램을 컴파일하면 응용 프로그램에서 오류 보고서를 수집 합니다. 그러면 컴퓨터의 관리자가 로그인 할 때 오류 보고 시스템에 로그온 한 이후에 발생 한 오류 보고서를 Microsoft에 전달할 수 있는 팝업 창이 표시 됩니다.  
  
> [!NOTE]
> 이 `/bugreport` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 모든 `T2.vb` 버그 보고 정보를 컴파일하여 파일 `Problem.txt`에 저장 합니다.  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)
- [-errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Ws-securitypolicy에 대 한 trustLevel 요소 (ASP.NET Settings 스키마)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))
