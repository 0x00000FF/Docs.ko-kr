---
title: 하이브리드 클라우드 시나리오로 마이그레이션
description: Azure 클라우드 및 Windows 컨테이너와 기존.NET 응용 프로그램을 최신식 | 하이브리드 클라우드 시나리오로 마이그레이션
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 8885ee8fce4f8c11c14ee8936f3ee0ffd89ece04
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a>하이브리드 클라우드 시나리오로 마이그레이션

일부 조직에서 및 기업 규정 또는 자신의 정책으로 인해 다른 공용 클라우드 또는 공용 클라우드에 Microsoft Azure와 같은 응용 프로그램의 일부를 마이그레이션할 수 없습니다. 그러나 어떤 조직에서 몇 가지 공용 클라우드 및 다른 응용 프로그램이 온-프레미스에서 응용 프로그램의 장점을 활용할 수 있음을 가능성이 높습니다. 하지만 혼합된 환경 지나치게 복잡 하 게 서로 다른 플랫폼 및 공용 클라우드 및 온-프레미스 환경에서에서 사용 된 기술으로 인해 환경에서 발생할 수 있습니다.

Microsoft는 가장 적합 한 하이브리드 클라우드 솔루션 제공을 기존 자산을 최적화할 수 있습니다 하나 온-프레미스 및 공용 클라우드에서 Azure 하이브리드 클라우드에 일관성을 보장 하는 동안 합니다. 기존 기술을 최대화 수 있으며 클라우드 또는 온-프레미스에서 Azure 스택 (온-프레미스) 및 Azure (공용 클라우드) 덕분에 실행할 수 있는 앱을 개발 하는 유연 하 고 통합 된 접근 방식을 가져올 수 있습니다.

보안에 관한, 관리 및 보안을 중앙 집중화할 수 있습니다 하이브리드 클라우드에 있습니다. Single sign on 온-프레미스에 제공 하 여 클라우드로 데이터 센터에서 모든 자산에 대 한 제어를 가져올 수 있으며 클라우드 앱. Active Directory 하이브리드 클라우드를 확장 하 고 id 관리를 사용 하 여이 작업을 수행할 합니다.

마지막으로 배포 하 고 분석 데이터 원활 하 게, 클라우드 및 온-프레미스 자산에 대 한 동일한 쿼리 언어를 사용 하 고 있습니다 분석 워크 로드와 해당 소스에 관계 없이 데이터를 보강 하기 위해 Azure에서 학습 깊습니다 적용 합니다.

## <a name="azure-stack"></a>Azure Stack

Azure 스택은 조직의 데이터 센터에서 Azure 서비스를 제공할 수 있는 하이브리드 클라우드 플랫폼입니다. Azure 스택 가장자리와 연결 되지 않은 환경 또는 특정 보안 및 규정 준수 요구 사항을 충족와 같은 주요 시나리오에 최신 응용 프로그램에 대 한 새 옵션을 지원 하도록 설계 되었습니다.

그림 4-13 Microsoft에서 제공 하는 true 하이브리드 클라우드 플랫폼의 개요를 보여 줍니다.

![Azure 스택 및 Azure로 Microsoft 하이브리드 클라우드 플랫폼](./media/image13.jpg)

> **그림 4-13입니다.** Azure 스택 및 Azure로 Microsoft 하이브리드 클라우드 플랫폼

Azure 스택 요구 사항에 맞게 두 가지 배포 옵션에서 제공 됩니다.

-   Azure 스택 시스템 통합

-   Azure 스택 개발 키트

### <a name="azure-stack-integrated-systems"></a>Azure 스택 시스템 통합

Azure 스택 통합 시스템은 Microsoft 및 하드웨어 파트너의 파트너 관계를 통해 제공 됩니다. 파트너 관계 관리에서 단순성와 균형을 이룹니다 클라우드 속도 혁신을 제공 하는 솔루션을 만듭니다. Azure 스택 하드웨어 및 소프트웨어의 통합된 된 시스템을 제공 하는, 때문에 여전히 클라우드에서 혁신을 채택 하는 동안 적절 한 양의 유연성 및 제어를 가져옵니다. Azure 스택 통합 시스템 4 개에서 12 노드에 크기 하 고 공동으로 하드웨어 파트너 및 Microsoft에서 지원 됩니다. 사용 하 여 Azure 스택 프로덕션 작업에 대 한 새 시나리오를 구현 하는 시스템을 통합 합니다.

### <a name="azure-stack-development-kit"></a>Azure 스택 개발 키트

Microsoft Azure 스택 개발 키트는 단일 노드 배포 Azure 스택, 평가 하 고 Azure 스택에 대 한 자세한 내용은 사용할 수 있습니다. 여기서 Api를 사용 하 여 개발할 수 있습니다 및 Azure와 일치 하는 도구는 개발자 환경으로 Azure 스택 개발 키트를 사용할 수도 있습니다. Azure 스택 개발 키트는 프로덕션 환경으로 사용할 수 없습니다.

### <a name="additional-resources"></a>추가 자료

-   **Azure 하이브리드 클라우드**

    [https://www.microsoft.com/cloud-platform/hybrid-cloud](https://www.microsoft.com/cloud-platform/hybrid-cloud)

-   **Azure Stack**

    [https://azure.microsoft.com/overview/azure-stack/](https://azure.microsoft.com/overview/azure-stack/)

-   **Windows 컨테이너에 대 한 active Directory 서비스 계정**

    [https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts)

-   **Active Directory를 지 원하는 컨테이너 만들기**

    [https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/](https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/)

-   **Azure 하이브리드 혜택 라이선스**

    [https://azure.microsoft.com/pricing/hybrid-use-benefit/](https://azure.microsoft.com/pricing/hybrid-use-benefit/)

>[!div class="step-by-step"]
[이전](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[다음](../walkthroughs-technical-get-started-overview.md)
