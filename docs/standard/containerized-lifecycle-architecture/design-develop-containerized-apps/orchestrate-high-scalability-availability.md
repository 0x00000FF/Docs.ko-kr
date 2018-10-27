---
title: 마이크로 서비스 및 높은 확장성 및 가용성을 위해 다중 컨테이너 응용 프로그램 오케스트레이션
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: 993f1d18637f39b6df4d876db8a0fe86e34391e3
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2018
ms.locfileid: "50170356"
---
# <a name="orchestrating-microservices-and-multicontainer-applications-for-high-scalability-and-availability"></a>마이크로 서비스 및 높은 확장성 및 가용성을 위해 다중 컨테이너 응용 프로그램 오케스트레이션

응용 프로그램이 마이크로 서비스를 기반으로 하거나 단순히 여러 컨테이너로 분할되는 경우 프로덕션 지원 응용 프로그램에 오케스트레이터를 사용해야 합니다. 이전에 소개한 대로 마이크로 서비스 기반 방법에서 각 마이크로 서비스마다 모델 및 데이터를 소유하므로 개발 및 배포 관점에서 독립적입니다. 하지만 보다 일반적인 응용 프로그램을 구성 된 여러 서비스 (예: SOA)가 있는 경우에 또한 수는 여러 컨테이너 또는 분산된 시스템으로 배포 해야 하는 단일 비즈니스 응용 프로그램을 구성 하는 서비스입니다. 이러한 종류의 시스템은 규모 확장 및 관리할 복잡 한 따라서 반드시 프로덕션이 준비 된 하 고 확장 가능한 다중 컨테이너 응용 프로그램을 원할 경우 오 케 스트레이 터가 필요 합니다.

그림 4 ~ 6 (컨테이너) 여러 마이크로 서비스로 구성 된 응용 프로그램의 클러스터로 배포를 보여 줍니다.

![](./media/image6.png)

그림 4-6: 컨테이너의 클러스터

이는 논리적인 방법처럼 보입니다. 하지만 어떻게 하면 처리는 부하 분산, 라우팅 및 이러한 구성 된 응용 프로그램을 오케스트레이션?

Docker 명령줄 인터페이스 (CLI)를 하나의 호스트에서 하나의 컨테이너를 관리 하는 요구 사항을 충족 하지만 복잡 한 분산된 응용 프로그램에 대 한 여러 호스트에 배포 하는 여러 컨테이너를 관리 하는 데 있어 짧은 합니다. 대부분의 경우에는 자동으로 컨테이너를 시작, 일시 중단 하면 또는 필요한 경우 종료 하 고 제어 하는 것이 가장 좋습니다도 네트워크 및 데이터 저장소와 같은 리소스에 액세스 하는 방법을 관리 플랫폼을 해야 합니다.

개별 컨테이너 또는 매우 간단하게 구성된 앱을 관리하는 것 외에도, 마이크로 서비스가 있는 대규모 엔터프라이즈 응용 프로그램으로 이동하려면 오케스트레이션 및 클러스터링 플랫폼으로 전환해야 합니다.

아키텍처 및 개발 관점에서 빌드, 대기업, 마이크로 서비스 기반 있다면 응용 프로그램의 경우 것은 다음 플랫폼과 고급 시나리오를 지 원하는 제품을 이해 해야:

-   **클러스터 및 오 케 스트레이 터** 크기를 조정 해야 하는 경우-out 많은 Docker 호스트에서 응용 프로그램을 같은 대규모 마이크로 서비스 기반 응용 프로그램을 사용 하 여는 것이 중요 하 여 단일 클러스터로 모든 해당 호스트를 관리 하려면 기본 플랫폼의 복잡성을 추상화 합니다. 이것이 컨테이너 클러스터 및 오 케 스트레이 터 제공 항목입니다. 오 케 스트레이 터의 예로 Docker Swarm, Mesosphere DC/OS, Kubernetes (처음 3 개 Azure Container Service를 통해 사용할 수 있는), 및 Azure Service Fabric이 있습니다.

-   **스케줄러** *일정* 관리자 사용자 인터페이스를 제공 하는 클러스터에서 컨테이너를 시작 하는 기능을 할 것을 의미 합니다. 클러스터 스케줄러에는 여러 책임: 클러스터의 리소스를 효율적으로 사용 하려면, 사용자가 노드 또는 호스트 간에 효율적으로 부하 분산 컨테이너에서 제공 하는 제약 조건을 설정 및 높은 하면서 오류에 대해 강력한 되도록 가용성입니다.

클러스터 및 스케줄러의 개념은 밀접하게 관련되어 있으므로 여러 공급업체에서 제공하는 제품은 종종 두 가지 기능의 집합을 제공합니다. 표 4-1의 가장 중요 한 플랫폼 및 클러스터 및 스케줄러에 대 한 소프트웨어 선택 항목을 나열 합니다. 이러한 클러스터는 Azure와 같은 공용 클라우드에서 일반적으로 제공 됩니다.

컨테이너 클러스터링, 오케스트레이션 및 예약에 대 한 표 4-1: 소프트웨어 플랫폼

| 플랫폼 | 설명 |
|---|---|
| Docker Swarm<br/> ![Docker Swarm 로고](./media/image7.png) | Docker Swarm 클러스터 및 Docker 컨테이너를 예약 하는 기능을 제공 합니다. Swarm을 사용하면 Docker 호스트 풀을 단일 가상 Docker 호스트로 전환할 수 있습니다. 클라이언트 Swarm API 요청에는 Swarm 쉽게 크기를 조정 하는 응용 프로그램에 대 한 여러 호스트 즉, 호스트에 수행한 동일한 방식으로 수행할 수 있습니다. <br /><br /> Docker Swarm은 Docker 회사의 제품입니다. <br /><br /> Docker v1.12 이상에서는 네이티브 및 기본 제공 Swarm 모드를 실행할 수 있습니다. |
| Mesosphere DC/OS<br/>![Mesosphere DC/OS 로고](./media/image8.png) |  Mesosphere Enterprise DC/OS(Apache Mesos 기반)는 컨테이너 및 분산 응용 프로그램을 실행하기 위한 프로덕션 지원 플랫폼입니다. <br /><br /> DC/OS는 클러스터에서 사용할 수 있는 리소스 컬렉션을 추상화하고 이를 기반으로 하여 빌드된 구성 요소에서 이러한 리소스를 사용할 수 있도록 함으로써 작동합니다. Marathon은 일반적으로 DC/OS와 통합된 스케줄러로 사용됩니다. |
| Google Kubernetes<br />![Google Kubernetes 로고](./media/image9.png) | Kubernetes는 클러스터 인프라와 컨테이너 예약에서 기능 오케스트레이션에 이르기까지 다양한 기능을 제공하는 오픈 소스 제품입니다. 사용 하 여 호스트 클러스터 전체에서 배포, 크기 조정 및 응용 프로그램 컨테이너의 작업을 자동화할 수 있습니다. <br /><br /> Kubernetes는 쉽게 관리하고 검색할 수 있도록 응용 프로그램 컨테이너를 논리 단위로 그룹화하는 컨테이너 중심 인프라를 제공합니다. |
| Azure Service Fabric<br />![Azure Service Fabric 로고](./media/image10.png) | [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview)은 응용 프로그램을 빌드하기 위한 Microsoft 마이크로 서비스 플랫폼입니다. 서비스의 [오케스트레이터](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction)이며, 컴퓨터로 구성된 클러스터를 만듭니다. 기본적으로 Service Fabric 배포 하 고 프로세스에 따라 서비스를 활성화 하지만 Service Fabric에서 Docker 컨테이너 이미지에 서비스를 배포할 수 있습니다. 더 중요 한 혼합할 수 있습니다 서비스 프로세스에서 동일한 응용 프로그램 컨테이너의 서비스를 사용 하 여. <br /><br /> 2017 년 5 월을 기준으로 Service fabric Docker 컨테이너로 배포 서비스를 지 원하는 기능은 미리 보기 상태에서입니다. <br /><br /> 사용 하 여 다양 한 방법으로 Service Fabric 서비스를 개발할 수 있습니다 합니다 [Service Fabric 프로그래밍 모델](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) 배포 하는 데 [게스트 실행 파일](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-existing-app) 컨테이너 외에도 합니다. Service Fabric 지원 같은 규범적인 응용 프로그램 모델 [상태 저장 서비스](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) 하 고 [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction)합니다.

## <a name="using-container-based-orchestrators-in-azure"></a>Azure에서 컨테이너 기반 오 케 스트레이 터를 사용 하 여

여러 클라우드 공급 업체는 Docker 컨테이너 지원 및 Docker 클러스터 / 오케스트레이션 지원을, Azure, Amazon EC2 Container Service 및 Google Container Engine을 포함 하 여 제공 합니다. Azure는 다음 섹션에 설명 된 대로 Azure 컨테이너 서비스를 통해 클러스터 및 오 케 스트레이 터 지원을 Docker를 제공 합니다.

다른 선택도 Docker Linux 및 Windows 컨테이너에 기반을 지 원하는 Azure Service Fabric을 사용 하는 것입니다. Service Fabric은 Azure 또는 다른 클라우드 뿐만 [온-프레미스](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere)합니다.

## <a name="using-azure-container-service"></a>Azure Container Service 사용

Docker 클러스터는 여러 Docker 호스트를 풀링하고 단일 가상 Docker 호스트로 공개하여 여러 컨테이너를 클러스터에 배포할 수 있습니다. 클러스터는 확장성 및 상태 등 모든 복잡 한 관리 작업을 처리 합니다. 그림 4-7 Container Service에 구성 된 응용 프로그램에 대 한 Docker 클러스터 매핑되는 방법을 나타냅니다.

컨테이너 서비스 만들기, 구성 및 컨테이너 화 된 응용 프로그램을 실행 하도록 미리 구성 된 Vm의 클러스터 관리를 단순화 하는 방법을 제공 합니다. 인기 있는 오픈 소스 예약 및 오케스트레이션 도구의 최적화 된 구성을, Container Service를 사용 하면 기존 기술을 사용 하거나 크고 확장 배포 및 컨테이너 기반 관리에 대 한 커뮤니티 전문 본문에는 기능 Azure에서 응용 프로그램입니다.

Container Service는 인기 있는 Docker 클러스터링 오픈 소스 도구 및 기술의 구성을 Azure에 맞게 최적화 합니다. 컨테이너와 응용 프로그램 구성 모두에 이식성을 제공하는 개방형 솔루션을 얻을 수 있습니다. 사용자가 크기, 호스트 수, 오케스트레이터 도구를 선택하고, Container Service에서 다른 모든 작업을 처리합니다.

Container Service Docker 이미지를 사용 하 여 응용 프로그램 컨테이너가 완전히 이식 가능한 지 확인. DC/OS, Kubernetes 및 Docker Swarm과 같은 오픈 소스 오케스트레이션 플랫폼의 선택한 이러한 응용 프로그램 수천 또는 수만 개의 컨테이너로 확장할 수 있도록 지원 합니다.

Azure Container Service를 사용 하 여 오케스트레이션 계층에 포함 되는 응용 프로그램 이식성을 유지 하면서 Azure의 엔터프라이즈급 기능을 활용을 걸릴 수 있습니다.

![](./media/image11.png)

그림 4-7: Azure Container Service에서 선택할 수 있는 클러스터링

그림 4-8에서와 같이 Container Service DC/OS, Kubernetes 또는 Docker Swarm을 배포 하기 위해 Azure에서 제공 하는 인프라 이지만 모든 추가 오 케 스트레이 터를 구현 하지 않습니다. 따라서 Container Service는 하지 오 케 스트레이 터를 같이; 컨테이너에 대 한 기존 오픈 소스 오 케 스트레이 터를 활용 하는 인프라 이며

![](./media/image12.png)

Container Service에서 그림 4-8: 오 케 스트레이 터

사용 관점에서 Container Service의 목표는 인기 있는 오픈 소스 도구 및 기술을 사용 하 여 컨테이너 호스팅 환경을 제공 하는입니다. 이를 위해 선택한 오케스트레이터의 표준 API 엔드포인트를 공개합니다. 이러한 끝점을 사용 하 여 해당 엔드포인트와 통신할 수 있는 모든 소프트웨어를 사용할 수 있습니다. 예를 들어, Docker Swarm 엔드포인트의 경우 Docker CLI를 사용 하도록 선택할 수 있습니다. DC/OS의 경우 DC/OS CLI를 사용하도록 선택할 수 있습니다.

### <a name="getting-started-with-container-service"></a>Container Service 시작

Container Service 사용을 시작 하려면 Azure Resource Manager 템플릿을 사용 하 여 Azure portal에서 컨테이너 서비스 클러스터를 배포 또는 [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli)합니다. 사용 가능한 템플릿으로, [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes) 및 [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos)가 있습니다. 빠른 시작 템플릿은 추가 또는 고급 Azure 구성을 포함 하도록 수정할 수 있습니다.

**자세한 내용은** Container Service 클러스터를 Azure 웹 사이트를 배포 하는 방법에 대 한 자세한 내용을 알아보려면 [Azure Container Service 클러스터 배포](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment)합니다.

기본적으로 ACS의 일부로 설치된 소프트웨어에 대해서는 추가 비용이 없습니다. 모든 기본 옵션은 오픈 소스 소프트웨어로 구현됩니다.

컨테이너 서비스는 현재 표준 A, D, DS, G 및 GS 시리즈 Linux Vm에서 Azure에 대 한 합니다. 다른 기본 인프라 리소스 사용, 저장소 및 네트워킹과 같은 뿐만 아니라 선택 계산 인스턴스에 대해서만 요금이 청구 됩니다. 컨테이너 서비스에 대 한 증분 비용이 없습니다 자체 가지.

### <a name="additional-resources"></a>추가 자료

다음은 추가 정보를 찾을 수 있는 위치:

-   Docker 컨테이너 호스팅 솔루션 Container Service를 사용 하 여 소개:  
    https://docs.microsoft.com/azure/container-service/kubernetes/container-service-intro-kubernetes>

-   Docker Swarm 개요:  
    <https://docs.docker.com/swarm/overview/>

-   Swarm 모드 개요:  
    <https://docs.docker.com/engine/swarm/>

-   Mesosphere DC/OS 개요:    
    <https://docs.mesosphere.com/1.7/overview/>

-   Kubernetes (공식 사이트):  
    <https://kubernetes.io/>

## <a name="using-service-fabric"></a>Service Fabric을 사용 하 여

Service Fabric 서비스를 제공 하는 보통 모놀리식 스타일 인 "box" 제품 제공에서 Microsoft의 전환에서 발생 합니다. 빌드 및 Azure SQL Database, Azure Document DB, Azure Service Bus 또는 Cortana의 백 엔드와 같은 규모가 큰 대규모 서비스 운영 경험을 Service Fabric 기반 만들었습니다. 점점 더 많은 서비스가 도입됨에 따라 플랫폼은 시간이 지날수록 향상되었습니다. 중요한 점은 Service Fabric은 Azure뿐만 아니라 독립 실행형 Windows Server 배포에서도 실행되어야 한다는 것입니다.

Service Fabric의 목적은 구축 하 고 서비스를 실행 하 고 팀을 마이크로 서비스 접근 방식을 사용 하 여 비즈니스 문제를 해결할 수 있도록 인프라 리소스를 효율적으로 활용 하 여 어려운 문제를 해결 하는 것입니다.

Service Fabric은 마이크로 서비스 접근 방식을 사용하는 응용 프로그램을 빌드하는 데 도움이 되는 두 가지 폭넓은 영역을 제공합니다.

-   실패한 서비스를 배포, 확장, 업그레이드, 검색 및 다시 시작하고 서비스 위치를 검색하며 상태를 관리하고 상태를 모니터링하는 시스템 서비스를 제공하는 플랫폼. 이러한 시스템 서비스에 이전에 설명한 마이크로 서비스의 특징을 많이 제공 된 적용.

-   마이크로 서비스로 응용 프로그램을 빌드하는 데 도움이 되는 프로그래밍 API 또는 프레임워크: [Reliable Actor 및 Reliable Service](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). 물론 마이크로 서비스를 구축하는 코드를 선택할 수는 있지만 이러한 API를 사용하면 작업이 더 간단해지며 플랫폼과 보다 자세히 통합할 수 있습니다. 이러한 방식으로 상태 및 진단 정보를 얻을 수 있거나 신뢰할 수 있는 상태 관리를 이용할 수 있습니다.

Service Fabric은 서비스 구축하는 방법과 관련하여 제약이 없으며 모든 기술을 사용할 수 있습니다. 단, 마이크로 서비스를 보다 쉽게 구축할 수 있도록 해주는 기본 제공 프로그래밍 API가 제공됩니다.

그림 4-9 만들고 간단한 프로세스 또는 Docker 컨테이너와 Service Fabric에서 마이크로 서비스를 실행 하는 방법을 보여 줍니다. 동일한 Service Fabric 클러스터 내에서 컨테이너 기반 마이크로 서비스와 프로세스 기반 마이크로 서비스를 함께 사용할 수도 있습니다.

![](./media/image13.png)

그림 4-9: 프로세스 또는 Azure Service Fabric에서 컨테이너와 마이크로 서비스 배포

Linux 및 Windows 호스트를 기반으로 하는 Service Fabric 클러스터는 Docker Linux 컨테이너와 Windows 컨테이너를 실행할 수 있습니다.

**자세한 내용은** Azure 웹 사이트에서 Service fabric에서 컨테이너 지원에 대 한 최신 정보에 대 한 읽기 [Service Fabric 및 컨테이너](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview)합니다.

Service Fabric은 다른 논리적 아키텍처 (비즈니스 마이크로 서비스 또는 바인딩된 컨텍스트) 물리적 구현과 정의할 수 있는 플랫폼의 좋은 예입니다. 예를 들어, 구현 하는 경우 [상태 저장 Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) 에 [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview)에 다음 섹션에 도입 된 "[상태 비저장 및 상태 저장 마이크로](#stateless-versus-stateful-microservices), "비즈니스 마이크로 서비스 개념을 여러 물리적 서비스를 사용 해야 합니다.

그림 4-10에서 Service Fabric 상태 저장 신뢰할 수 있는 서비스를 구현 하는 경우 논리적/비즈니스 마이크로 서비스 관점에서 생각에 표시 된 것 처럼 일반적으로 해야 두 가지 서비스 계층을 구현 합니다. 첫 번째는 백 엔드 상태 저장 reliable service, 여러 파티션을 처리 하는 경우 두 번째 프런트 엔드 서비스 또는 다중 파티션 또는 상태 저장 서비스 인스턴스 간에 라우팅 및 데이터 집계를 담당 게이트웨이 서비스입니다. 또한 Gateway 서비스는 Service Fabric과 함께 사용 하면 백 엔드 서비스에 액세스 하는 재시도 루프를 사용 하 여 클라이언트 쪽 통신을 처리 [역방향 프록시](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy)합니다.

![](./media/image14.png)

Service Fabric에서 여러 상태 저장 및 상태 비저장 서비스를 사용 하 여 그림 4-10: 비즈니스 마이크로 서비스

어떤 경우든, Service Fabric 상태 저장 Reliable Services를 사용하면, 일반적으로 여러 물리적 서비스로 구성된 논리적 또는 비즈니스 마이크로 서비스(바인딩된 컨텍스트)가 있습니다. 이러한, 게이트웨이 서비스 및 Partition 서비스의 각 그림 4-10에서와 같이 ASP.NET Web API 서비스로 구현할 수 있습니다.

Service Fabric에서는 오케스트레이터 또는 클러스터의 패키징 및 배포 단위인 [Service Fabric 응용 프로그램](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model)으로 서비스 그룹을 그룹화 및 배포할 수 있습니다. 따라서 Service Fabric 응용 프로그램에 매핑될 수이 자치 비즈니스 및 논리적 마이크로 서비스 경계 또는 바인딩된 컨텍스트에 합니다.

### <a name="service-fabric-and-containers"></a>Service Fabric 및 컨테이너

Service Fabric에서 컨테이너와 관련 하 여도 서비스를 Service Fabric 클러스터 내에서 컨테이너 이미지로 배포할 수 있습니다. 그림 4-11 서비스 당 하나의 컨테이너만 됩니다 시간의 대부분을 보여 줍니다.

![](./media/image15.png)

Service Fabric에서 여러 서비스 (컨테이너)를 사용 하 여 그림 4-11: 비즈니스 마이크로 서비스

그러나 소위 "사이드카" 컨테이너 (논리적 서비스의 일부로 함께 배포 해야 하는 두 개의 컨테이너)는 Service Fabric에서 가능한도. 중요한 것은 비즈니스 마이크로 서비스가 여러 응집 요소 주위의 논리적 경계라는 것입니다. 대부분의 경우에서 단일 데이터 모델을 사용 하 여 단일 서비스 수 있습니다 하지만 일부 다른 경우에서 실제 여러 서비스에도 있을 수 있습니다.

이 문서의 작성 (2017 년 4 월) 기준으로 Service Fabric에 배포할 수 없습니다 컨테이너에서 상태 저장 Reliable Services SF-게스트 컨테이너, 상태 비저장 서비스 또는 행위자 서비스만 컨테이너를 배포할 수 있습니다. 그러나 프로세스의 서비스와 동일한 Service Fabric 응용 프로그램을 컨테이너의 서비스를 혼합할 수 있습니다 그림 4-12에 나와 있는 것 처럼.

![](./media/image16.png)

컨테이너 및 상태 저장 서비스를 사용 하 여 Service Fabric 응용 프로그램에 매핑된 그림 4-12: 비즈니스 마이크로 서비스

지원은 또한 Linux 또는 Windows 컨테이너에서 Docker 컨테이너 사용 하는지에 따라 달라 집니다. Service Fabric에서 컨테이너에 대 한 지원이 곧 출시 될 릴리스에서 확장 될 예정입니다. Azure 웹 사이트에서 Service fabric에서 컨테이너 지원에 대 한 최신 뉴스 읽기 [Service Fabric 및 컨테이너](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview)합니다.

## <a name="stateless-versus-stateful-microservices"></a>상태 비저장 및 상태 저장 마이크로 서비스

앞에서 설명한 대로, 각 마이크로 서비스(논리적 바인딩된 컨텍스트)는 고유한 도메인 모델(데이터 및 논리)을 소유해야 합니다. 상태 비저장 마이크로 서비스의 경우 데이터베이스 외부 SQL Server와 같은 관계형 옵션 또는 MongoDB 또는 Azure DocumentDB와 같은 NoSQL 옵션 사용 됩니다.

하지만 서비스 자체 수도 있습니다 상태 저장 마이크로 서비스 내에서 데이터 상주 하는 것을 의미 하는 합니다. 이 데이터 드라이브에 저장 및 다른 노드에 복제 뿐 아니라 같은 서버에 있지만, 메모리에서 마이크로 서비스 프로세스 내에 존재할 수 있습니다. 그림 4-13에는 여러 가지 방법을 보여 줍니다.

![](./media/image17.png)

그림 4-13: 상태 비저장 및 상태 저장 마이크로 서비스

상태 비저장 방법을 완벽 하 게 유효 하며 기존의 잘 알려진 패턴과 유사 하기 때문에 상태 저장 마이크로 서비스 보다 구현 하기가 쉽습니다. 그러나 상태 비저장 마이크로 서비스는 프로세스와 데이터 원본 간에 대기 시간을 둡니다. 또한 캐시 및 대기열을 추가하여 성능을 향상시키려는 경우 더욱 복잡해집니다. 결과적으로 너무 많은 계층을 가진 복잡한 아키텍처로 끝날 수 있습니다.

반대로 [상태 저장 마이크로 서비스](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) 도메인 논리와 데이터 간의 대기 시간이 없기 때문에 고급 시나리오에서 뛰어납니다. 대량의 데이터 처리, 게임 백 엔드, 서비스 및 기타 대기 시간이 짧은 시나리오 빠른 액세스에 대 한 로컬 상태를 제공 하는 상태 저장 서비스의 모든 혜택으로 데이터베이스입니다.

상태 비저장 및 상태 저장 서비스는 보완적입니다. 예를 들어 여러 파티션으로 상태 저장 서비스를 구분할 수 있습니다. 이러한 파티션에 액세스하려면 파티션 키를 기반으로 각 파티션의 주소를 지정하는 방법을 알고 있는 게이트웨이 서비스로 작동하는 상태 비저장 서비스가 필요할 수 있습니다.

상태 저장 서비스에는 단점이 있습니다. 쉽게 확장할 수 있도록 하는 복잡성 수준을 내포 합니다. 일반적으로 외부 데이터베이스 시스템에 의해 구현되는 기능은 상태 저장 마이크로 서비스 간 데이터 복제 및 데이터 분할과 같은 작업을 위해 처리되어야 합니다. 그러나이 오 케 스트레이 터와 같은 영역 중 하나입니다 [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) 사용 하 여 해당 [상태 저장 reliable services](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) 가장 도움이-개발 및 상태 저장의 수명 주기를 간소화 하 여 마이크로 서비스를 사용 하 여 [Reliable Services API](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) 하 고 [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction)합니다.

상태 저장 서비스를 허용하고 Actor 패턴을 지원하며 비즈니스 논리와 데이터 간의 내결함성과 대기 시간을 향상시키는 기타 마이크로 서비스 프레임워크로는 Microsoft Research의 Microsoft [Orleans](https://github.com/dotnet/orleans) 및 [Akka.NET](https://getakka.net/)이 있습니다. 두 프레임워크는 현재 Docker에 대한 지원을 개선 중입니다.

Docker 컨테이너 자체는 상태 비저장입니다. 상태 저장 서비스를 구현하려면 앞에서 언급한 추가 규범 및 상위 수준 프레임워크 중 하나가 필요합니다. 그러나이 문서의 작성 시점 현재 Service Fabric에서 상태 저장 서비스를 일반 마이크로 서비스로 컨테이너로 지원 되지 않습니다. 컨테이너에서 지 원하는 신뢰할 수 있는 서비스는 Service Fabric의 향후 버전에서 사용할 수 있습니다.


>[!div class="step-by-step"]
[이전](soa-applications.md)
[다음](docker-apps-development-environment.md)
