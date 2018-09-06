---
title: Flowchart 활동에서 TryCatch를 사용하여 오류 처리
ms.date: 03/30/2017
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
ms.openlocfilehash: e89c80ecfa8ec93fdde82b5638c504ded681a4fc
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864695"
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a><span data-ttu-id="f208e-102">Flowchart 활동에서 TryCatch를 사용하여 오류 처리</span><span class="sxs-lookup"><span data-stu-id="f208e-102">Fault Handling in a Flowchart Activity Using TryCatch</span></span>
<span data-ttu-id="f208e-103">이 샘플에서는 복잡한 제어 흐름 활동 내에서 <xref:System.Activities.Statements.TryCatch> 활동을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f208e-103">This sample shows how the <xref:System.Activities.Statements.TryCatch> activity can be used within a complex control flow activity.</span></span>  
  
 <span data-ttu-id="f208e-104">이 샘플에서는 승격 코드에 해당하는 식을 기반으로 할인율을 계산하는 <xref:System.Activities.Statements.Flowchart> 활동에 승격 코드와 자식 수를 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="f208e-104">In this sample, a promotion code and number of children are passed as variables to a <xref:System.Activities.Statements.Flowchart> activity that calculates a discount based on formulae that correspond to the promotion code.</span></span> <span data-ttu-id="f208e-105">이 샘플에는 샘플의 명령적 코드 및 Workflow Designer 버전이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f208e-105">The sample includes imperative code and workflow designer versions of the sample.</span></span>  
  
 <span data-ttu-id="f208e-106">다음 표에서는 `CreateFlowchartWithFaults` 활동의 변수에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f208e-106">The following table details the variables for the `CreateFlowchartWithFaults` activity.</span></span>  
  
|<span data-ttu-id="f208e-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f208e-107">Parameters</span></span>|<span data-ttu-id="f208e-108">설명</span><span class="sxs-lookup"><span data-stu-id="f208e-108">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="f208e-109">promoCode</span><span class="sxs-lookup"><span data-stu-id="f208e-109">promoCode</span></span>|<span data-ttu-id="f208e-110">승격 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f208e-110">The promotion code.</span></span> <span data-ttu-id="f208e-111">형식: String</span><span class="sxs-lookup"><span data-stu-id="f208e-111">Type: String</span></span><br /><br /> <span data-ttu-id="f208e-112">가능한 값은 다음과 같으며 괄호 안에 설명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f208e-112">The possible values with description in parentheses:</span></span><br /><br /> <span data-ttu-id="f208e-113">단일 (단일)</span><span class="sxs-lookup"><span data-stu-id="f208e-113">-   Single (Single)</span></span><br /><span data-ttu-id="f208e-114">-MNK (기혼 이며 없음)</span><span class="sxs-lookup"><span data-stu-id="f208e-114">-   MNK (Married with no kids.)</span></span><br /><span data-ttu-id="f208e-115">-MWK (기혼 이며)</span><span class="sxs-lookup"><span data-stu-id="f208e-115">-   MWK (Married with kids.)</span></span>|  
|<span data-ttu-id="f208e-116">numKids</span><span class="sxs-lookup"><span data-stu-id="f208e-116">numKids</span></span>|<span data-ttu-id="f208e-117">자식 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f208e-117">The number of children.</span></span> <span data-ttu-id="f208e-118">형식: int</span><span class="sxs-lookup"><span data-stu-id="f208e-118">Type: int</span></span>|  
  
 <span data-ttu-id="f208e-119">`CreateFlowchartWithFaults` 활동은 <xref:System.Activities.Statements.FlowSwitch%601> 인수로 전환하고 다음 수식을 사용하여 할인율을 계산하는 `promoCode` 활동을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f208e-119">The `CreateFlowchartWithFaults` activity uses a <xref:System.Activities.Statements.FlowSwitch%601> activity that switches on the `promoCode` argument and calculates the discount using the following formula.</span></span>  
  
|<span data-ttu-id="f208e-120">`promoCode`의 값</span><span class="sxs-lookup"><span data-stu-id="f208e-120">Value of `promoCode`</span></span>|<span data-ttu-id="f208e-121">할인율(%)</span><span class="sxs-lookup"><span data-stu-id="f208e-121">Discount (%)</span></span>|  
|--------------------------|--------------------|  
|<span data-ttu-id="f208e-122">Single</span><span class="sxs-lookup"><span data-stu-id="f208e-122">Single</span></span>|<span data-ttu-id="f208e-123">10</span><span class="sxs-lookup"><span data-stu-id="f208e-123">10</span></span>|  
|<span data-ttu-id="f208e-124">MNK</span><span class="sxs-lookup"><span data-stu-id="f208e-124">MNK</span></span>|<span data-ttu-id="f208e-125">15</span><span class="sxs-lookup"><span data-stu-id="f208e-125">15</span></span>|  
|<span data-ttu-id="f208e-126">MWK</span><span class="sxs-lookup"><span data-stu-id="f208e-126">MWK</span></span>|<span data-ttu-id="f208e-127">15 + (1-1 /`numberOfKids`)\*10 **참고:** 이 계산 잠재적으로 throw 할 수는 <xref:System.DivideByZeroException>합니다.</span><span class="sxs-lookup"><span data-stu-id="f208e-127">15 + (1 – 1/`numberOfKids`)\*10 **Note:**  Potentially, this calculation can throw a <xref:System.DivideByZeroException>.</span></span> <span data-ttu-id="f208e-128">할인율 계산은 <xref:System.Activities.Statements.TryCatch> 예외를 catch하고 할인율을 0으로 설정하는 <xref:System.DivideByZeroException> 활동에 래핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="f208e-128">So, the discount calculation is wrapped in a <xref:System.Activities.Statements.TryCatch> activity that catches the <xref:System.DivideByZeroException> exception and sets the discount to zero.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="f208e-129">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="f208e-129">To use this sample</span></span>  
  
1.  <span data-ttu-id="f208e-130">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 FlowchartWithFaultHandling.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f208e-130">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the FlowchartWithFaultHandling.sln solution file.</span></span>  
  
2.  <span data-ttu-id="f208e-131">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f208e-131">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="f208e-132">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f208e-132">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f208e-133">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f208e-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f208e-134">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="f208e-134">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f208e-135">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="f208e-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f208e-136">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f208e-136">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`  
  
## <a name="see-also"></a><span data-ttu-id="f208e-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f208e-137">See Also</span></span>  
 [<span data-ttu-id="f208e-138">순서도 워크플로</span><span class="sxs-lookup"><span data-stu-id="f208e-138">Flowchart Workflows</span></span>](../../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)  
 [<span data-ttu-id="f208e-139">예외</span><span class="sxs-lookup"><span data-stu-id="f208e-139">Exceptions</span></span>](../../../../docs/framework/windows-workflow-foundation/exceptions.md)
