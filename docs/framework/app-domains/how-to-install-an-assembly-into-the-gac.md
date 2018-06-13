---
title: '방법: 전역 어셈블리 캐시에 어셈블리 설치'
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed6519cb6bb7006f62ef83cd6baf8f2e32a44d19
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744384"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a>방법: 전역 어셈블리 캐시에 어셈블리 설치
강력한 이름의 어셈블리를 전역 어셈블리 캐시(GAC)에 설치하는 방법은 두 가지입니다.  
  
> [!IMPORTANT]
>  강력한 이름의 어셈블리만 GAC에 설치할 수 있습니다. 강력한 이름의 어셈블리를 만드는 방법에 대한 자세한 내용은 [방법: 강력한 이름으로 어셈블리 서명](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)을 참조하세요.  
  
-   [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688.aspx) 사용.  
  
     이렇게 하려면 Visual Studio 2012 및 Visual Studio 2013에서 InstallShield Limited Edition 프로젝트를 만듭니다.  
  
     전역 어셈블리 캐시에 어셈블리를 추가하는 가장 일반적인 방법입니다. 설치 관리자는 전역 어셈블리 캐시에서 어셈블리 참조 횟수를 제공하며, 다른 여러 가지 이점을 제공합니다.  
  
-   [전역 어셈블리 캐시 도구(Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) 사용.  
  
     Gacutil.exe를 사용하여 전역 어셈블리 캐시에 강력한 이름의 어셈블리를 추가하고 전역 어셈블리 캐시의 콘텐츠를 볼 수 있습니다.  
  
    > [!NOTE]
    >  Gacutil.exe는 개발 용도로만 사용되며, 전역 어셈블리 캐시에 프로덕션 어셈블리를 설치하는 데 사용할 수 없습니다.  
  
> [!NOTE]
>  이전 버전의 .NET Framework에서는 Shfusion.dll Windows 셸 확장을 통해 파일 탐색기로 어셈블리를 끌어서 설치할 수 있었습니다. [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터는 Shfusion.dll이 사용되지 않습니다.  
  
### <a name="to-use-the-global-assembly-cache-tool-gacutilexe"></a>전역 어셈블리 캐시 도구(Gacutil.exe)를 사용하려면  
  
1.  명령 프롬프트에 다음 명령을 입력합니다.  
  
     **gacutil -i** \<*assembly name*>  
  
     이 명령에서 *assembly name*은 전역 어셈블리 캐시에 설치할 어셈블리의 이름입니다.  
  
 다음 예제는 파일 이름이 `hello.dll`인 어셈블리를 전역 어셈블리 캐시에 설치합니다.  
  
```  
gacutil -i hello.dll  
```  
  
 자세한 내용은 [전역 어셈블리 캐시 도구(Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)를 참조하세요.  
  
### <a name="to-use-an-installshield-limited-edition-project"></a>InstallShield Limited Edition 프로젝트를 사용하려면  
  
1.  솔루션에 대한 바로 가기 메뉴를 열고 **추가**, **새 프로젝트**를 차례로 선택하여 솔루션에 설치 및 배포 패키지를 추가합니다.  
  
2.  **새 프로젝트 추가** 대화 상자의 **Installed** 폴더에서 **기타 프로젝트 형식**, **설치 및 배포**, **InstallShield Limited Edition**을 차례로 선택하고 프로젝트 이름을 지정합니다. (메시지가 나타나면 InstallShield를 다운로드, 설치 및 활성화합니다.)  
  
3.  **솔루션 탐색기**에서 프로젝트 도우미를 사용하거나 **솔루션 탐색기**에서 번호가 매겨진 단계의 하위 단계를 선택하여 설치 및 배포 프로젝트의 일반 구성을 수행합니다. GAC에 어셈블리를 추가하지 않을 경우 수행하는 대로 설치를 구성합니다.  
  
4.  GAC에 어셈블리를 추가하는 프로세스를 시작하려면 **솔루션 탐색기**의 **응용 프로그램 데이터 지정** 단계에서 **파일**을 선택합니다.  
  
5.  **대상 컴퓨터의 폴더** 창에서 **대상 컴퓨터**에 대한 바로 가기 메뉴를 열고 **미리 정의된 폴더 표시**, **[GlobalAssemblyCache]** 를 차례로 선택합니다.  
  
6.  전역 어셈블리 캐시에 설치하려는 어셈블리를 포함한 솔루션의 각 프로젝트에 대해 다음을 수행합니다.  
  
    1.  **원본 컴퓨터의 폴더** 창에서 프로젝트를 선택합니다.  
  
    2.  **대상 컴퓨터의 폴더** 창에서 **[GlobalAssemblyCache]** 를 선택합니다.  
  
    3.  **원본 컴퓨터의 파일** 창에서 *<project_name>***의 기본 출력**을 선택합니다.  
  
    4.  c 단계에서 파일을 **대상 컴퓨터의 파일** 창으로 끌거나 파일의 바로 가기 메뉴에서 **복사** 및 **붙여넣기** 명령을 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [어셈블리 및 전역 어셈블리 캐시 사용](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [방법: 전역 어셈블리 캐시에서 어셈블리 제거](../../../docs/framework/app-domains/how-to-remove-an-assembly-from-the-gac.md)  
 [Gacutil.exe(전역 어셈블리 캐시 도구)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)  
 [방법: 강력한 이름으로 어셈블리 서명](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [Windows Installer 배포](http://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0)
