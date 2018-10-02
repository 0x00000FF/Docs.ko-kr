---
title: WCF Data Services 개발 및 배포
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
ms.openlocfilehash: cf1782eaf54701f0cf93576325b3d46e8bc4d3f1
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48030461"
---
# <a name="develop-and-deploy-wcf-data-services"></a>개발 및 WCF Data Services를 배포 합니다.

이 항목에서는 WCF Data Services 개발 및 배포에 대 한 정보를 제공 합니다. WCF Data Services에 대 한 기본적인 정보를 참조 하세요. [Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md) 하 고 [개요](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)합니다.

## <a name="develop-wcf-data-services"></a>WCF Data Services 개발

WCF Data Services를 지 원하는 데이터 서비스 만들기를 사용 하는 경우는 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]를 개발 하는 동안 다음과 같은 기본 작업을 수행 해야 합니다.

1.  **데이터 모델 정의**

     WCF Data Services는 다양 한 다양 한 런타임에 바인딩된 데이터 형식으로 관계형 데이터베이스에서 데이터 원본에서에서 데이터를 기반으로 데이터 모델을 정의할 수 있도록 데이터 서비스 공급자를 지원 합니다. 자세한 내용은 [데이터 서비스 공급자](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)합니다.

2.  **데이터 서비스 만들기**

     가장 기본적인 데이터 서비스는 <xref:System.Data.Services.DataService%601> 클래스에서 상속하는 클래스를 엔터티 컨테이너의 네임스페이스로 정규화된 이름인 `T` 형식으로 노출합니다. 자세한 내용은 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)의 개발 및 배포에 대한 정보를 제공합니다.

3.  **데이터 서비스 구성**

     기본적으로 WCF Data Services는 엔터티 컨테이너에 의해 노출 되는 리소스에 대 한 액세스를 비활성화 합니다. <xref:System.Data.Services.DataServiceConfiguration> 인터페이스를 사용 하면 리소스에 대 한 액세스를 구성 및 서비스 작업, odata, 지원 되는 버전을 지정 하 고 일괄 처리 동작 또는 반환할 수 있는 엔터티의 최대 수와 같은 서비스 전반적인 기타 동작을 정의 하려면 단일 응답 피드에 합니다. 자세한 내용은 [데이터 서비스 구성](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)합니다.

이 항목에서는 Visual Studio를 사용 하 여 주로 개발 및 데이터 서비스의 배포를 설명 합니다. 데이터를 OData 피드로 노출 하는 것에 대 한 WCF Data Services에서 제공 하는 유연성에 대 한 정보를 참조 하세요 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)합니다.

### <a name="choose-a-development-web-server"></a>개발 웹 서버를 선택 합니다.

WCF 데이터 서비스를 개발 하는 경우는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램 또는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Visual Studio 2015를 사용 하 여 웹 사이트를 개발 하는 동안 데이터 서비스를 실행 하는 웹 서버의 선택할 수 있습니다. 다음 웹 서버 테스트 하 고 로컬 컴퓨터의 데이터 서비스를 디버깅할 수 있도록 Visual Studio와 통합 합니다.

1.  **로컬 IIS 서버**

     IIS(인터넷 정보 서비스)에서 실행되는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램 또는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 사이트인 데이터 서비스를 만들 때 로컬 컴퓨터에서 IIS를 사용하여 데이터 서비스를 개발하고 테스트하는 것이 좋습니다. IIS에서 데이터 서비스를 실행하면 디버깅하는 동안 HTTP 요청을 쉽게 추적할 수 있습니다. 또한 IIS에서 데이터 서비스에 필요한 파일, 데이터베이스 및 기타 리소스에 액세스하는 데 필요한 권한을 미리 결정할 수도 있습니다. 데이터 서비스에서 IIS를 실행 하려면 있습니다 해야 하면 IIS 및 Windows Communication Foundation (WCF)이 설치 되 고 올바르게 구성 하 고 파일 시스템 및 데이터베이스에서 IIS 계정에 대 한 액세스를 부여 합니다. 자세한 내용은 [방법: IIS에서 실행되는 WCF Data Services 개발](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)을 참조하십시오.

    > [!NOTE]
    > 로컬 IIS 서버를 구성 하려면 개발 환경을 사용 하도록 설정 하려면 관리자 권한으로 Visual Studio를 실행 해야 합니다.

2.  **Visual Studio 개발 서버**

     Visual Studio에 기본 제공 웹 서버인, Visual Studio 개발 서버에 대 한 기본 웹 서버는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 프로젝트입니다. 이 웹 서버는 개발 중에 로컬 컴퓨터에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 프로젝트를 실행하도록 디자인되었습니다. 합니다 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) Visual Studio 개발 서버에서 실행 되는 데이터 서비스를 만드는 방법을 보여 줍니다.

     Visual Studio 개발 서버를 사용 하 여 데이터 서비스를 개발할 때 다음 제한 사항을 알고 있어야 합니다.

    -   이 서버는 로컬 컴퓨터에서만 액세스할 수 있습니다.

    -   이 서버는 HTTP 메시지의 기본 포트인 특정 포트(포트 80 제외)와 `localhost` 에서 수신 대기합니다. 자세한 내용은 [Visual Studio의 ASP.NET 웹 프로젝트에 대한 웹 서버](https://msdn.microsoft.com/library/31d4f588-df59-4b7e-b9ea-e1f2dd204328)를 참조하세요.

    -   이 서버는 현재 사용자 계정의 컨텍스트에서 데이터 서비스를 실행합니다. 예를 들어 관리자 수준의 사용자로 실행 하는 경우 Visual Studio 개발 서버에서 실행 되는 데이터 서비스 관리자 수준의 권한을 가집니다. 따라서 데이터 서비스가 IIS 서버에 배포된 리소스 중 액세스 권한이 없는 리소스에도 액세스할 수 있습니다.

    -   이 서버에는 인증과 같은 IIS의 추가 기능이 포함되어 있지 않습니다.

    -   이 서버는 청크 분할된 HTTP 스트림을 처리할 수 없는 데이터 서비스에서 큰 이진 데이터에 액세스 하는 경우 기본적으로 WCF Data Services 클라이언트 수는 보내집니다. 자세한 내용은 [스트리밍 공급자](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md)합니다.

    -   이 서버에는 기간을 처리 하는 문제가 (`.`)이이 문자 키 값에서 WCF Data Services에서 지원 되는 경우에 URL에서 문자입니다.

    > [!TIP]
    > Visual Studio 개발 서버를 사용 하 여 개발 하는 동안 데이터 서비스를 테스트 하려면, 있지만 IIS를 실행 하는 웹 서버에 배포한 후 다시 테스트 해야 합니다.

3.  **Microsoft Azure 개발 환경**

     Windows Azure Tools for Visual Studio는 통합 된 Visual Studio에서 Windows Azure 서비스를 개발 하기 위한 도구 집합을 포함 합니다. 이 도구를 사용하면 Microsoft Azure에 배포할 수 있는 데이터 서비스를 개발하고, 배포하기 전에 로컬 컴퓨터에서 데이터 서비스를 테스트할 수 있습니다. Visual Studio를 사용 하 여 Windows Azure 플랫폼에서 실행 되는 데이터 서비스를 개발 하는 경우 이러한 도구를 사용 합니다. Visual Studio 용 Windows Azure Tools를 다운로드할 수 있습니다 합니다 [Microsoft 다운로드 센터](https://go.microsoft.com/fwlink/?LinkID=201848)합니다. Windows Azure에서 실행 되는 데이터 서비스를 개발 하는 방법에 대 한 자세한 내용은 게시물을 참조 하세요 [Windows Azure에서 OData 서비스 배포](https://go.microsoft.com/fwlink/?LinkId=201847)합니다.

### <a name="development-tips"></a>개발 팁

데이터 서비스를 개발할 때 다음 사항을 고려해야 합니다.

-   사용자를 인증하거나 특정 사용자의 액세스를 제한하려는 경우 데이터 서비스의 보안 요구 사항을 확인해야 합니다. 자세한 내용은 [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)을 참조하세요.

-   HTTP 검사 프로그램은 요청 및 응답 메시지의 내용을 검사할 수 있도록 하여 데이터 서비스를 디버깅할 때 아주 유용할 수 있습니다. 원시 패킷을 표시할 수 있는 네트워크 패킷 분석기를 사용하여 데이터 서비스와 주고받는 HTTP 요청 및 응답을 검사할 수 있습니다.

-   일반적인 작업을 수행할 때보다 데이터 서비스를 디버깅할 때 데이터 서비스에서 발생하는 오류에 대한 자세한 정보가 필요할 수 있습니다. <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> 에서 <xref:System.Data.Services.DataServiceConfiguration> 속성을 `true` 로 설정하고 데이터 서비스 클래스에서 <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> 특성의 <xref:System.ServiceModel.Description.ServiceDebugBehavior> 속성을 `true`로 설정하여 데이터 서비스에서 추가 오류 정보를 가져올 수 있습니다. 자세한 내용은 게시물을 참조 하세요 [WCF Data Services 디버깅](https://go.microsoft.com/fwlink/?LinkId=201868)합니다. 또한 HTTP 메시징 계층에서 발생 하는 예외를 확인할 wcf에서 추적을 사용할 수 있습니다. 자세한 내용은 [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)을 참조하세요.

-   으로 일반적으로 개발 되 고 데이터 서비스는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 있지만 응용 프로그램 프로젝트를 만들 수도 데이터 서비스는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Visual Studio에서 웹 사이트 프로젝트입니다. 두 가지 프로젝트 유형의 차이점에 대 한 정보를 참조 하세요 [NIB: 웹 응용 프로그램 프로젝트와 Visual Studio에서 웹 사이트 프로젝트 비교](https://msdn.microsoft.com/library/2861815e-f5a2-4378-a2f8-b8a86dc012f5)합니다.

-   사용 하 여 데이터 서비스를 만들면 합니다 **새 항목 추가** Visual studio에서 데이터 서비스 대화 상자에서 호스팅되는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] IIS에서 합니다. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 및 IIS가 데이터 서비스의 기본 호스트지만 다른 호스팅 옵션도 지원됩니다. 자세한 내용은 [데이터 서비스 호스팅](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)합니다.

## <a name="deploy-wcf-data-services"></a>WCF Data Services를 배포 합니다.

WCF Data Services에서는 데이터 서비스를 호스트하는 프로세스를 유연성 있게 선택할 수 있도록 합니다. 다음 플랫폼에 데이터 서비스를 배포 하려면 Visual Studio를 사용할 수 있습니다.

-   **IIS에서 호스트되는 웹 서버**

     데이터 서비스를 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 프로젝트로 개발하는 경우 표준 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 배포 프로세스를 사용하여 IIS 웹 서버에 배포할 수 있습니다.  Visual Studio에 대 한 다음과 같은 배포 기술을 제공 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]종류에 따라의 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 배포 하는 데이터 서비스를 호스팅하는 프로젝트입니다.

    -   **ASP.NET 웹 응용 프로그램을 위한 배포 기술**

        -   [웹 배포 패키지](https://msdn.microsoft.com/library/1f9713c8-9540-494c-b80d-9893b970ad6f)

        -   [One-click 게시](https://msdn.microsoft.com/library/59226246-99ad-4aec-975d-7c61e8a8911c)

    -   **ASP.NET 웹 사이트를 위한 배포 기술**

        -   [웹 사이트 복사 도구](https://msdn.microsoft.com/library/b819aed4-014b-427e-be80-02317b1bb003)

        -   [웹 사이트 게시 도구](https://msdn.microsoft.com/library/d0a1a20f-15be-4940-9485-cb8e4aa8181b)

        -   [XCopy](https://msdn.microsoft.com/library/4312c651-2119-49be-bbeb-ee28bdbfe71e)

     에 대 한 배포 옵션에 대 한 자세한 내용은 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램을 참조 하세요 [Visual Studio 및 ASP.NET 웹 배포 개요](https://msdn.microsoft.com/library/99bd1927-b59f-4e02-87b4-55c6ba2adbc3)합니다.

    > [!TIP]
    > 데이터 서비스를 IIS에 배포하기 전에 IIS가 실행 중인 웹 서버로의 배포를 테스트했는지 확인해야 합니다. 자세한 내용은 [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)을 참조하십시오.

-   **Windows Azure**

     Visual Studio 용 Windows Azure Tools를 사용 하 여 Windows Azure에 데이터 서비스를 배포할 수 있습니다. Visual Studio 용 Windows Azure Tools를 다운로드할 수 있습니다 합니다 [Microsoft 다운로드 센터](https://go.microsoft.com/fwlink/?LinkID=201848)합니다. Windows Azure에 데이터 서비스를 배포 하는 방법에 대 한 자세한 내용은 게시물을 참조 하세요 [Windows Azure에서 OData 서비스 배포](https://go.microsoft.com/fwlink/?LinkId=201847)합니다.

### <a name="deployment-considerations"></a>배포 고려 사항

데이터 서비스를 배포할 때 다음 사항을 고려해야 합니다.

-   [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 공급자를 사용하는 데이터 서비스를 배포하여 SQL Server 데이터베이스에 액세스하는 경우 데이터 서비스 배포와 함께 데이터 구조, 데이터 또는 둘 다를 전파해야 할 수 있습니다. Visual Studio에서 대상 데이터베이스에서 이렇게 하려면 스크립트 (.sql 파일)를 자동으로 만들 수와 이러한 스크립트의 웹 배포 패키지에 포함 될 수는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램입니다. 자세한 내용은 [방법:를 사용 하 여 웹 프로젝트를 데이터베이스 응용 프로그램을 배포](https://msdn.microsoft.com/library/683b33f1-8a3d-45cf-af6e-61ab50fc518b)합니다. 에 대 한는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 사이트를 하면이 사용 하는 **데이터베이스 게시 마법사** Visual Studio에서. 자세한 내용은 [데이터베이스 게시 마법사를 사용 하 여 데이터베이스 배포](https://msdn.microsoft.com/library/1e3682e7-8b57-4da6-a393-af9640ccf8b7)을 참조하세요.

-   WCF Data Services가 기본 WCF 구현의 포함 하므로 Windows Server에서 실행 되는 IIS에 배포 하는 데이터 서비스를 모니터링 하려면 Windows Server AppFabric을 사용할 수 있습니다. Windows Server AppFabric을 사용 하 여 데이터 서비스를 모니터링 하는 방법에 대 한 자세한 내용은 게시물을 참조 하세요 [Windows Server AppFabric로 WCF Data Services 추적](https://go.microsoft.com/fwlink/?LinkID=202005)합니다.

## <a name="see-also"></a>참고 항목

- [데이터 서비스 호스팅](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)
- [WCF Data Services 보안](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)
- [WCF Data Services 정의](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
