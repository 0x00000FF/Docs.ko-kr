---
title: WorkflowHostingEndpoint 다시 시작 책갈피
ms.date: 03/30/2017
ms.assetid: a708064f-50b0-4751-b44e-d5410d08d451
ms.openlocfilehash: 5c3c996a73d8f88e925d459fae3eb785996eada4
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59340544"
---
# <a name="workflowhostingendpoint-resume-bookmark"></a><span data-ttu-id="6148a-102">WorkflowHostingEndpoint 다시 시작 책갈피</span><span class="sxs-lookup"><span data-stu-id="6148a-102">WorkflowHostingEndpoint Resume Bookmark</span></span>
<span data-ttu-id="6148a-103">이 샘플에서는 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>를 <xref:System.ServiceModel.Activities.WorkflowServiceHost>와 함께 사용하여 워크플로 인스턴스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6148a-103">This sample demonstrates how the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> can be used with <xref:System.ServiceModel.Activities.WorkflowServiceHost> to create workflow instances.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="6148a-104">세부 항목</span><span class="sxs-lookup"><span data-stu-id="6148a-104">Demonstrates</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint><span data-ttu-id="6148a-105">,</span><span class="sxs-lookup"><span data-stu-id="6148a-105">,</span></span> <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
## <a name="discussion"></a><span data-ttu-id="6148a-106">토론</span><span class="sxs-lookup"><span data-stu-id="6148a-106">Discussion</span></span>  
 <span data-ttu-id="6148a-107">이 샘플에서는 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>를 사용하여 워크플로 인스턴스를 만듭니다. 이 워크플로 인스턴스는 <xref:System.ServiceModel.Activities.WorkflowServiceHost>를 통해 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="6148a-107">This sample uses the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to create a workflow instance hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> <span data-ttu-id="6148a-108">확장성 지점입니다 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 다음과 같은 시나리오에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6148a-108">is an extensibility point for <xref:System.ServiceModel.Activities.WorkflowServiceHost> that can be used in the following scenarios:</span></span>  
  
-   <span data-ttu-id="6148a-109">새 워크플로 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="6148a-109">Creating new workflow instances.</span></span>  
  
-   <span data-ttu-id="6148a-110"><xref:System.ServiceModel.Activities.WorkflowServiceHost>에 호스트되는 워크플로 인스턴스에 대한 책갈피 다시 시작</span><span class="sxs-lookup"><span data-stu-id="6148a-110">Resuming bookmarks on a workflow instance hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="6148a-111">여기에 포함되어 있는 샘플 끝점은 워크플로를 만들고 인스턴스 ID를 반환하거나 특정 ID의 인스턴스를 만드는 작업을 제공하는 계약을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="6148a-111">The sample endpoint that is included exposes a contract that provides operations to create a workflow and return an instance ID, or to create an instance with a specific ID.</span></span> <span data-ttu-id="6148a-112">샘플 콘솔 응용 프로그램에서는 기본 워크플로 정의를 사용하여 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 인스턴스를 만들고 호스트에 `CreationEndpoint`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6148a-112">The sample console application creates a <xref:System.ServiceModel.Activities.WorkflowServiceHost> instance with a basic workflow definition, and adds a `CreationEndpoint` to the host.</span></span> <span data-ttu-id="6148a-113">그런 다음 끝점에 대해 `Create` 작업을 호출하여 새 워크플로 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6148a-113">It then calls the `Create` operation on the endpoint to create a new workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6148a-114">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="6148a-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="6148a-115">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6148a-115">Build the solution.</span></span>  
  
2. <span data-ttu-id="6148a-116">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6148a-116">Run the application.</span></span> <span data-ttu-id="6148a-117">워크플로 인스턴스를 만들 때 인스턴스 ID를 포함하는 메시지가 `CreationEndpoint` 콘솔에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6148a-117">The `CreationEndpoint` console shows a message that includes the instance ID when the workflow instance is created.</span></span> <span data-ttu-id="6148a-118">"Hello World!" 메시지</span><span class="sxs-lookup"><span data-stu-id="6148a-118">The message "Hello World!"</span></span> <span data-ttu-id="6148a-119">성공적으로 다시 시작 책갈피에서 워크플로로 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6148a-119">is printed by the workflow on successful resumption of the bookmark.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6148a-120">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6148a-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6148a-121">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="6148a-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6148a-122">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="6148a-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6148a-123">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6148a-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ResumeBookmarkEndpoint`
