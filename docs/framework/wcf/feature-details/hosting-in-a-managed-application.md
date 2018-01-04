---
title: "관리되는 응용 프로그램에서의 호스팅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c74f95fba492b677d3b1702d090c7a055bc5f1ff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="hosting-in-a-managed-application"></a><span data-ttu-id="fa39a-102">관리되는 응용 프로그램에서의 호스팅</span><span class="sxs-lookup"><span data-stu-id="fa39a-102">Hosting in a Managed Application</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="fa39a-103"> 서비스는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 응용 프로그램에서 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa39a-103"> services can be hosted in any [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] application.</span></span> <span data-ttu-id="fa39a-104">자체 호스팅 서비스는 배포하는 데 최소한의 인프라를 필요로 하기 때문에 가장 유연한 호스팅 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="fa39a-104">Self-hosting services is the most flexible hosting option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="fa39a-105">그러나 관리되는 응용 프로그램이 IIS(인터넷 정보 서비스) 및 Windows 서비스와 같은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 다른 호스팅 옵션에 대한 고급 호스팅 및 관리 기능을 제공하지 않기 때문에 가장 약한 호스팅 옵션이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa39a-105">However, it is also the least robust hosting option, because managed applications do not provide the advanced hosting and management features of other hosting options in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], such as Internet Information Services (IIS) and Windows services.</span></span>  
  
 <span data-ttu-id="fa39a-106">자체 호스팅 서비스를 만들려면 <xref:System.ServiceModel.ServiceHost>의 인스턴스를 만들고 열어, 여기서 서비스의 메시지 수신 대기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fa39a-106">To create a self-hosted service, create and open an instance of the <xref:System.ServiceModel.ServiceHost>, which starts a service listening for messages.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="fa39a-107">[하는 방법: 관리 되는 응용 프로그램에서 WCF 서비스 호스팅](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa39a-107"> [How to: Host a WCF Service in a Managed Application](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).</span></span>  
  
 <span data-ttu-id="fa39a-108">계약을 정의 계약을 구현 및 관리 되는 응용 프로그램 내에 서비스를 호스트 하는 방법에는 전체 예제에 대 한 참조는 [초보자를 위한 자습서](../../../../docs/framework/wcf/getting-started-tutorial.md) 및 [자체 호스트](../../../../docs/framework/wcf/samples/self-host.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa39a-108">For a complete example on how to define a contract, implement the contract, and host a service inside of a managed application see the [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md) and the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md).</span></span>  
  
 <span data-ttu-id="fa39a-109">다음 단원에서는 이 호스팅 옵션을 사용하는 일반적인 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa39a-109">The following sections describe common scenarios that use this hosting option.</span></span>  
  
## <a name="console-applications"></a><span data-ttu-id="fa39a-110">콘솔 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="fa39a-110">Console Applications</span></span>  
 <span data-ttu-id="fa39a-111">자체 호스팅을 사용하는 일반적인 시나리오는 콘솔 응용 프로그램 내에서 실행되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="fa39a-111">Common scenarios that self-hosting enables are [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services running inside console applications.</span></span> <span data-ttu-id="fa39a-112">일반적으로 콘솔 응용 프로그램 내에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호스팅하면 서비스의 개발 단계에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa39a-112">Hosting a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service inside a console application is typically useful during the development phase of the service.</span></span> <span data-ttu-id="fa39a-113">이 경우 쉽게 디버깅을 수행할 수 있으며, 응용 프로그램 내에서 발생하는 상황을 확인하기 위한 추적 정보를 손쉽게 얻을 수 있으며, 새 위치에 서비스를 복사하여 이동하기 용이합니다.</span><span class="sxs-lookup"><span data-stu-id="fa39a-113">This makes them easy to debug, easy to get trace information from to find out what is happening inside of the application, and easy to move around by copying them to new locations.</span></span>  
  
## <a name="rich-client-applications"></a><span data-ttu-id="fa39a-114">리치 클라이언트 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="fa39a-114">Rich Client Applications</span></span>  
 <span data-ttu-id="fa39a-115">자체 호스팅을 사용하는 다른 일반적인 시나리오는 [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] 또는 Windows Forms(WinForms)에 기반한 응용 프로그램과 같은 리치 클라이언트 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="fa39a-115">Other common scenarios that self-hosting enables are rich client applications, such as those based on [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] or Windows Forms (WinForms).</span></span> <span data-ttu-id="fa39a-116">이 호스팅 옵션을 사용하면 리치 클라이언트 응용 프로그램(예: [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] 및 WinForms 응용 프로그램)에서 외부와 쉽게 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa39a-116">This hosting option also makes it easy for rich client applications, such as [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] and WinForms applications, to communicate with the outside world.</span></span> <span data-ttu-id="fa39a-117">예를 들면 사용자 인터페이스에 대해 [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] 를 사용하고 또한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호스팅하여 다른 클라이언트에서 해당 서비스에 연결하여 정보를 공유할 수 있도록 하는 피어 투 피어 공동 작업 클라이언트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa39a-117">For example, a peer-to-peer collaboration client that uses [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] for its user interface and also hosts a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that allows other clients to connect to it and share information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa39a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa39a-118">See Also</span></span>  
 [<span data-ttu-id="fa39a-119">서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="fa39a-119">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="fa39a-120">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="fa39a-120">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)
