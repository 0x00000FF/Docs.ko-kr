---
title: '방법: Net.TCP Port Sharing Service 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 20db0ef427a5e791bd6b8dcef90bf7911ae0d4a9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343482"
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a><span data-ttu-id="addb5-102">방법: Net.TCP Port Sharing Service 사용</span><span class="sxs-lookup"><span data-stu-id="addb5-102">How to: Enable the Net.TCP Port Sharing Service</span></span>
<span data-ttu-id="addb5-103">Windows Communication Foundation (WCF) Net.TCP Port Sharing Service 라는 Windows 서비스를 사용 하 여 여러 프로세스에서 TCP 포트를 공유할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="addb5-103">Windows Communication Foundation (WCF) uses a Windows service called the Net.TCP Port Sharing Service to facilitate the sharing of TCP ports across multiple processes.</span></span> <span data-ttu-id="addb5-104">이 서비스는 WCF의 일부로 설치 되지만 서비스 보안 예방 조치로 서 기본적으로 사용 되지 않으며 따라서 수동으로 활성화 해야 처음 사용 하기 전에 합니다.</span><span class="sxs-lookup"><span data-stu-id="addb5-104">This service is installed as part of WCF, but the service is not enabled by default as a security precaution and so must be manually enabled prior to first use.</span></span> <span data-ttu-id="addb5-105">이 항목에서는 MMC(Microsoft Management Console) 스냅인을 사용하여 Net TCP Port Sharing Service를 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="addb5-105">This topic describes how to configure the Net TCP Port Sharing Service using the Microsoft Management Console (MMC) snap-In.</span></span>  
  
 <span data-ttu-id="addb5-106">Net.TCP Port Sharing Service를 사용 하도록 설정 하 고 수동으로 시작 후 참조 [방법: 포트 공유를 사용 하도록 WCF 서비스 구성](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) 이 서비스를 사용 하도록 서비스를 구성 하는 방법에 대 한 정보에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="addb5-106">After you enable the Net.TCP Port Sharing Service and start it manually, see [How to: Configure a WCF Service to Use Port Sharing](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) for information about how to configure your service to use this service.</span></span>  
  
 <span data-ttu-id="addb5-107">Net.tcp:// 포트 공유를 사용 하는 샘플에 대해서는 [Net.TCP Port Sharing 샘플](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="addb5-107">For a sample that uses net.tcp:// port sharing, see the [Net.TCP Port Sharing Sample](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).</span></span>  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a><span data-ttu-id="addb5-108">MMC를 사용하여 Net.TCP Port Sharing Service를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="addb5-108">To enable the Net.TCP Port Sharing Service using MMC</span></span>  
  
1. <span data-ttu-id="addb5-109">시작 메뉴에서 명령 프롬프트 창을 열고를 입력 하 여 서비스 관리 콘솔을 엽니다 `services.msc` 실행을 열고를 입력 하거나 `services.msc` 열기 상자에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="addb5-109">From the Start menu, open the Services Management Console either by opening a Command Prompt window and typing `services.msc` or by opening Run and typing `services.msc` into the Open box.</span></span>  
  
2. <span data-ttu-id="addb5-110">에 **이름** 열의 서비스 목록 마우스 오른쪽 단추로 클릭 합니다 **Net.Tcp Port Sharing Service**, 선택한 **속성** 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="addb5-110">In the **Name** column of the list of services, right-click the **Net.Tcp Port Sharing Service**, and select **Properties** from the menu.</span></span>  
  
3. <span data-ttu-id="addb5-111">서비스의 수동 시작을 사용 하도록 설정 하는 **속성** 창 선택 합니다 **일반** 탭 및는 **시작 유형** 수동을 선택한 다음 를클릭**적용**합니다.</span><span class="sxs-lookup"><span data-stu-id="addb5-111">To enable the manual start-up of the service, in the **Properties** window select the **General** tab, and in the **Startup type** box select Manual, and then click **Apply**.</span></span>  
  
4. <span data-ttu-id="addb5-112">서비스 상태 영역에서 서비스를 시작 하려면 클릭 합니다 **시작** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="addb5-112">To start the service,  in the Service status area, click the **Start** button.</span></span> <span data-ttu-id="addb5-113">서비스 상태가 "시작됨"으로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="addb5-113">The service status should now display "Started".</span></span>  
  
5. <span data-ttu-id="addb5-114">서비스 목록으로 돌아가려면 클릭 합니다 **확인**를 하 고 MMC 콘솔을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="addb5-114">To return to the list of services, click the **OK**, and exit the MMC Console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="addb5-115">예제</span><span class="sxs-lookup"><span data-stu-id="addb5-115">Example</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="addb5-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="addb5-116">See also</span></span>

- [<span data-ttu-id="addb5-117">Net.TCP 포트 공유</span><span class="sxs-lookup"><span data-stu-id="addb5-117">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="addb5-118">Net.TCP Port Sharing Service 구성</span><span class="sxs-lookup"><span data-stu-id="addb5-118">Configuring the Net.TCP Port Sharing Service</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
