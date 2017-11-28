---
title: "Visual Studio용 개발자 명령 프롬프트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
caps.latest.revision: "45"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e93a1d116ac0480c80e259ddbadbc65fd9539389
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="developer-command-prompt-for-visual-studio"></a>Visual Studio용 개발자 명령 프롬프트
Visual Studio용 개발자 명령 프롬프트는 .NET Framework 도구를 쉽게 사용할 수 있는 환경 변수를 자동으로 설정합니다. 개발자 명령 프롬프트는 전체 또는 커뮤니티 버전의 Visual Studio와 함께 설치됩니다. Express 버전의 Visual Studio에서는 설치되지 않습니다.  
  
<a name="find"></a>   
## <a name="searching-for-the-command-prompt-on-your-machine"></a>컴퓨터에서 명령 프롬프트 검색  
 설치한 Visual Studio의 버전과 추가 SDK에 따라 여러 개의 명령 프롬프트가 표시될 수 있습니다. 예를 들어 64비트 버전의 Visual Studio는 32비트 및 64비트 명령 프롬프트를 모두 제공합니다. (32비트 및 64비트 버전의 대부분의 도구는 동일하나, 몇 가지 도구에서는 32비트 및 64비트 환경에 맞게 변경됩니다.) 아래 단계가 작동하지 않는 경우 [컴퓨터에서 수동으로 파일 찾기](#alternative) 또는 [Visual Studio 내에서 명령 프롬프트 실행](#visualstudio)을 시도해 볼 수 있습니다.  
  
 **Windows 10**  
  
1.  키보드에서 Windows 로고 키 ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")를 눌러 **시작** 메뉴를 엽니다.  
  
2.  **시작** 메뉴에서 `dev`를 입력합니다. 그러면 검색 패턴에 일치하는 설치된 응용 프로그램의 목록이 표시됩니다. 다른 명령 프롬프트를 찾으려면 `prompt`와 같은 다른 검색어를 입력해 봅니다.  
  
3.  **개발자 명령 프롬프트**(또는 사용할 명령 프롬프트)를 선택합니다.  
  
 **Windows 8.1**  
  
1.  키보드에서 Windows 로고 키 ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")를 눌러 **시작** 화면으로 이동합니다.  
  
2.  **시작** 화면에서 `CTRL + TAB`을 눌러 **앱** 목록을 열고 `V` 키를 누릅니다. 그러면 설치된 모든 Visual Studio 명령 프롬프트가 포함된 목록을 가져옵니다.  
  
3.  **개발자 명령 프롬프트**(또는 사용할 명령 프롬프트)를 선택합니다.  
  
 **Windows 8**  
  
1.  키보드에서 Windows 로고 키 ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")를 눌러 **시작** 화면으로 이동합니다.  
  
2.  **시작**에서 Windows 로고 키 ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`를 누릅니다.  
  
3.  화면 아래쪽에서 **앱 보기** 아이콘을 선택하고 `V` 키를 누릅니다. 그러면 설치된 모든 Visual Studio 명령 프롬프트가 포함된 목록을 가져옵니다.  
  
4.  **개발자 명령 프롬프트**(또는 사용할 명령 프롬프트)를 선택합니다.  
  
 **Windows 7**  
  
1.  **시작**을 선택하고 **모든 프로그램**, **Microsoft Visual Studio**를 차례로 확장합니다.  
  
2.  설치한 Visual Studio 버전에 따라 **Visual Studio Tools**, **Visual Studio 명령 프롬프트** 또는 사용할 명령 프롬프트를 선택합니다.  
  
 [Windows SDK](http://msdn.microsoft.com/windows/desktop/aa904949) 또는 [Windows Phone SDK](https://dev.windowsphone.com/downloadsdk)를 설치한 경우 ARM, x86 또는 x64 아키텍처의 추가 명령 프롬프트가 표시될 수 있습니다. 각 도구의 설명서를 확인하여 사용할 명령 프롬프트 버전을 결정합니다.  
  
<a name="alternative"></a>   
## <a name="manually-locating-the-files-on-your-machine"></a>컴퓨터에서 수동으로 파일 찾기  
  일반적으로 설치한 명령 프롬프트의 바로 가기는 C:\ProgramData\Microsoft\Windows\시작 메뉴\Programs\Visual Studio 2015\Visual Studio Tools와 같이 Visual Studio에 대한 **시작 메뉴** 폴더에 배치됩니다.    하지만 어떤 이유로 명령 프롬프트를 검색했는데 예상된 결과를 생성하지 않는 경우, 컴퓨터에서 수동으로 바로 가기를 찾아 이를 사용하려고 시도할 수 있습니다.   VsDevCmd.bat와 같은 명령 프롬프트 파일의 이름 검색을 시도하거나 C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools와 같은 도구 폴더로 이동합니다(경로는 Visual Studio 버전 및 설치 위치에 따라 바뀜).  
  
<a name="visualstudio"></a>   
## <a name="running-command-prompt-from-inside-visual-studio"></a>Visual Studio 내에서 명령 프롬프트 실행  
 Visual Studio 개발자 명령 프롬프트 또는 다른 명령 프롬프트를 외부 도구 목록에 추가하여 Visual Studio의 도구 메뉴에 추가하면 쉽게 액세스할 수 있습니다. 다음은 이 작업을 수행할 수 있는 방법입니다.  
  
1.  Visual Studio를 엽니다.  
  
2.  **도구** 메뉴를 선택하고 **외부 도구...**를 선택합니다.  
  
3.  **외부 도구** 대화 상자에서 **추가** 단추를 선택합니다. 새 항목이 표시됩니다.  
  
4.  `Command Prompt`와 같은 새 메뉴 항목에 대해 **제목**을 입력합니다.  
  
5.  **명령** 필드에서 `%comspec%` 또는 `C:\Windows\System32\cmd.exe` 등의 시작할 파일을 지정합니다.  
  
6.  **인수** 필드에서 `/k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools\VsDevCmd.bat"` 등의 사용하려는 특정 명령 프롬프트가 있는 위치를 지정합니다(이렇게 하면 [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]로 설치된 개발자 명령 프롬프트를 시작함). Visual Studio 버전 및 설치 위치에 따라 이 값을 변경해야 합니다.  
  
7.  **프로젝트 디렉터리**와 같은 **초기 디렉터리** 필드에 대한 값을 선택합니다.  
  
8.  **확인** 단추를 선택합니다.  
  
 그런 다음 새 메뉴 항목이 추가되고 **도구** 메뉴에서 명령 프롬프트에 액세스할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [도구](../../../docs/framework/tools/index.md)  
 [외부 도구 관리](/visualstudio/ide/managing-external-tools)
