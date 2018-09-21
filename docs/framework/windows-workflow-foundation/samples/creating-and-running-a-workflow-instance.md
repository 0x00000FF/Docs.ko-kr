---
title: 워크플로 인스턴스 만들기 및 실행
ms.date: 03/30/2017
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
ms.openlocfilehash: 571d41194ebc98be81646fb5bfdab060225015ca
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46517949"
---
# <a name="creating-and-running-a-workflow-instance"></a><span data-ttu-id="18fcf-102">워크플로 인스턴스 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="18fcf-102">Creating and Running a Workflow Instance</span></span>
<span data-ttu-id="18fcf-103">이 샘플에서는 워크플로 인스턴스를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18fcf-103">This sample shows how to run a workflow instance.</span></span> <span data-ttu-id="18fcf-104">동기적 실행 방법과 비동기적 실행 방법을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18fcf-104">It shows how to execute it synchronously and asynchronously.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="18fcf-105">세부 항목</span><span class="sxs-lookup"><span data-stu-id="18fcf-105">Demonstrates</span></span>  
 <span data-ttu-id="18fcf-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="18fcf-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="18fcf-107">토론</span><span class="sxs-lookup"><span data-stu-id="18fcf-107">Discussion</span></span>  
 <span data-ttu-id="18fcf-108">샘플의 첫 번째 부분에서는 <xref:System.Activities.WorkflowInvoker.Invoke%2A>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="18fcf-108">The first part of the sample uses <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span> <span data-ttu-id="18fcf-109">이는 워크플로를 실행하는 가장 기본적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="18fcf-109">This is the most basic way to execute a workflow.</span></span> <span data-ttu-id="18fcf-110"><xref:System.Activities.WorkflowInvoker.Invoke%2A>를 사용할 경우 워크플로를 동기적으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18fcf-110">Workflows executed with <xref:System.Activities.WorkflowInvoker.Invoke%2A> are executed synchronously.</span></span>  
  
 <span data-ttu-id="18fcf-111">샘플의 다음 부분에서는 <xref:System.Activities.WorkflowApplication> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="18fcf-111">The second part of the sample uses the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="18fcf-112"><xref:System.Activities.WorkflowApplication> 클래스를 사용하면 실행 중인 워크플로와 상호 작용하고 워크플로를 비동기적으로 실행하는 등 각 인스턴스를 보다 효과적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18fcf-112"><xref:System.Activities.WorkflowApplication> enables you to have more control over each instance, including the ability to interact with the running workflow and to run the workflow asynchronously.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="18fcf-113">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18fcf-113">The samples may already be installed on your machine.</span></span> <span data-ttu-id="18fcf-114">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="18fcf-114">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="18fcf-115">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="18fcf-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="18fcf-116">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18fcf-116">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a><span data-ttu-id="18fcf-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18fcf-117">See Also</span></span>  
 [<span data-ttu-id="18fcf-118">WorkflowInvoker 및 WorkflowApplication 사용</span><span class="sxs-lookup"><span data-stu-id="18fcf-118">Using WorkflowInvoker and WorkflowApplication</span></span>](../../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md)
