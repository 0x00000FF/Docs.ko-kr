---
title: ".NET Core 명령줄 도구 Preview 3 아키텍처"
description: "Preview 3을 통해 전체.NET Core 도구를 계층화하는 방법에 대한 특정 변경 내용 설명"
keywords: "CLI, 확장성, 사용자 지정 명령, .NET Core"
author: blackdwarf
manager: wpickett
ms.date: 11/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: 233d365b582c274cd3a1f078846a6e854c7a6c95

---

<a name="high-level-overview-of-changes-in-cli-preview-3"></a>CLI Preview 3에 대한 변경의 심화 설명
-----------------------------------------------

# <a name="overview"></a>개요
이 문서에서는 `project.json`에서 MSBuild 및 `csproj` 프로젝트 시스템으로 이동으로 인해 발생하는 높은 수준의 변경 내용에 대해 설명합니다. 모두 구동 상태로 도구를 계층화하는 새로운 방법과, 사용할 수 있는 새로운 부분, 전체적인 상황에서의 현재 위치에 대해 간략하게 설명합니다. 이 문서를 읽고 나면 MSBuild 및 `csproj`로 이동한 후 .NET Core 도구를 구성하는 모든 부분에 대해 잘 이해하게 됩니다. 

> **참고:** 이 문서는 Preview 3 .NET Core 명령줄 도구를 사용하는 데 **필요하지 않습니다**. 이전 방식으로 도구를 계속 사용할 수 있습니다. 이 문서는 MSBuild로의 이동이 전반적인 "계층" 및 명령줄 도구 아키텍처를 어떻게 변화시키는지에 대한 완벽한 그림을 제공합니다. 

# <a name="moving-away-from-projectjson"></a>project.json로부터의 이동
.NET Core용 Preview 3 도구에서의 가장 큰 변화는 프로젝트 시스템이 [project.json에서 csproj로](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/) 이동한 점입니다. 명령줄 도구의 Preview 3 버전은 project.json에 대한 어떤 지원도 포함되지 않은 .NET Core 명령줄 도구의 첫 번째 릴리스입니다. 즉, project.json 기반 응용 프로그램 및 라이브러리를 빌드, 실행 또는 게시하는 데 사용할 수 없습니다. 이 버전의 도구를 사용하려면 기존 프로젝트를 마이그레이션하거나 새 프로젝트를 시작해야 합니다. 

이러한 흐름에 포함되어 project.json 프로젝트를 빌드하기 위해 개발된 사용자 지정 빌드 엔진이 전문적이고 완전한 기능의 빌드 엔진인 [MSBuild](https://github.com/Microsoft/msbuild)로 바뀌었습니다. MSBuild는.NET 커뮤니티에서 잘 알려진 엔진으로 플랫폼의 첫 번째 릴리스 이후 핵심 기술로 부상하였습니다. 물론 .NET Core 응용 프로그램을 구축해야 하므로 MSBuild는 .NET Core로 이식되었으며, .NET Core에서 실행하는 모든 플랫폼에서 사용할 수 있습니다. NET Core의 주요 기능 중 하나는 플랫폼 간 개발 스택에 대한 것으로 이 이동으로 인해 이 기능이 없어지진 않습니다.

> **참고:** 처음 MSBuild를 사용하고 자세한 내용을 보려면 [기존 설명서](https://msdn.microsoft.com/en-us/library/dd637714.aspx)를 읽어 시작할 수 있습니다. 

# <a name="the-tooling-layers"></a>도구 레이어
기존 프로젝트 시스템으로부터의 이동과 빌드 엔진 전환에 따라 이러한 변화로 인해 전체 .NET Core 도구 에코 시스템의 전반적인 "계층"에도 변화가 있는지 자연스럽게 질문이 나오게 됩니다. 새로운 비트 및 구성 요소가 있을까요?

다음 그림에 나와 있는 것처럼 이전에 알고 있는 Preview 2 계층을 빠르게 환기시켜보겠습니다.

![Preview 2 도구에 대한 상위 수준 아키텍처](media/p2-arch.png)

도구 계층은 매우 간단합니다. 맨 아래 기본으로 .NET Core 명령줄 도구가 있습니다. Visual Studio 또는 VS Code와 같은 높은 수준의 다른 도구는 모두 프로젝트 빌드와 종속성 복원을 위해 CLI를 사용합니다. 다시 말하면 예를 들어 Visual Studio에서 복원 작업을 수행하려면 CLI에서 `dotnet restore` 명령을 호출합니다. 

새 프로젝트 시스템으로의 이전으로 이전 다이어그램이 다음과 같이 변경됩니다. 

![Preview 3 도구에 대한 상위 수준 아키텍처](media/p3-arch.png)

주요 차이점은 CLI가 더 이상 기본 계층이 아니라는 점입니다. 이 역할은 이제 "공유된 SDK 구성 요소"에 의해 채워집니다. 이 공유된 SDK 구성 요소는 코드 컴파일, 게시, nuget 패키지 압축 등을 담당하는 대상 및 관련 작업 집합입니다. SDK 자체는 오픈 소스이며 [SDK 리포지토리](https://github.com/dotnet/sdk)의 GitHub에서 사용할 수 있습니다. 

> **참고:** "대상"은 MSBuild에서 호출할 수 있는 명명된 작업을 나타내는 MSBuild 용어입니다. 일반적으로 대상에서 구현되는 로직을 실행하는 하나 이상의 작업과 함께 사용됩니다. MSBuild는 `Copy` 또는 `Execute`와 같이 바로 사용할 수 있는 많은 대상을 지원합니다. 또한 이를 통해 사용자는 관리되는 코드를 사용하여 고유한 작업을 기록하고 대상을 정의하여 이러한 작업을 실행할 수 있습니다. 자세한 내용은 [MSDN](https://msdn.microsoft.com/en-us/library/ms171466.aspx)에서 MSBuild 작업에 대해 확인하세요. 

이제 모든 도구 집합은 CLI를 비롯하여 공유된 SDK 구성 요소와 대상을 사용합니다. 예를 들어 Visual Studio의 다음 버전에서 NET Core 프로젝트용 종속성 복원을 위해 `dotnet restore` 명령을 호출하지 않는다면, 직접 "복원" 대상을 사용합니다. 이는 MSBuild 대상이므로, 원시 MSBuild를 사용하여 [dotnet msbuild](dotnet-msbuild.md) 명령을 통해 실행할 수도 있습니다. 

## <a name="preview-3-cli-commands"></a>Preview 3 CLI 명령
공유된 SDK 구성 요소는 대부분의 기존 CLI 명령들이 MSBuild 작업 및 대상으로 다시 구현되었음을 의미합니다. CLI 명령 및 도구 집합의 경우 어떤 의미가 있을까요? 

사용 관점으로 보면 CLI를 사용하는 방식은 변경되지 않습니다. CLI에는 Preview 2 릴리스에 있는 핵심 명령이 아직 있습니다.

* `new`
* `restore`
* `run` 
* `build`
* `publish`
* `test`
* `pack` 

이러한 명령은 여전히 사용자가 예상하는 대로 수행됩니다(프로젝트 새로 구동, 빌드, 게시, 압축 등). 대부분의 옵션은 변경되지 않은 채로 그래도 있습니다. 변경 사항에 대해 살펴보려면 이 사이트의 Preview 3 설명서 또는 명령의 도움말 화면(`dotent <command> --help` 사용)에서 참조할 수 있습니다. 

실행 관점에서 CLI 명령은 매개 변수를 사용하고 "원시" MSBuild에 대한 호출을 생성하여 필요한 속성을 설정하고 원하는 대상을 실행합니다. 이해를 돕기 위해 다음 명령을 고려해 보세요. 

    `dotnet publish -o pub -c Release`. 
    
이 명령은 "릴리스" 구성을 사용하여 응용 프로그램을 `pub` 폴더에 게시합니다. 내부적으로 이 명령은 다음과 같은 MSBuild 호출로 변환됩니다. 

    `dotnet msbuild /t:Publish /p:OutputPath=pub /p:Configuration`

이 규칙에서 주목할 만한 예외는 `new` 및 `run` 명령으로 MSBuild 대상으로 구현되지 않았습니다. 

# <a name="conclusion"></a>결론 
이 문서에서는 Preview 3에서 제공되는 전반적인 CLI 도구 아키텍처와 기능에서 발생하는 높은 수준의 변경에 대해 개괄적으로 살펴보았습니다. 공유된 SDK 구성 요소 개념에 대해 소개하고 Preview 3에서 CLI 명령이 기술적인 관점에서 작동하는 방식에 대해 살펴보았습니다. 




<!--HONumber=Nov16_HO3-->


