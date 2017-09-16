---
title: "다중 컨테이너 및 마이크로 서비스 기반 .NET 응용 프로그램 디자인 및 개발"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 다중 컨테이너 및 마이크로 서비스 기반 .NET 응용 프로그램 디자인 및 개발"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: 8651254f4550a1a5c6a776ebd2524b5bfe20c546
ms.contentlocale: ko-kr
ms.lasthandoff: 09/05/2017

---
# <a name="designing-and-developing-multi-container-and-microservice-based-net-applications"></a>다중 컨테이너 및 마이크로 서비스 기반 .NET 응용 프로그램 디자인 및 개발

*컨테이너화된 마이크로 서비스 응용 프로그램의 개발은 다중 컨테이너 응용 프로그램 빌드를 의미합니다. 그러나 다중 컨테이너 응용 프로그램은 3계층 응용 프로그램과 같이 더 간단할 수 있으며, 마이크로 서비스 아키텍처를 사용하여 빌드하지 못할 수 있습니다.*

이전에 우리는 “마이크로 서비스 아키텍처를 구축할 때 Docker가 필요한가요?”라는 질문을 제기했습니다. 대답은 명확히 “아니요”입니다. Docker는 지원 기능으로, 중요한 이점을 제공할 수 있지만, 컨테이너 및 Docker가 마이크로 서비스에 대한 명백한 요구 사항은 아닙니다. 예를 들어 간단한 프로세스 또는 Docker 컨테이너로 실행되는 마이크로 서비스를 지원하는 Azure Service Fabric을 사용할 때 Docker 유무와 관계없이 마이크로 서비스 기반 응용 프로그램을 만들 수 있습니다.

그러나 Docker 컨테이너를 기반으로 하는 마이크로 서비스 기반 응용 프로그램을 설계 및 개발하는 방법을 알고 있는 경우 다른 간단한 응용 프로그램 모델을 설계 및 개발할 수도 있습니다. 예를 들어 다중 컨테이너 접근 방식이 필요한 3계층 응용 프로그램을 설계할 수도 있습니다. 이런 이유로 그리고 컨테이너 업계 내에서 마이크로 서비스 아키텍처가 중요한 추세이므로 이 섹션에서는 Docker 컨테이너를 사용하여 마이크로 서비스 아키텍처를 구현하는 데 중점을 둡니다.


>[!div class="step-by-step"]
[이전](../containerize-net-framework-applications/index.md) [다음](microservice-application-design.md)

