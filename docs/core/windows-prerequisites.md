---
title: "Windows | Microsoft Docs에서 .NET Core의 필수 구성 요소"
description: "Windows 컴퓨터에서 .NET Core 응용프로그램을 개발 및 실행하기 위해 필요한 종속성이 무엇인지 살펴보세요."
keywords: ".NET Core, Windows, 필수 구성 요소, 종속성, Visual Studio"
author: mairaw
ms.author: mairaw
ms.date: 03/07/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
translationtype: Human Translation
ms.sourcegitcommit: ff143583ba62fc1d82561e739a75107e50ebee88
ms.openlocfilehash: 13947fd81940c1ccb606cb4cd765dc230fe95c0f
ms.lasthandoff: 03/20/2017

---

# <a name="prerequisites-for-net-core-on-windows"></a>Windows에서 .NET Core의 필수 구성 요소

이 문서에서는 Windows 컴퓨터에서 .NET Core 응용프로그램을 배포 및 실행하고 Visual Studio 를 사용하여 개발하기 위해 필요한 종속성을 보여 줍니다.

## <a name="supported-windows-versions"></a>지원되는 Windows 버전

.NET Core는 다음 Windows 버전에서 지원됩니다.

* Windows 7 SP1
* Windows 8.1
* Windows 10
* Windows Server 2008 R2 SP1(전체 서버 또는 Server Core)
* Windows Server 2012 SP1(전체 서버 또는 Server Core)
* Windows Server 2012 R2 SP1(전체 서버 또는 Server Core)
* Windows Server 2016(전체 서버, Server Core 또는 Nano 서버)

[.NET Core 릴리스 정보](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md)에서 지원되는 운영 체제의 전체 집합을 참조하세요.

## <a name="net-core-dependencies"></a>.NET Core 종속성

Windows 10 및 Windows Server 2016보다 이전 버전의 Windows에서 실행하는 경우.NET core는 Visual C++ 재배포 가능 패키지가 필요합니다. 이 종속성은.NET Core 설치 관리자를 사용하는 경우에 자동으로 설치됩니다. 그러나 [설치 관리자 스크립트](https://docs.microsoft.com/en-us/dotnet/articles/core/tools/dotnet-install-script)를 통해 .NET Core를 설치하거나 자체 포함 .NET Core 응용프로그램을 배포하는 경우에는 [Visual Studio 2015용 Visual C++ 재배포 가능 패키지](https://www.microsoft.com/en-us/download/details.aspx?id=48145)를 수동으로 설치해야 합니다.

> [!NOTE]
> <em>Windows 7 및 Windows Server 2008용 컴퓨터만 해당:</em><br>
> 설치된 Windows가 최신 버전이며 Windows 업데이트를 통해 설치된 핫픽스 [KB2533623](https://support.microsoft.com/en-us/kb/2533623)이 포함되어 있는지 확인하세요.

## <a name="prerequisites-with-visual-studio-2017"></a>Visual Studio 2017 필수 구성 요소

.NET Core SDK를 사용하여 .NET Core 응용 프로그램을 개발할 수 있도록 원하는 편집기를 사용할 수 있습니다. 그러나 통합 개발 환경의 Windows에서 .NET Core 응용 프로그램을 개발하려는 경우 [Visual Studio 2017](#visual-studio-2017)을 사용할 수 있습니다.

> [!IMPORTANT]
> Visual Studio 2015에서 .NET Core 도구 미리 보기 버전을 사용할 수 있지만 이러한 프로젝트는 현재 더 이상 사용되지 않는 *project.json* 기반입니다. Visual Studio 2017에서는 MSBuild를 기준으로 하는 프로젝트 파일을 사용합니다. 형식 변경에 대한 자세한 내용은 [변경 내용의 대략적인 개요](./tools/cli-msbuild-architecture.md)를 참조하세요.

Visual Studio 2017을 사용하여 .NET Core 앱을 개발하려면 **.NET Core 플랫폼 간 개발** 도구 집합(**기타 도구 집합** 섹션)을 선택하여 최신 버전의 Visual Studio를 설치해야 합니다.
![".NET Core 플랫폼 간 개발" 워크플로가 선택된 Visual Studio 2017 설치 스크린샷](./media/windows-prerequisites/vs_workloads.jpg)

여러 버전의 Visual Studio 2017이 있습니다. [Visual Studio Community 2017](https://www.visualstudio.com/downloads/)을 무료로 다운로드하여 시작할 수 있습니다.  Visual Studio 설치 프로세스에 대한 자세한 내용은 [Visual Studio 2017 설치](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio)를 참조하세요.

최신 버전의 Visual Studio 2017을 실행 중인지 확인하려면 다음을 수행합니다.
 +
 +*도움말**메뉴에서**Microsoft Visual Studio 정보**를 선택합니다. +***Microsoft Visual Studio 정보** 대화 상자에서 버전 번호가 15.0.26228.4 이상이어야 합니다.

[릴리스 정보](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes)에서 Visual Studio 2017의 변경 내용에 대해 자세히 알아볼 수 있습니다.

[sdk]: https://go.microsoft.com/fwlink/?LinkID=827546
