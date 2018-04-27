---
title: 워크플로 디버깅
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 866fe3ebcec295b57444f937b3b6fd6677bfe0f4
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="debugging-workflows"></a><span data-ttu-id="1c400-102">워크플로 디버깅</span><span class="sxs-lookup"><span data-stu-id="1c400-102">Debugging Workflows</span></span>
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="1c400-103">는 개발 환경에서 실행 중인 워크플로를 디버깅하기 위한 여러 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c400-103"> offers several options for debugging running workflows from the development environment.</span></span> <span data-ttu-id="1c400-104">디자이너, XAML 및 코드에서 워크플로를 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c400-104">Workflows can be debugged in the designer, in XAML, and in code.</span></span>  
  
## <a name="debugging-in-the-workflow-designer"></a><span data-ttu-id="1c400-105">워크플로 디자이너에서 디버깅</span><span class="sxs-lookup"><span data-stu-id="1c400-105">Debugging in the Workflow Designer</span></span>  
 <span data-ttu-id="1c400-106">활동을 강조 표시 하 고 키를 눌러 워크플로 디자이너의 활동에 중단점을 설정할 수 있습니다 **F9** 또는 활동의 상황에 맞는 메뉴를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c400-106">Breakpoints can be set on activities in the workflow designer by either highlighting the activity and pressing **F9** or by using the activity’s context menu.</span></span> <span data-ttu-id="1c400-107">그러면 워크플로 호스트가 디버그 모드에서 실행될 때 워크플로 실행이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c400-107">Execution of the workflow then breaks when the workflow host is run in debug mode.</span></span> <span data-ttu-id="1c400-108">다음 스크린샷에서는 워크플로 실행이 중단점에서 일시 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c400-108">In the following screenshot, workflow execution is paused at a breakpoint.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="1c400-109"> [워크플로 디자이너로 워크플로 디버깅](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c400-109"> [Debugging Workflows with the Workflow Designer](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer).</span></span>  
  
## <a name="debugging-in-xaml"></a><span data-ttu-id="1c400-110">XAML에서 디버깅</span><span class="sxs-lookup"><span data-stu-id="1c400-110">Debugging in XAML</span></span>  
 <span data-ttu-id="1c400-111">워크플로가 디자이너의 중단점에서 일시 중지된 경우 XAML에서 워크플로를 디버깅할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c400-111">If a workflow has paused at a breakpoint in the designer, the workflow can also be debugged in XAML.</span></span> <span data-ttu-id="1c400-112">XAML에서 실행 지점을 보려면 선택 **XAML 뷰의** 워크플로 실행이 일시 중지 될 때 워크플로 디자이너에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c400-112">To view the point of execution in XAML, select **XAML View** in the workflow designer when workflow execution is paused.</span></span> <span data-ttu-id="1c400-113">솔루션 탐색기에서 디자이너에 워크플로를 다시 열어 디버깅을 다시 디자이너로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c400-113">Debugging can be switched back to the designer by re-opening the workflow in the designer from the solution explorer.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="1c400-114"> [방법: 워크플로 디자이너로 XAML 디버그](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c400-114"> [How to: Debug XAML with the Workflow Designer](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer).</span></span>  
  
## <a name="debugging-in-code"></a><span data-ttu-id="1c400-115">코드에서 디버깅</span><span class="sxs-lookup"><span data-stu-id="1c400-115">Debugging in Code</span></span>  
 <span data-ttu-id="1c400-116">[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]에서는 다른 명령형 응용 프로그램과 동일한 방법으로 코드 중단점을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c400-116">Code breakpoints can be used in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] in the same way that they can be used in other imperative applications.</span></span> <span data-ttu-id="1c400-117">코드 중단점을 만들려면 코드 창의 왼쪽된 여백을 클릭 하거나 키를 눌러 **F9** 커서 위치에 중단점을 배치 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c400-117">Click the left margin of the code pane to create a code breakpoint, or press **F9** to place a breakpoint at the cursor location.</span></span>  
  
## <a name="attaching-to-a-workflow-process"></a><span data-ttu-id="1c400-118">워크플로 프로세스에 연결</span><span class="sxs-lookup"><span data-stu-id="1c400-118">Attaching to a Workflow Process</span></span>  
 <span data-ttu-id="1c400-119">워크플로 디버깅은 Visual Studio 인프라를 사용하여 프로세스에 연결하는 방식도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1c400-119">Workflow debugging also supports using Visual Studio’s infrastructure to attach to a process.</span></span> <span data-ttu-id="1c400-120">이렇게 하면 워크플로 작성자가 Internet Information Services(IIS) 7.0 등 다른 호스트 환경에서 실행되는 워크플로를 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c400-120">This enables the workflow author to debug a workflow running in a different host environment such as Internet Information Services (IIS) 7.0.</span></span>  
  
## <a name="remote-debugging"></a><span data-ttu-id="1c400-121">Remote Debugging</span><span class="sxs-lookup"><span data-stu-id="1c400-121">Remote Debugging</span></span>  
 <span data-ttu-id="1c400-122">Windows WF (Workflow Foundation) 원격 디버깅 다른 Visual Studio 구성 요소에 대 한 원격 디버깅으로 동일 하 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c400-122">Windows Workflow Foundation (WF) remote debugging functions the same as remote debugging for other Visual Studio components.</span></span> <span data-ttu-id="1c400-123">원격 디버깅을 사용 하는 방법은 참조 하십시오. [하는 방법: 원격 디버깅 사용](http://go.microsoft.com/fwlink/?LinkId=196257)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c400-123">For information on using remote debugging, see [How to: Enable Remote Debugging](http://go.microsoft.com/fwlink/?LinkId=196257).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c400-124">워크플로 응용 프로그램에는 x86 대상으로 하는 경우 아키텍처 원격 디버깅은 작동 되지 않습니다 되거나 워크플로 응용 프로그램에 대 한 대상에 변경 되 면 Visual Studio가 원격 컴퓨터에 설치 하지 않는 한 64 비트 운영 체제를 실행 하는 컴퓨터에 호스트 됩니다 **모든 CPU**합니다.</span><span class="sxs-lookup"><span data-stu-id="1c400-124">If the workflow application targets the x86 architecture and is hosted on a computer running a 64 bit operating system, then remote debugging will not work unless Visual Studio is installed on the remote computer or the target for the workflow application is changed to **Any CPU**.</span></span>  
  
## <a name="extending-the-workflow-debugging-service"></a><span data-ttu-id="1c400-125">워크플로 디버깅 서비스 확장</span><span class="sxs-lookup"><span data-stu-id="1c400-125">Extending the Workflow Debugging Service</span></span>  
 <span data-ttu-id="1c400-126">워크플로 디버거 서비스는 현재 공용이며 다시 호스트된 디자이너에서 모니터링, 시뮬레이션 및 디버깅과 같은 사용자 지정 응용 프로그램을 만드는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c400-126">The workflow debugger service is now public and can be used to create custom applications such as monitoring, simulation, and debugging in a re-hosted designer.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="1c400-127"> <xref:System.Activities.Presentation.Debug.DebuggerService> 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c400-127"> the <xref:System.Activities.Presentation.Debug.DebuggerService> topic.</span></span>
