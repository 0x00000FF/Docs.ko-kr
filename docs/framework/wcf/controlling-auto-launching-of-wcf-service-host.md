---
title: WCF 서비스 호스트 자동 시작 제어
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5bb6356ba4698cad00d443fdb80b1a45d35e2175
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="528c6-102">WCF 서비스 호스트 자동 시작 제어</span><span class="sxs-lookup"><span data-stu-id="528c6-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="528c6-103">자동 시작 기능을 제어할 수 있습니다 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 에 대 한 서비스 호스트 (WcfSvcHost.exe)를 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리 프로젝트에 여러 프로젝트가 포함 된 같은 Visual Studio 솔루션의 다른 프로젝트를 디버깅할 때.</span><span class="sxs-lookup"><span data-stu-id="528c6-103">You can control the auto-launching capability of [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Service Host (WcfSvcHost.exe) for a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Library project, when you debug another project in the same Visual Studio solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="528c6-104">이렇게 하려면 마우스 오른쪽 단추로 클릭는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 프로젝트에 **솔루션 탐색기**, 선택 **속성**를 클릭 하 고 **WCF 옵션** 탭 합니다. **WCF 서비스 호스트 시작 동일한 솔루션의 다른 프로젝트를 디버깅할 때** 확인란은 기본적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="528c6-104">To do so, right-click the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="528c6-105">같은 솔루션의 다른 프로젝트를 디버깅할 때 이 특정 프로젝트에 대해 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트가 시작되지 않게 하려면 이 확인란의 선택을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="528c6-105">You can clear the box so that [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="528c6-106">이 동작은 F5 키를 사용한 디버깅이나 이 프로젝트의 서비스 참조 추가 기능에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="528c6-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="528c6-107">이 옵션은 다음 프로젝트에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="528c6-107">This option is available to the following projects:</span></span>  
  
-   [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="528c6-108"> 서비스 라이브러리 프로젝트</span><span class="sxs-lookup"><span data-stu-id="528c6-108"> Service Library Project.</span></span>  
  
-   <span data-ttu-id="528c6-109">순차 워크플로 서비스 라이브러리 프로젝트</span><span class="sxs-lookup"><span data-stu-id="528c6-109">Sequential Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="528c6-110">상태 시스템 워크플로 서비스 라이브러리 프로젝트</span><span class="sxs-lookup"><span data-stu-id="528c6-110">State Machine Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="528c6-111">배포 서비스 라이브러리 프로젝트</span><span class="sxs-lookup"><span data-stu-id="528c6-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="528c6-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="528c6-112">See Also</span></span>  
 [<span data-ttu-id="528c6-113">WCF 서비스 호스트(WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="528c6-113">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
