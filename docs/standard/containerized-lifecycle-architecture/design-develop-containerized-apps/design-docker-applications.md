---
title: Docker 응용 프로그램 디자인
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 951169a6b7c458872f5c90a8845826b675671101
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="design-docker-applications"></a>Docker 응용 프로그램 디자인

1 장 컨테이너 및 Docker에 대 한 기본 개념을 도입 합니다. 해당 정보는 기본 수준 시작 하는 데 필요한 정보입니다. 하지만 엔터프라이즈 응용 프로그램은 복잡 하 고 단일 서비스 또는 컨테이너 대신 여러 서비스 구성 될 수 있습니다. 이러한 선택적으로 사용 사례에 대 한 알아야 추가 방법은 디자인 같은 서비스 지향 아키텍처 SOA () 및 더 많은 고급 microservices 개념 및 컨테이너에 오케스트레이션 개념입니다. 이 문서의 범위 microservices 제한 되지 않습니다. 하지만 모든 Docker 응용 프로그램 수명 주기를 따라서 것 않습니다 탐색 하지는 심층에서 microservices 아키텍처 있습니다도 하거나 하기 때문에 컨테이너 및 Docker를 사용 하 여 작업, 백그라운드 작업 또는 일반 쌍으로 포함 하 여 단일 응용 프로그램 배포 방법입니다.

그러나 응용 프로그램 수명 주기 및 DevOps에 들어가기 전에 되기 미리 알고 어떻게 디자인 및 응용 프로그램 란 무엇 이며 디자인 선택 사항 구성 하는 것이 중요 합니다.


>[!div class="step-by-step"]
[이전] [다음] (공통-컨테이너-디자인-principles.md) (index.md)
