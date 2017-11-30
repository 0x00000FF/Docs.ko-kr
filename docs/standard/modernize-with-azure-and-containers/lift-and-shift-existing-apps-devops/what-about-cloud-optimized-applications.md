---
title: "클라우드 액세스에 최적화 된 응용 프로그램은 어떻습니까?"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 클라우드 액세스에 최적화 된 응용 프로그램은 어떻습니까?"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 40d493196f12af7a5337c47ed85581d933374396
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="what-about-cloud-optimized-applications"></a>클라우드 액세스에 최적화 된 응용 프로그램은 어떻습니까?

하지만 클라우드 액세스에 최적화 된 및 [클라우드 네이티브](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) 응용 프로그램이 주 목적은 되지 않습니다.이 가이드의이 현대화 maturity 수준의 이해 클라우드 DevOps 지원에서 구분 하는 데 도움이 됩니다.

그림 4-3 응용 프로그램 현대화 완성도 수준에서 클라우드 액세스에 최적화 된 앱을 배치:

![클라우드 액세스에 최적화 된 응용 프로그램을 위치 지정](./media/image3.png)

> **그림 4-3입니다.** 클라우드 액세스에 최적화 된 응용 프로그램을 위치 지정

클라우드 액세스에 최적화 된 현대화 성장 수준에는 일반적으로 개발 투자가 필요합니다. 일반적으로 클라우드 액세스에 최적화 된 수준으로 이동를 응용 프로그램 비용을 줄이고 민첩성을 가능한 한 현대화 할 비즈니스 요구 사항에 따라 진행 되 고 이점은 경합 합니다. 이러한 목표는 PaaS 클라우드 사용을 최대화 하 여 수행 됩니다. 뿐만 아니라 DBaaS, CaaS, 및 저장소 서비스 (STaaS)로 있지만 응용 프로그램 및 서비스는 PaaS를 마이그레이션하여 Azure 앱 서비스와 같은 플랫폼을 계산 하는 같은 PaaS 서비스를 사용 하거나 orchestrators를 사용 하 여 의미 합니다.

이러한 유형의 현대화에서는 일반적으로 리팩터링 또는에 최적화 된 새 코드를 작성 해야 클라우드 PaaS 플랫폼 (Azure 앱 서비스에 대 한 유사). 필요할 수 있습니다도 클라우드 환경에 맞게 설계 microservices을 기반으로 하는 클라우드 네이티브 응용 프로그램 모델을 이동 하는 경우에 특히 합니다. 차별화 클라우드 DevOps 지원, 없습니다 재설계 요구 하 고 새 코드가 없는에 비해 요소 키입니다.

경우에 따라 더 많은 고급 만들 수 있습니다 [클라우드 네이티브](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) 민첩성와 함께 개선 하 고 모놀리식 아키텍처에서 달성 하기 어려운 제한을 확장할 수 있는 microservices 아키텍처를 기반으로 응용 프로그램 온-프레미스 환경에 배포 합니다.

그림 4-4에는 클라우드에 최적화 된 모델을 사용 하는 경우 배포할 수 있는 응용 프로그램의 유형을 표시 합니다. 두 개의 기본 선택 항목 최신 웹 응용 프로그램과 클라우드 네이티브 응용 프로그램 해야합니다.

> ![클라우드 액세스에 최적화 된 수준에서 응용 프로그램 형식](./media/image4.png)
>
> **그림 4-4입니다.** 클라우드 액세스에 최적화 된 수준에서 응용 프로그램 형식

인공 인텔리전스 (AI), 기계 학습 (ML) 및 IoT와 같은 다른 서비스를 추가 하 여 기본 웹 앱 및 클라우드-네이티브 앱을 확장할 수 있습니다. 이러한 서비스 중 하나는 확장 가능한 클라우드 액세스에 최적화 된 방법 중 하나를 사용할 수 있습니다.

클라우드 액세스에 최적화 된 수준에서 응용 프로그램의 기본적인 차이점은 응용 프로그램 아키텍처입니다. [클라우드-네이티브](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) 정의 따르면 microservices을 기반으로 하는 응용 프로그램의 응용 프로그램은 합니다. 클라우드-네이티브 앱에는 특별 한 아키텍처, 기술 및 플랫폼에서 모놀리식 웹 응용 프로그램이 나 기존 N 계층 응용 프로그램에 비해 필요 합니다.

Microservices 사용 하지 않는 새 응용 프로그램을 만들기는 것이 좋습니다. Microservices 기반 접근 방식을 사용자의 요구를 초과할 수 있습니다는 새롭고 현대적인 여전히 많은 시나리오가 있습니다. 경우에 따라 수 하 려 할 간단 모놀리식 웹 응용 프로그램을 만들거나 정교 하지 않은 서비스 N 계층 응용 프로그램에 추가 합니다. 이러한 경우에 사용할 수 있습니다 여전히 전체 클라우드의 Azure 앱 서비스에서 제공 하는 것과 같은 PaaS 기능입니다. 여전히 제한으로 유지 관리 작업을 줄입니다.

또한 새 코드를 작성 하기 때문에 클라우드 액세스에 최적화 된 시나리오 (응용 프로그램의 전체 또는 부분 하위 시스템에 대 한)에서 새 코드를 만들 때 사용 해야 최신 버전의.NET ([.NET Core](https://docs.microsoft.com/dotnet/core/) 및 [ASP.NET Core](https://docs.microsoft.com/aspnet/core/), 특히). .NET Core는 간결 하 고 빠른 프레임 워크 이므로 microservices 및 컨테이너를 만드는 경우 특히 유용 합니다. 작은 메모리 사용 공간 및 컨테이너에 대 한 빠른 시작 얻게 됩니다 하 고 응용 프로그램 성능이 잠금 해제 됩니다. 이 방법은 microservices 및 컨테이너의 요구 사항을 완벽 하 게 맞는 하 고는 플랫폼 간 프레임 워크-되 고 Linux, Windows Server 및 Mac (Mac 개발 환경)에서 동일한 응용 프로그램을 실행할 수의 이점을 얻을 수 있습니다.

## <a name="cloud-native-applications-with-cloud-optimized-applications"></a>클라우드 액세스에 최적화 된 응용 프로그램과 클라우드 네이티브 응용 프로그램

[클라우드-네이티브](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) 광범위 하 고 중요 한 응용 프로그램에 대 한 보다 고급 또는 완성도 높은 상태입니다. 클라우드-네이티브 응용 프로그램 아키텍처 및 디자인 하 여 기존 응용 프로그램 현대화 대신 처음부터 새로 만든에 일반적으로 필요 합니다. 클라우드-네이티브 응용 프로그램 및 간단한 클라우드 액세스에 최적화 된 웹 응용 프로그램에 PaaS 배포의 주요 차이점은 클라우드 네이티브 접근 방식에서 microservices 아키텍처를 사용 하도록 권장 합니다. 클라우드 액세스에 최적화 된 앱 모놀리식 웹 앱 또는 N 계층 응용 프로그램을 Azure 앱 서비스 같은 PaaS 서비스는 클라우드에 배포할 수 있습니다.

[12 단계 앱](https://12factor.net/) (microservices 방법과 밀접 한 관련이 있는 패턴의 컬렉션)도 것으로 간주 됩니다에 대 한 요구 사항 [클라우드 네이티브](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) 응용 프로그램 아키텍처입니다.

[클라우드 네이티브 컴퓨팅 Foundation (CNCF)](https://www.cncf.io/) 클라우드 네이티브 조항의 기본 프로모터 됩니다. Microsoft는는 [는 CNCF 소속](https://azure.microsoft.com/blog/announcing-cncf/)합니다.

샘플 정의 대 한 클라우드 네이티브 응용 프로그램의 특성에 대 한 자세한 내용은 Gartner 문서를 참조 [설계 및 클라우드 네이티브 응용 프로그램을 디자인 하는 방법을](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications)합니다. 클라우드-네이티브 응용 프로그램을 구현 하는 방법에 대 한 Microsoft의 특정 지침에 대 한 참조 [.NET microservices: 화 된.NET 응용 프로그램에 대 한 아키텍처](https://aka.ms/microservicesebook)합니다.

전체 응용 프로그램을 마이그레이션할 경우 고려해 야 할 가장 중요 한 요소는 [클라우드 네이티브](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) 모델은 다시 microservices 기반 아키텍처를 설계 해야 합니다. 이 관련 된 큰 리팩터링 프로세스로 인해 개발에 많은 투자를 명확 하 게 해야합니다. 이 옵션은 일반적으로 새로운 수준의 확장성 및 장기 유연성을 필요로 하는 중요 응용 프로그램에 대 한 선택 됩니다. 하지만 microservices 몇 개의 새로운 시나리오에 대 한 추가 하 여 클라우드 네이티브 쪽으로 이동 하 고 결국 microservices로 완벽 하 게 응용 프로그램을 리팩터링할 수 없습니다. 일부 시나리오에 가장 적합 한 옵션은 하는 증분 방식입니다.

## <a name="what-about-microservices"></a>Microservices 어떻습니까? 

조직에 대 한 클라우드 네이티브 응용 프로그램을 고려할 때는 microservices 및 작동 방법을 이해 하는 것이 중요 합니다.

Microservices 아키텍처는 처음부터 새로 또는 기존 응용 프로그램을 개발할 때 생성 되는 응용 프로그램에 사용할 수 있는 고급 방법을 (온-프레미스 또는 클라우드 DevOps 준비 앱) 클라우드 네이티브 응용 프로그램으로 합니다. 몇 가지 microservices 새로운 microservices 패러다임에 대 한 자세한 내용은 기존 응용 프로그램을 추가 하 여 시작할 수 있습니다. 하지만 설계자와 특히 이러한 유형의 아키텍처 방법에 대 한 코드를 필요 명확 하 게 합니다.

그러나 microservices 모든 새로운 또는 최신 응용 프로그램에 대 한 필수있지 않습니다. 모든 응용 프로그램을 만들려면 단일, 가장 좋은 방법은 되지 않게 차단 및 Microservices "매직 bullet" 하지 않습니다. Microservices 시기와 방법을 사용 하 여 빌드하는 데 필요한 응용 프로그램 종류에 따라 달라 집니다.

Microservices 아키텍처 자치 서비스의 형태로 독립적인 여러, 하위 시스템을 기반으로 하는 중요 한 응용 프로그램의 배포 및 대규모 또는 복잡 한 선호 되는 방법은 해지고 있습니다. Microservices 기반 아키텍처에서는 응용 프로그램을 배포 하 고 크기가 조정 독립적으로 개발, 테스트, 버전이 지정 될 수 있는 서비스의 컬렉션으로 만들어집니다. 이 모든 관련, 자치 데이터베이스당 마이크로 서비스를 포함할 수 있습니다.

.NET Core를 사용 하 여 구현할 수 있는 microservices 아키텍처에 자세히, 다운로드 가능한 PDF 전자책을 참조 하십시오. [.NET microservices: 화 된.NET 응용 프로그램에 대 한 아키텍처](https://aka.ms/microservicesebook)합니다. 이 가이드는 또한 사용할 수는 [온라인](https://docs.microsoft.com/dotnet/standard/microservices-architecture/)합니다.

하지만 microservices이 강력한 기능 독립 배포, 강력한 하위 시스템 경계 및 기술 다양성 제공 하는 시나리오 에서도-많은 새로운 문제도 발생 시킵니다. 조각화 하 고 독립적인 데이터 모델과; 같은 분산된 응용 프로그램 개발 관련 된 문제 달성 microservices; 간 복원 가능한 통신 결과적 일관성;에 대 한 필요성 및 작업의 복잡성을 추가 합니다. Microservices는 복잡성 기존의 모놀리식 응용 프로그램에 비해 더 높은 수준의 소개 합니다.

Microservices 아키텍처의 복잡성 때문에 특정 응용 프로그램 종류 및 특정 시나리오는 마이크로 서비스 기반 응용 프로그램에 적합 합니다. 여기에 포함 하는 여러 크고 복잡 한 응용 프로그램 하위 시스템을 발전 합니다. 이러한 경우에 더 복잡 한 소프트웨어 아키텍처 장기 민첩성을 향상할된 및 보다 효율적인 응용 프로그램 유지 관리에 대 한 투자 이므로 합니다. 그러나 덜 복잡 한 시나리오에 대 한 좋을 수도 있습니다는 모놀리식 응용 프로그램 접근 방식으로 계속 하 나 간단한 N 계층 접근 합니다.

마지막으로,이 개념에 대 한 반복 되 고 위험이 있는 서는 안 보면 microservices로 응용 프로그램에서 사용 하 여 "올인원 하거나 전혀 nothing*.*" 확장 하 고 새로 만들기, microservices 기반 소규모 시나리오를 추가 하 여 기존 모놀리식 응용 프로그램을 개발할 수 있습니다. microservices 아키텍처 접근 방식으로 작업을 시작 하는 처음부터 다시 시작할 필요가 없습니다. 사실, 새로운 시나리오를 추가 하 여 기존 모놀리식 또는 N 계층 응용 프로그램을 사용 하 여도 발전 하는 것이 좋습니다. 결국 응용 프로그램 자치 구성 요소 또는 microservices을 나눌 수 있습니다. 진화 단계별 microservices 방향의 모놀리식 응용 프로그램을 시작할 수 있습니다.

## <a name="when-to-use-azure-app-service-for-modernizing-existing-net-apps"></a>현대화 기존.NET 응용 프로그램에 대 한 Azure 앱 서비스를 사용 하는 경우

웹 응용 프로그램은.NET Framework를 사용 하 여 개발 된 때문에 클라우드 액세스에 최적화 된 완성도 수준으로 기존 ASP.NET 웹 응용 프로그램을 최신식 Windows 및 대부분의 경우 인터넷 정보 서버 (IIS)에서 주요 종속성 됩니다. 사용할 수 있으며 Windows 및 IIS 기반 응용 프로그램을 배포에 직접 배포 하거나 [Azure 앱 서비스](https://docs.microsoft.com/azure/app-service/app-service-value-prop-what-is) 기준 먼저 Windows 컨테이너를 사용 하 여 응용 프로그램 containerizing 또는 합니다. Containerizing, 하는 경우 응용 프로그램을 배포 하거나 Windows 컨테이너 (VM 기반) 호스트 또는 클러스터의 Windows 컨테이너를 지 원하는 Azure 서비스 패브릭으로 합니다.

Windows 컨테이너를 사용 하면 컨테이너 화의 혜택을 모두 가져옵니다. 환경 문제 (준비, 개발/테스트, 프로덕션)에 대 한 마찰 줄이고 민첩성에 전달 하 고 응용 프로그램 배포. 다음 단원에서 컨테이너를 사용 하 여 얻을 수 있는 이점에 대 한 좀 더 자세히 이동 합니다.

이 가이드를 작성할 당시 Azure 앱 서비스는 Windows 컨테이너를 지원 하지 않습니다. Linux 용 컨테이너 지원지 않습니다. 다음 질문에 "선택 하려면 어떻게 합니까 Azure 앱 서비스와 Windows 컨테이너 간의?" 될 수 있으므로

기본적으로, Azure 앱 서비스 응용 프로그램에 대해 작동 하는 경우 모든 서버 또는 응용 프로그램 서비스를 사용 하는 경로 차단 하는 사용자 지정 종속성이 없는 응용 프로그램 서비스를 기존.NET 웹 응용 프로그램 마이그레이션해야 합니다. 응용 프로그램 유지 관리 하는 가장 쉬운 가장 효율적인 방법입니다. Azure에서 응용 프로그램이 포함 됩니다는 간단한 유지 관리 경로 DBaaS, CaaS, STaaS 같은 PaaS 인프라에서이 점으로 인해 합니다.

그러나 응용 프로그램에 서버 또는 Azure 앱 서비스에서 지원 되지 않는 사용자 지정 종속성을 Windows 컨테이너를 기반으로 하는 옵션을 고려해 야 할 수 있습니다. 서버 또는 사용자 지정 종속성의 예로 제 3 자 소프트웨어 또는.msi 파일 서버에 설치 해야 하는 있지만 Azure 앱 서비스에서 지원 되지 않습니다. 또 다른 예로 전역 어셈블리 캐시 (GAC) 또는 COM에서 어셈블리를 사용할 때와 같이 Azure 앱 서비스에서 지원 되지 않는 다른 서버 구성 / COM + 구성 요소입니다. Windows 컨테이너 이미지 덕분에 동일한 "배포 단위입니다."의 사용자 지정 종속성을 포함할 수 있습니다.

또는 Azure 앱 서비스에서 지원 되지 않는 응용 프로그램의 영역을 리팩터링할 수 있습니다. 작업의 볼륨에 따라 리팩터링 필요한 신중 하 게 가치 있는 제공할지 여부를 평가 하는 것입니다.

### <a name="benefits-of-moving-to-azure-app-service"></a>Azure 앱 서비스를 이동 하는 이점

Azure 앱 서비스를 제공 하는 완전히 관리 되는 PaaS 쉽게 비즈니스 프로세스에 의해 지원 되는 웹 앱을 빌드할 수는 있습니다. 응용 프로그램 서비스를 사용 하 여 웹 앱 온-프레미스 유지 관리 및 업그레이드와 관련 된 인프라 관리 비용이 발생 하지 않도록 합니다. 특히, 하드웨어 및 라이선스 비용의 웹 앱 온-프레미스로 실행 잘라냅니다.

웹 응용 프로그램이 Azure 앱 서비스를 마이그레이션하는 데 적합 한 경우 주요 장점은 응용 프로그램을 이동 하는 데 걸리는 시간의 짧은 시간입니다. 앱 서비스는 시작를 매우 쉽게 환경을 제공 합니다.

Azure 앱 서비스 웹 앱을 실행 하는 데 사용할 수 있는 Azure에서 가장 간단한 PaaS 있기 때문에 대부분의 웹 응용 프로그램에 대 한 최선의 선택은 합니다. 배포 및 관리 플랫폼에 통합 되어, 사이트 높은 트래픽 부하를 처리 하도록 신속 하 게 확장할 및 기본 제공 부하 분산 및 트래픽 관리자는 고가용성을 제공 합니다.

도 웹 응용 프로그램을 모니터링 하는 것은 Azure Application Insights를 통해 간단 합니다. Application Insights 무료 앱 서비스와 추가 되며 응용 프로그램에서 특별 한 코드를 작성 합니다. 필요 하지 않습니다. 앱 서비스에서 웹 앱을 실행 하기만 하 고 추가 작업 없이 매력적인 모니터링 시스템을 얻게 됩니다.

앱 서비스와 Azure 웹 응용 프로그램 갤러리 (예: WordPress 또는 Umbraco)에서 많은 오픈 소스 응용 프로그램을 직접도 사용할 수 있습니다 또는 프레임 워크 및 ASP.NET과 같은 원하는 도구를 사용 하 여 새 사이트를 만들 수 있습니다. 앱 서비스 웹 작업 기능을 사용 하면 쉽게 응용 프로그램 서비스 웹 앱을 처리 하는 백그라운드 작업을 추가할 수 있습니다.

Azure 앱 서비스의 웹 응용 프로그램 기능을 사용 하 여 웹 응용 프로그램을 마이그레이션할 경우의 주요 이점은 다음과 같습니다.

-   자동 크기 조정을 하 사용량이 많을 때의 요구를 충족 하 고 시간 이외 비용을 절감 합니다.

-   변경 내용 및 데이터를 보호 하기 위해 자동 사이트 백업을 합니다.

-   고가용성 및 Azure PaaS 플랫폼에서 복구 합니다.

-   배포 슬롯 개발 또는 스테이징 환경을와 여러 사이트 디자인을 테스트 합니다.

-   부하 분산 및 배포 된 서비스 거부 (DDoS) 보호 합니다.

-   사용자를 가장 가까운 지리적 배포도 트래픽 관리 합니다.

그러나 앱 서비스 있을 수 있고 새 웹 앱에 대 한 최선의 선택 수, 기존 응용 프로그램에 대 한 앱 서비스 수 있습니다 적합 하 고 응용 프로그램 종속성 앱 서비스에서 사용할 수 있는 경우에 합니다.

### <a name="additional-resources"></a>추가 리소스

-   **Azure 앱 서비스에 대 한 호환성 분석**  
[https://www.migratetoazure.net/Resources](https://www.migratetoazure.net/Resources)


### <a name="benefits-of-moving-to-windows-containers"></a>Windows 컨테이너를 이동 하는 이점

Windows 컨테이너를 사용 하 여의 주요 장점은 더 안정적이 고 향상 된 배포 환경을 아닌 컨테이너 화 가능한 응용 프로그램에 비해 가질 수 있다는 것입니다. 또한 효과적으로 컨테이너와 현대화 된 응용 프로그램에 두면 응용 프로그램에 대해 다른 여러 플랫폼 및 Windows 컨테이너를 지 원하는 클라우드 준비 있습니다. Windows 컨테이너를 이동 하는 이점은 다음 섹션에서 자세히 다룹니다.

Azure 서비스 패브릭 및 기본 Windows 컨테이너 호스트 (Windows Server 2016 Vm)를 지 원하는 Windows 컨테이너 (2017 중순 현재 일반 공급)에 Azure에서 기본 계산 환경이 표시 됩니다. 이러한 환경에는이 가이드에서 다루는 주요 인프라 시나리오는 합니다.

Windows 컨테이너 Kubernetes, docker는 Docker Swarm 또는 DC/OS와 같은 다른 orchestrators를 배포할 수도 있습니다. 현재 (초기가 2017) Windows 컨테이너를 사용 하기 위한 Azure 컨테이너 서비스의 미리 보기에서 이러한 플랫폼은 합니다.

>[!div class="step-by-step"]
[이전](microsoft-technologies-in-cloud-devops-ready-applications.md)
[다음](how-to-deploy-existing-net-apps-to-azure-app-service.md)
