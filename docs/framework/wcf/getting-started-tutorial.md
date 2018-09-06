---
title: Tutorial1 시작
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], getting started
- Windows Communication Foundation [WCF], getting started
- getting started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: e5a07e5264c715f568121403721a3c844b903d99
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43886320"
---
# <a name="getting-started-tutorial"></a>초보자를 위한 자습서
이 단원의 항목에서는 프로그래밍 환경을 Windows Communication Foundation (WCF)에 대해 간략하게 위해 제공 됩니다. 이 항목 아래쪽에 나열된 순서대로 진행하세요. 이 자습서를 통해 WCF 서비스 및 클라이언트 응용 프로그램을 만드는 데 필요한 단계를 대략적으로 이해할을 제공 합니다. 서비스는 하나 이상의 엔드포인트를 노출하며 각 엔드포인트는 하나 이상의 서비스 작업을 노출합니다. 합니다 *끝점* 서비스의 서비스를 찾을 수 있는, 서비스 및 기능을 정의 하는 계약을 사용 하 여 통신 해야 하는 방법을 설명 하는 정보를 포함 하는 바인딩 주소를 지정 합니다. 클라이언트가 서비스에서 제공 합니다.  
  
 이 자습서의 항목을 순서대로 수행하면 서비스를 실행하고 클라이언트에서 서비스를 호출할 수 있습니다. 첫 번째 세 개 항목에서는 서비스 계약을 정의하는 방법, 서비스 계약을 구현하는 방법 및 서비스를 호스트하는 방법을 설명합니다. 만들어진 서비스는 콘솔 응용 프로그램 내에서 자체 호스트됩니다. IIS(인터넷 정보 서비스)에서 서비스를 호스트할 수도 있습니다. 이 작업을 수행 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: IIS에서 WCF 서비스 호스팅](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)합니다. 서비스는 코드로 구성하지만 구성 파일 내에 서비스를 구성할 수도 있습니다. 구성 파일을 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [구성 파일을 사용 하 여 서비스 구성](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)합니다.  
  
 다음 세 개 항목에서는 클라이언트 프록시를 만드는 방법, 클라이언트 응용 프로그램을 구성하는 방법 및 클라이언트 프록시를 사용하여 서비스에서 노출하는 서비스 작업을 호출하는 방법을 설명합니다. 서비스는 클라이언트 응용 프로그램이 서비스와 통신하는 데 필요한 정보를 정의하는 메타데이터를 게시합니다. [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]에서는 이 메타데이터에 액세스하는 프로세스를 자동화하고 해당 메타데이터를 사용하여 서비스에 대한 클라이언트 응용 프로그램을 생성 및 구성합니다. 사용 하지 않는 경우 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]를 사용할 수는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 을 생성 및 서비스용 클라이언트 응용 프로그램을 구성 합니다.  
  
 이 단원에 있는 모든 항목에서는 Visual Studio 2011을 개발 환경으로 사용하는 것으로 간주합니다. 다른 개발 환경을 사용 하는 경우 Visual Studio 특정 지침을 무시 합니다.  
  
> [!NOTE]
>  실행 하는 경우 [!INCLUDE[wv](../../../includes/wv-md.md)] 또는 이후 버전의 Windows 운영 체제에서는 시작 메뉴로 이동 하 고 Visual Studio 2011을 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 Visual Studio를 시작 해야 합니다 **관리자 권한으로 실행**합니다. 항상 있습니다 수 바로 가기를 만들려면 바로 가기를 마우스 오른쪽 단추로 클릭, 속성을 선택, 선택 관리자로 서 Visual Studio 2011을 시작 하려면 합니다 **호환성** 탭을 확인 합니다 **관리자권한으로이프로그램을실행합니다.** 확인란을 선택 합니다. 이 바로 가기로 Visual Studio 2011을 시작하면 프로그램이 항상 관리자 권한으로 실행됩니다.  
  
 하드 디스크를 다운로드할 수 있습니다 및 실행의 항목을 참조 하는 샘플 응용 프로그램에 대 한 [Windows Communication Foundation 샘플](https://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)합니다. 이 항목의 경우 특히 참조를 [Getting Started](../../../docs/framework/wcf/samples/getting-started-sample.md)합니다.  
  
 자세한 내용은 서비스 및 클라이언트 만들기에 대 한 참조 [기본 WCF 프로그래밍](../../../docs/framework/wcf/basic-wcf-programming.md)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 서비스 계약 정의](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 사용자 정의 인터페이스를 사용 하 여 WCF 계약을 만드는 방법을 설명 합니다. 계약은 서비스에서 노출하는 기능을 정의합니다.  
  
 [방법: 서비스 계약 구현](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 서비스 계약을 구현하는 방법에 대해 설명합니다. 정의된 계약은 서비스 클래스를 사용하여 구현해야 합니다.  
  
 [방법: 기본 서비스 호스트 및 실행](../../../docs/framework/wcf/how-to-host-and-run-a-basic-wcf-service.md)  
 코드에서 서비스의 엔드포인트를 구성하는 방법 및 콘솔 응용 프로그램에서 서비스를 호스트하는 방법을 설명합니다. 서비스를 활성화하려면 런타임 환경에 구성하고 호스트해야 합니다. 이 환경에서 서비스를 만들고 서비스의 컨텍스트 및 수명을 제어합니다.  
  
 [방법: 클라이언트 만들기](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 WCF 서비스에서 WCF 클라이언트 프록시를 만드는 데 사용 하는 메타 데이터를 검색 하는 방법에 설명 합니다. 이 프로세스는 Visual Studio 2011의 서비스 참조 추가 기능을 사용합니다.  
  
 [방법: 클라이언트 구성](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
 WCF 클라이언트를 구성하는 방법을 설명합니다. 클라이언트를 구성하려면 클라이언트에서 서비스에 액세스하는 데 사용하는 엔드포인트를 지정해야 합니다.  
  
 [방법: 클라이언트 사용](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)  
 WCF 클라이언트 프록시를 사용 하 여 서비스 작업을 호출 하는 방법에 설명 합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.ServiceModel.ServiceContractAttribute>  
  
 <xref:System.ServiceModel.OperationContractAttribute>  
  
## <a name="related-sections"></a>관련 단원  
 [Windows Communication Foundation 샘플](https://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
  
 [기본 프로그래밍 수명 주기](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
## <a name="see-also"></a>참고 항목  
 [개념적 개요](../../../docs/framework/wcf/conceptual-overview.md)  
 [설명서에 대한 안내](../../../docs/framework/wcf/guide-to-the-documentation.md)  
 [Windows Communication Foundation 정의](../../../docs/framework/wcf/whats-wcf.md)  
 [WCF 기능 정보](../../../docs/framework/wcf/feature-details/index.md)
