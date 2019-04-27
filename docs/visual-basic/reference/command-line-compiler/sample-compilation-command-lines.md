---
title: 샘플 컴파일 명령줄(Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: 0771ed41d6c58ce7cc98435b405f5819e45393db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916762"
---
# <a name="sample-compilation-command-lines-visual-basic"></a>샘플 컴파일 명령줄 (Visual Basic)
Visual Studio 내에서 Visual Basic 프로그램을 컴파일할 수 또는 실행 파일 (.exe) 또는 동적 연결 라이브러리 (.dll) 파일을 생성 하려면 명령줄에서 컴파일할 수 있습니다.  
  
 Visual Basic 명령줄 컴파일러에는 입출력 파일, 어셈블리 및 디버그 및 전처리기 옵션을 제어 하는 옵션의 전체 집합을 지원 합니다. 각 옵션은 서로 바꿔 사용할 수 있는 두 가지 형태로 사용할 수 있습니다: `-option` 고 `/option`입니다. 이 설명서 표시는 `-option` 폼입니다.  
  
 다음 표에서 몇 가지 샘플 명령줄이 용도 맞게 수정할 수 있습니다.  
  
|대상|사용|  
|--------|---------|  
|File.exe를 만들어 File.vb 컴파일|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|File.dll을 만들어 File.vb 컴파일|`vbc -target:library File.vb`|  
|File.vb 컴파일하고 My.exe를 만듭니다|`vbc -out:My.exe File.vb`|  
|File.vb 컴파일 및 라이브러리와 File.dll 이라는 참조 어셈블리를 만들려면|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|최적화를 사용 하 여 현재 디렉터리에서 모든 Visual Basic 파일에서 컴파일 및 `DEBUG` File2.exe 생성 정의 기호|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|로고 또는 경고를 표시 하지 않고 File2.dll의 디버그 버전을 생성 하는 현재 디렉터리에서 모든 Visual Basic 파일을 컴파일합니다|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|현재 디렉터리 Something.dll에 있는 모든 Visual Basic 파일 컴파일|`vbc -target:library -out:Something.dll *.vb`|  
  
> [!TIP]
>  Visual Studio IDE를 사용 하 여 프로젝트를 빌드할 때 연결에 대 한 정보를 표시할 수 있습니다 **vbc** 출력 창에 해당 컴파일러 옵션을 사용 하 여 명령입니다. 이 정보를 표시 하려면 열을 [옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), 설정한 후 합니다 **MSBuild 프로젝트 빌드 출력의 자세한 정도** 에 **보통** 또는 더 높은 수준의 세부 정보 표시 합니다.   
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
