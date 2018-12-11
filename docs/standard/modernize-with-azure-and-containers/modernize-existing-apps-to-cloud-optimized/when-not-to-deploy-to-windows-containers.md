---
title: Windows 컨테이너를 배포 하지 않는 경우
description: Azure 클라우드 및 Windows 컨테이너를 사용 하 여 기존.NET 응용 프로그램 현대화 | Windows 컨테이너를 배포 하지 않는 경우
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 940e94b45dcfb4e301b095cbe4ef5bcaf6752c4c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129898"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="eb2d1-103">Windows 컨테이너를 배포 하지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="eb2d1-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="eb2d1-104">일부 Windows 기술은 Windows 컨테이너에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2d1-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="eb2d1-105">이러한 경우 Windows 및 IIS만 사용 하 여 일반적으로 표준 Vm에 마이그레이션할 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2d1-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="eb2d1-106">경우 2018 년 5 월을 기준으로 Windows 컨테이너에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2d1-106">Cases not supported in Windows Containers, as of May 2018:</span></span> 

-   <span data-ttu-id="eb2d1-107">현재 Microsoft 메시지 큐 (MSMQ)는 다른 이전 릴리스의 아니라 Windows Server v1803 릴리스를 기준으로 하는 Windows 컨테이너에서 사용할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2d1-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span> 

    -   [<span data-ttu-id="eb2d1-108">UserVoice 요청 포럼</span><span class="sxs-lookup"><span data-stu-id="eb2d1-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [<span data-ttu-id="eb2d1-109">토론 포럼</span><span class="sxs-lookup"><span data-stu-id="eb2d1-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   <span data-ttu-id="eb2d1-110">Microsoft Distributed Transaction Coordinator (MSDTC) 현재 지원 되지 않습니다 Windows 컨테이너에서.</span><span class="sxs-lookup"><span data-stu-id="eb2d1-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

    -   [<span data-ttu-id="eb2d1-111">GitHub 문제</span><span class="sxs-lookup"><span data-stu-id="eb2d1-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   <span data-ttu-id="eb2d1-112">현재 Microsoft Office는 컨테이너를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2d1-112">Microsoft Office currently does not support containers.</span></span>

    -   [<span data-ttu-id="eb2d1-113">UserVoice 요청 포럼</span><span class="sxs-lookup"><span data-stu-id="eb2d1-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

-   <span data-ttu-id="eb2d1-114">UI 앱 (시각적 사용자 인터페이스를 사용 하 여 클라이언트 앱)은 지원 되는 시나리오.</span><span class="sxs-lookup"><span data-stu-id="eb2d1-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

-   <span data-ttu-id="eb2d1-115">Windows 인프라 역할 (DNS, DHCP, DC, NTP, 인쇄, 파일 서버, IAM 등) 지원 되는 시나리오가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2d1-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>


<span data-ttu-id="eb2d1-116">추가 지원 되지 않는 시나리오와 커뮤니티에서 요청에 대 한 UserVoice 포럼 Windows 컨테이너에 대 한 참조: <https://windowsserver.uservoice.com/forums/304624-containers>합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2d1-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="eb2d1-117">추가 자료</span><span class="sxs-lookup"><span data-stu-id="eb2d1-117">Additional resources</span></span>

-   <span data-ttu-id="eb2d1-118">**Virtual machines 및 Azure에서 컨테이너**</span><span class="sxs-lookup"><span data-stu-id="eb2d1-118">**Virtual machines and containers in Azure**</span></span>

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
><span data-ttu-id="eb2d1-119">[이전](deploy-existing-net-apps-as-windows-containers.md)
>[다음](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="eb2d1-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>