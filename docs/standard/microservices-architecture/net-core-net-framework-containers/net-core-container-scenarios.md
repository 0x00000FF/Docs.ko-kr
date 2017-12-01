---
title: "Docker 컨테이너에 대 한.NET Core를 선택 하는 경우"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Docker 컨테이너에 대 한.NET Core를 선택 하는 경우"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b7e2322bab7937c41d4659fefef11c8937d5eae7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="when-to-choose-net-core-for-docker-containers"></a>Docker 컨테이너에 대 한.NET Core를 선택 하는 경우

.NET Core의 모듈성 및 간단한 특성을 사용 하면 컨테이너에 대 한 완벽 한 있습니다. 배포 하는 컨테이너를 시작 하는 경우 해당 이미지는.NET Framework와 함께 보다.NET core 훨씬 작은입니다. 반면, 컨테이너에 대 한.NET Framework를 사용 하려면 Windows Nano Server 또는 Linux 이미지.NET Core를 사용 하는 보다 많이 과도 Windows Server Core 이미지를 이미지에 기반 해야 있습니다.

또한,.NET Core는 플랫폼 간 Linux 또는 Windows 컨테이너 이미지를 사용 하 여 서버 앱을 배포할 수 있습니다. 그러나 기존.NET Framework를 사용 하는 Windows Server Core에 따라 이미지만 배포할 수 있습니다.

자세한 설명은.NET Core를 선택 하는 이유는 다음과 같습니다.

## <a name="developing-and-deploying-cross-platform"></a>개발 및 배포 플랫폼 크로스

명확 하 게, 목표는 있어야 하는 경우 응용 프로그램 (웹 응용 프로그램 또는 서비스) 선택 하면 Docker (Linux 및 Windows)에서 지 원하는 여러 플랫폼에서 실행할 수 있는.NET Core를.NET Framework만 Windows를 지원 하므로.

.NET core는 개발 플랫폼으로 macOS도 지원합니다. 그러나 Docker 호스트에 컨테이너를 배포할 때 해당 호스트 Linux 또는 Windows 기반 (현재) 해야 합니다. 예를 들어 개발 환경에서 사용할 수 있습니다 mac에서 실행 중인 Linux VM

[Visual Studio](https://www.visualstudio.com/) Docker 개발을 지원 및 Windows 용 통합된 개발 환경 (IDE)를 제공 합니다. 

[Mac 용 visual Studio](https://www.visualstudio.com/vs/visual-studio-mac/) IDE, Xamarin Studio가 macOS에서 실행의 변화를 이며 2017 중순 이후 Docker를 지원 합니다.

사용할 수도 있습니다 [Visual Studio Code](https://code.visualstudio.com/) (VS Code) macOS, Linux 및 Windows에 있습니다. VS Code 디버깅 및 IntelliSense를 포함 하 여.NET Core를 완벽 하 게 지원 합니다. VS Code 경량 편집기 이기 때문에 Docker CLI와 함께에서 Mac에서 컨테이너 화 된 응용 프로그램 개발에 사용할 수 있습니다 및 [.NET Core CLI (명령줄 인터페이스) 도구](https://docs.microsoft.com/dotnet/core/tools/?tabs=netcore2x)합니다. 또한 제 3 자 가장 편집기 Sublime 텍스트, Emacs, vi, 및.NET 언어에 대 한 IntelliSense 지원을 제공 하는 오픈 소스 OmniSharp 프로젝트와 같은.NET Core를 지정할 수 있습니다. Ide 및 편집기 외에 지원 되는 모든 플랫폼에 대 한.NET Core CLI를 사용할 수 있습니다.

## <a name="using-containers-for-new-green-field-projects"></a>새 ("필드 녹색") 프로젝트에 대 한 컨테이너를 사용 하 여

컨테이너는 웹 앱 또는 모든 아키텍처 패턴을 따르는 서비스를 컨테이너 화할를 사용할 수도 있지만 주로 microservices 아키텍처와 함께에서 사용 됩니다. .NET Framework를 사용 하 여 Windows 컨테이너 있지만 모듈화 및.NET Core가 볍 기를 사용 하면 컨테이너와 microservices 아키텍처에 대 한 완벽 한 합니다. 를 만들고 컨테이너를 배포 하는 경우 해당 이미지는.NET Framework와 함께 보다.NET core 훨씬 작은입니다.

## <a name="creating-and-deploying-microservices-on-containers"></a>만들고 컨테이너에 microservices 배포

일반 프로세스를 사용 하 여 (컨테이너) 없이 microservices 기반 응용 프로그램을 구축 하기 위한 일반적인.NET Framework를 사용할 수 있습니다. 이런 방식으로.NET Framework가 이미 설치 하 고, 프로세스에서 공유할 수 있으므로 처리 빛나는 빠른를 시작 합니다. 그러나 컨테이너를 사용 하는 경우 기존.NET Framework에 대 한 이미지의 Windows Server Core에도 기반 고 하는 컨테이너에 microservices 접근 방식에 대 한 너무 많이 있습니다.

반면,.NET Core는 간단한.NET Core는 때문에 컨테이너를 기반으로 하는 microservices 지향 시스템 디렉터리가 경우 가장 적합 한 후보입니다. 또한 Linux 이미지 또는 Windows Nano 이미지의 관련된 컨테이너 이미지는 간결 하 고 컨테이너 빛을 만드는 작은 및 빠른 시작입니다.

마이크로 서비스는 가능한 한 적은 하려는: light 나타날 스핀업 하는 경우, 작은 사용 공간을 작은 경계가 지정 된 상황을 우려 사항, 작은 영역을 나타내는 시작 및 중지를 빠르게 할 수 있어야 있어야 합니다. 이러한 요구 사항에 대 한.NET Core 컨테이너 이미지와 같은 작은 하 고 인스턴스화하여 fast 컨테이너 이미지를 사용 하도록 합니다.

Microservices 아키텍처에서는 기술 서비스 경계를 넘어 혼합할 수 있습니다. 이렇게 하면 다른 microservices 또는 Node.js, Python, Java, GoLang, 또는 기타 기술을 사용 하 여 개발 하는 서비스와 함께 작동 하는 새 microservices에 대 한.NET Core로 점진적 마이그레이션.

## <a name="deploying-high-density-in-scalable-systems"></a>확장 가능한 시스템에 높은 밀도 배포합니다.

컨테이너 기반 시스템에는 최상의 가능한 밀도, 세분성, 및 성능 해야,.NET Core 및 ASP.NET 코어는 가장 적합 한 옵션입니다. ASP.NET Core는 기존.NET framework, ASP.NET 보다 10 배 빠른 지 며 microservices Java servlet, 이동, Node.js 등 다른 인기 있는 업계 기술 합니다.

Microservices 아키텍처, microservices (컨테이너)를 실행 수백 있을 수 있는 경우 특히 그렇습니다. ASP.NET Core 이미지 (.NET 핵심 런타임을에 기반) Linux 또는 Windows Nano에 훨씬 더 낮은 수의 서버 또는 Vm의 경우 인프라의 비용을 절감 하 고 호스팅 궁극적으로 사용 하 여 시스템을 실행할 수 있습니다.


>[!div class="step-by-step"]
[이전] (일반-guidance.md) [다음] (net-프레임 워크-컨테이너-scenarios.md)
