---
title: 클라우드 액세스에 최적화 된 응용 프로그램에서 Microsoft 기술
description: Azure 클라우드 및 Windows 컨테이너와 기존.NET 응용 프로그램을 최신식 | 클라우드 액세스에 최적화 된 응용 프로그램에서 Microsoft 기술
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 3c5886dc3583a5d4a6cc9566556edbe1822ad6d1
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36315182"
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a>클라우드 액세스에 최적화 된 응용 프로그램에서 Microsoft 기술

다음 목록에는 도구, 기술 및 클라우드 액세스에 최적화 된 앱에 대 한 요구 사항으로 인식 되는 솔루션을 설명 합니다. 우선 순위에 따라 클라우드 액세스에 최적화 된 요소를 선택적으로 또는 점차적으로 적용할 수 있습니다.

-   **클라우드 인프라**: 계산 플랫폼, 운영 체제, 네트워크 및 저장소를 제공 하는 인프라입니다. Microsoft Azure는이 수준에 배치 됩니다.

-   **런타임**:이 계층은 실행할 응용 프로그램에 대 한 환경을 제공 합니다. 이 계층에 기반 일반적으로 컨테이너를 사용 하는 경우 [Docker 엔진](https://docs.docker.com/engine/), 또는 Linux 호스트에서 Windows 호스트에서 실행 중입니다. ([Windows 컨테이너](https://docs.microsoft.com/virtualization/windowscontainers/about/) Windows Server 2016부터 지원 됩니다. Windows 컨테이너는 Windows에서 실행 되는 기존.NET Framework 응용 프로그램에 적합 합니다.)

-   **클라우드를 관리 되는**: 비용 및 관리 하 고 기본 인프라를 Vm OS 패치를 지 원하는 및 네트워킹 구성의 복잡 한 경우 관리 되는 클라우드 옵션을 선택 하면 방지할 수 있습니다. IaaS를 사용 하 여 마이그레이션 하기로 선택한 경우 사용자는 이러한 작업을 모두에 대 한 관련된 비용입니다. 관리 되는 클라우드 옵션을 응용 프로그램 및 개발 하는 서비스를 관리 합니다. 클라우드 서비스 공급자는 일반적으로 다른 모든 관리 합니다. Examples of managed cloud services in Azure include [Azure SQL Database](https://azure.microsoft.com/services/sql-database), [Azure Redis Cache](https://azure.microsoft.com/services/cache/), [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Database for MySQL](https://azure.microsoft.com/services/mysql/), [Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/), and managed compute services like [VM scale sets](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/), [Azure App Service](https://azure.microsoft.com/services/app-service/), and [Azure Kubernetes Service](https://azure.microsoft.com/services/container-service/).

-   **응용 프로그램 개발**: 컨테이너에서 실행 되는 응용 프로그램을 빌드할 때 언어 언어 중에서 선택할 수 있습니다. 이 가이드에 중점을 두고 [.NET](https://www.microsoft.com/net), 있지만 이동 하거나/Java, Node.js, Python, ' 봄 ' 같은 다른 언어를 사용 하 여 컨테이너 기반 앱을 개발할 수 있습니다.

-   **모니터링, 원격 분석 로깅 및 감사**: 모니터 및 감사 응용 프로그램 및 클라우드에서 실행 중인 컨테이너에 기능은 모든 클라우드 액세스에 최적화 된 응용 프로그램에 매우 중요 합니다. [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) 및 [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) 클라우드 액세스에 최적화 된 앱에 대 한 모니터링 및 감사가 제공 하는 주요 Microsoft 도구입니다.

-   **프로 비전**: 자동화 도구를 사용 하면 인프라를 프로 비전 하 고 여러 환경 (프로덕션, 테스트, 스테이징)에 응용 프로그램을 배포 합니다. 응용 프로그램의 구성 및 환경 관리에 Chef 및 Puppet과 같은 도구를 사용할 수 있습니다. 또한이 계층 쉽고 직접적 접근 방식을 사용 하 여 구현할 수 있습니다. 예를 들어 Azure CLI (명령줄 인터페이스 Azure) 도구를 사용 하 여 직접 배포할 하 고 다음 연속 배포를 사용 하 여 있고 관리 파이프라인에서 릴리스 [Visual Studio Team Services](https://visualstudio.microsoft.com/team-services/)합니다.

-   **응용 프로그램 수명 주기**: [Visual Studio Team Services](https://visualstudio.microsoft.com/team-services/) Jenkins, 등의 다른 도구는 데 도움이 되는 빌드된 자동화 서버 구현 CI/CD 파이프라인, 릴리스 관리를 포함 하 여 합니다.

이 장 및 관련된 연습의 다음 섹션에서는 런타임 계층 (Windows 컨테이너)에 대 한 세부 정보에 대해서만 설명 집중 합니다. 지침에서는 Windows Server 2016 (및 이상 버전)에서 Windows 컨테이너를 Vm 및 Azure 컨테이너 인스턴스를 배포할 수 있습니다 하는 방법을 설명 합니다. 또한 Azure 앱 서비스 같은 더 많은 고급 PaaS 플랫폼 및 Azure 서비스 패브릭 및 Azure Kubernetes 서비스와 같은 orchestrator 다룹니다.

## <a name="monolithic-applications-can-be-cloud-optimized"></a>응용 프로그램 모놀리식 *수* 클라우드 액세스에 최적화 된 수

단일 응용 프로그램 (응용 프로그램 microservices에 기반 하지 않는)를 강조 표시 해야 *수* 클라우드 액세스에 최적화 된 응용 프로그램 이어야 합니다. 작성 하 고 클라우드 모델의 컨테이너, 지속적인 업데이트 DevOps 조합을 사용 하 여 컴퓨팅을 활용 하는 단일 응용 프로그램을 작동 시키려면 합니다. 비즈니스 목표에 대 한 기존 모놀리식 응용 프로그램이 적절 것을 최신식 있고 쉽게 클라우드 액세스에 최적화 된 합니다.

마찬가지로, 모놀리식 응용 프로그램이 클라우드 액세스에 최적화 된 응용 프로그램 일 수 N 계층 응용 프로그램 같은 다른, 더 복잡 한 아키텍처 클라우드 액세스에 최적화 된 응용 프로그램으로 현대화 수도 있습니다.

>[!div class="step-by-step"]
[이전](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
[다음](what-about-cloud-native-applications.md)
