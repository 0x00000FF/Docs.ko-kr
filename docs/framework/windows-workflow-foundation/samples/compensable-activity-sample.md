---
title: "보정 가능한 활동 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58f4898c-b2b8-44a4-9a73-3bef4da6d5ba
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b8d7fb5650a8927016e0deebc07a68a8145496db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="compensable-activity-sample"></a><span data-ttu-id="bd5eb-102">보정 가능한 활동 샘플</span><span class="sxs-lookup"><span data-stu-id="bd5eb-102">Compensable Activity Sample</span></span>
<span data-ttu-id="bd5eb-103">이 샘플에서는 `CompensableActivity` 활동을 사용하여 정상적인 실행 중에 지정된 동작에 대해 수행할 작업과 해당 동작을 보정하기 위해 필요한 경우 나중에 수행해야 하는 작업을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd5eb-103">This sample demonstrates how to use the `CompensableActivity` activity to define the work to be done for a given action during normal execution and the work that is necessary to be done to compensate that action, if necessary at a later time.</span></span>  <span data-ttu-id="bd5eb-104">샘플의 첫 번째 부분에서는 [!INCLUDE[wf](../../../../includes/wf-md.md)] 활동을 사용하여 `CompensableActivity`에서 보정 가능한 작업 단위를 정의하는 방법과 성공적인 실행 시 해당 작업 단위를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd5eb-104">The first part of the sample shows how units of compensable work can be defined in [!INCLUDE[wf](../../../../includes/wf-md.md)] using a `CompensableActivity` activity and how they are executed in a successful run.</span></span>  <span data-ttu-id="bd5eb-105">샘플의 두 번째 부분에서는 예기치 않은 이벤트가 발생하고 워크플로 인스턴스가 취소될 경우 동일한 보정 가능 작업 단위가 자동으로 보정을 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd5eb-105">The second part of the sample shows how the same units of compensable work automatically take care of compensation when an unexpected event is hit and the workflow instance is canceled.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bd5eb-106">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="bd5eb-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="bd5eb-107">Visual Studio 2010을 사용하여 CompensableActivity.sln을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bd5eb-107">Using Visual Studio 2010, open the CompensableActivity.sln.</span></span>  
  
2.  <span data-ttu-id="bd5eb-108">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="bd5eb-108">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="bd5eb-109">F5 키를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bd5eb-109">Run the application by pressing F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bd5eb-110">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd5eb-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bd5eb-111">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="bd5eb-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bd5eb-112">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="bd5eb-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bd5eb-113">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd5eb-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\BasicCompensableActivity`  
  
## <a name="see-also"></a><span data-ttu-id="bd5eb-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd5eb-114">See Also</span></span>
