---
title: "Regsvcs.exe(.NET 서비스 설치 도구) | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Regsvcs.exe
- .NET Services Installation tool
- loading assemblies
- assemblies [.NET Framework], registering
- type libraries
- registering assemblies
ms.assetid: 5220fe58-5aaf-4e8e-8bc3-b78c63025804
caps.latest.revision: 21
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 2c2820c265dc5c81dce638d533316a48f4972c6c
ms.contentlocale: ko-kr
ms.lasthandoff: 06/02/2017

---
# <a name="regsvcsexe-net-services-installation-tool"></a>Regsvcs.exe(.NET 서비스 설치 도구)
.NET 서비스 설치 도구를 사용하면 다음과 같은 작업을 수행할 수 있습니다.  
  
-   어셈블리를 로드 및 등록합니다.  
  
-   형식 라이브러리를 지정된 COM+ 응용 프로그램에 생성, 등록 및 설치합니다.  
  
-   프로그래밍 방식으로 클래스에 추가한 서비스를 구성합니다.  
  
 이 도구를 실행하려면 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다. 자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)를 참조하세요.  
  
 명령 프롬프트에 다음을 입력합니다.  
  
## <a name="syntax"></a>구문  
  
```  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll   
```  
  
#### <a name="parameters"></a>매개 변수  
  
|인수|설명|  
|--------------|-----------------|  
|*assemblyFile.dll*|소스 어셈블리 파일을 나타냅니다. 강력한 이름으로 어셈블리를 서명해야 합니다. 자세한 내용은 [강력한 이름으로 어셈블리 서명](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)을 참조하세요.|  
  
|옵션|설명|  
|------------|-----------------|  
|**/appdir:** *path*|응용 프로그램의 루트 디렉터리를 지정합니다.|  
|**/appname:** *applicationName*|찾거나 만들 COM+ 응용 프로그램의 이름을 지정합니다.|  
|**/c**|대상 응용 프로그램을 만듭니다.|  
|**/componly**|구성 요소만 구성하고 메서드 및 인터페이스는 무시합니다.|  
|**/exapp**|기존 응용 프로그램을 예상하기 위한 도구에 대해 지정합니다.|  
|**/extlb**|기존의 형식 라이브러리를 사용합니다.|  
|**/fc**|대상 응용 프로그램을 찾거나 만듭니다.|  
|**/help**|이 도구의 명령 구문 및 옵션을 표시합니다.|  
|**/noreconfig**|기존의 대상 응용 프로그램을 다시 구성하지 않습니다.|  
|**/nologo**|Microsoft 시작 배너를 표시하지 않습니다.|  
|**/parname:** *name*|찾거나 만들 COM+ 응용 프로그램의 이름 또는 ID를 지정합니다.|  
|**/reconfig**|기존의 대상 응용 프로그램을 다시 구성합니다. 이 값이 기본값입니다.|  
|**/tlb:** *typelibraryfile*|설치할 형식 라이브러리 파일을 지정합니다.|  
|**/u**|대상 응용 프로그램을 제거합니다.|  
|**/quiet**|자동 모드를 지정합니다. 즉, 로고 및 성공 메시지를 표시하지 않습니다.|  
|**/?**|이 도구의 명령 구문 및 옵션을 표시합니다.|  
  
## <a name="remarks"></a>설명  
 Regsvcs.exe에는 *assemblyFile.dll*에서 지정한 소스 어셈블리 파일이 필요하며, 이 어셈블리는 강력한 이름으로 서명되어야 합니다. 강력한 이름 서명에 대한 자세한 내용은 [강력한 이름으로 어셈블리 서명](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)을 참조하세요. 대상 응용 프로그램 및 형식 라이브러리 파일의 이름은 선택적입니다. *applicationName* 인수는 소스 어셈블리 파일에서 생성할 수 있으며, 이 인수가 없는 경우에는 소스 어셈블리 파일에서 생성될 수 있고 Regsvcs.exe로 만들어집니다. *typelibraryfile* 인수를 사용하여 형식 라이브러리 이름을 지정할 수 있습니다. 형식 라이브러리 이름을 지정하지 않으면 해당 어셈블리 이름이 기본값으로 사용됩니다.  
  
 Regsvcs.exe는 구성 요소의 메서드를 등록할 때 해당 메서드에 있는 [요청](http://msdn.microsoft.com/en-us/e5283e28-2366-4519-b27d-ef5c1ddc1f48) 및 [링크 요청](../../../docs/framework/misc/link-demands.md)의 영향을 받습니다. 이 도구는 완전히 신뢰할 수 있는 환경에서 실행되므로 대부분의 권한 요청이 성공하지만 Regsvcs.exe는 <xref:System.Security.Permissions.StrongNameIdentityPermission> 또는 <xref:System.Security.Permissions.PublisherIdentityPermission>에 대한 요청 또는 링크 요청에 따라 보호된 메서드가 있는 구성 요소를 등록할 수 없습니다.  
  
 Regsvcs.exe를 사용하려면 로컬 컴퓨터에 대한 관리자 권한이 있어야 합니다.  
  
 이러한 작업 수행 도중 오류가 발생하면 해당 오류 메시지가 표시됩니다.  
  
## <a name="examples"></a>예제  
 다음 명령을 사용하여 `myTest.dll`에 들어 있는 모든 공용 클래스를 `myTargetApp`(기존의 COM+ 응용 프로그램)에 추가하고 `myTest.tlb` 형식 라이브러리를 생성합니다.  
  
```  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 다음 명령을 사용하여 `myTest.dll`에 들어 있는 모든 공용 클래스를 `myTargetApp`(기존의 COM+ 응용 프로그램)에 추가하고 `newTest.tlb` 형식 라이브러리를 생성합니다.  
  
```  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a>참고 항목  
 [도구](../../../docs/framework/tools/index.md)   
 [방법: 강력한 이름으로 어셈블리 서명](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)   
 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)

