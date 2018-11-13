---
title: '연습: 확장 가능한 응용 프로그램 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [.NET Framework], add-in pipeline
- host-side adapters for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], creating
- add-in-side adapter [.NET Framework]
- contracts for add-in pipelines [.NET Framework]
ms.assetid: 694a33c5-a040-450d-aed5-ac49fc88ce61
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63780583d035d6fab6b3a79424857b82a910ef09
ms.sourcegitcommit: 5fd80619c760fa8c25d33a6f5661247cb65da465
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2018
ms.locfileid: "50744615"
---
# <a name="walkthrough-creating-an-extensible-application"></a><span data-ttu-id="d7a44-102">연습: 확장 가능한 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="d7a44-102">Walkthrough: Creating an Extensible Application</span></span>
<span data-ttu-id="d7a44-103">이 연습에서는 간단한 계산기 기능을 수행 하는 추가 기능에 대 한 파이프라인을 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-103">This walkthrough describes how to create a pipeline for an add-in that performs simple calculator functions.</span></span> <span data-ttu-id="d7a44-104">실제 시나리오; 보여 주지 않지만 대신, 파이프라인 및 방법으로 추가 기능 서비스를 제공할 수는 호스트의 기본 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-104">It does not demonstrate a real-world scenario; rather, it demonstrates the basic functionality of a pipeline and how an add-in can provide services for a host.</span></span>  
  
 <span data-ttu-id="d7a44-105">이 연습에서는 다음 작업을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-105">This walkthrough describes the following tasks:</span></span>  
  
-   <span data-ttu-id="d7a44-106">Visual Studio 솔루션을 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-106">Creating a Visual Studio solution.</span></span>  
  
-   <span data-ttu-id="d7a44-107">파이프라인 디렉터리 구조를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-107">Creating the pipeline directory structure.</span></span>  
  
-   <span data-ttu-id="d7a44-108">계약 및 뷰를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-108">Creating the contract and views.</span></span>  
  
-   <span data-ttu-id="d7a44-109">추가 기능 쪽 어댑터를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-109">Creating the add-in-side adapter.</span></span>  
  
-   <span data-ttu-id="d7a44-110">호스트 쪽 어댑터를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-110">Creating the host-side adapter.</span></span>  
  
-   <span data-ttu-id="d7a44-111">호스트를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-111">Creating the host.</span></span>  
  
-   <span data-ttu-id="d7a44-112">추가 기능에서 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-112">Creating the add-in.</span></span>  
  
-   <span data-ttu-id="d7a44-113">파이프라인을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-113">Deploying the pipeline.</span></span>  
  
-   <span data-ttu-id="d7a44-114">호스트 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-114">Running the host application.</span></span>  
  
 <span data-ttu-id="d7a44-115">이 파이프라인만 직렬화 가능 형식 전달 (<xref:System.Double> 고 <xref:System.String>), 호스트와 추가 기능 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-115">This pipeline passes only serializable types (<xref:System.Double> and <xref:System.String>), between the host and the add-in.</span></span> <span data-ttu-id="d7a44-116">복잡 한 데이터 형식의 컬렉션을 전달 하는 방법을 보여 주는 예제를 참조 하세요 [연습: 추가 기능 및 호스트 간의 컬렉션 전달](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-116">For an example that shows how to pass collections of complex data types, see [Walkthrough: Passing Collections Between Hosts and Add-Ins](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5).</span></span>  
  
 <span data-ttu-id="d7a44-117">이 파이프라인에 대 한 계약의 네 가지 산술 작업 개체 모델을 정의 합니다: 추가, 빼기, 곱하기, 및 분할 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-117">The contract for this pipeline defines an object model of four arithmetic operations: add, subtract, multiply, and divide.</span></span> <span data-ttu-id="d7a44-118">호스트가 2 + 2와 같은 계산 수식을 사용 하 여 추가 기능에서 제공 하 고 추가 호스트에 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-118">The host provides the add-in with an equation to calculate, such as 2 + 2, and the add-in returns the result to the host.</span></span>  
  
 <span data-ttu-id="d7a44-119">버전 2는 계산기 추가 기능에 추가 계산 기능을 제공 하 고 버전 관리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-119">Version 2 of the calculator add-in provides more calculating possibilities and demonstrates versioning.</span></span> <span data-ttu-id="d7a44-120">설명한 것 [연습: 호스트 변경 내용으로 사용 하도록 설정 하면 이전 버전과 호환성](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-120">It is described in [Walkthrough: Enabling Backward Compatibility as Your Host Changes](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d7a44-121">전제 조건</span><span class="sxs-lookup"><span data-stu-id="d7a44-121">Prerequisites</span></span>  
 <span data-ttu-id="d7a44-122">이 연습을 진행하려면 먼저 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-122">You need the following to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="d7a44-123">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d7a44-123">Visual Studio.</span></span>  
  
## <a name="creating-a-visual-studio-solution"></a><span data-ttu-id="d7a44-124">Visual Studio 솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="d7a44-124">Creating a Visual Studio Solution</span></span>  
 <span data-ttu-id="d7a44-125">파이프라인 세그먼트의 프로젝트를 포함 하도록 Visual Studio에서 솔루션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-125">Use a solution in Visual Studio to contain the projects of your pipeline segments.</span></span>  
  
#### <a name="to-create-the-pipeline-solution"></a><span data-ttu-id="d7a44-126">파이프라인 솔루션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d7a44-126">To create the pipeline solution</span></span>  
  
1.  <span data-ttu-id="d7a44-127">Visual Studio에서 명명 된 새 프로젝트를 만듭니다 `Calc1Contract`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-127">In Visual Studio, create a new project named `Calc1Contract`.</span></span> <span data-ttu-id="d7a44-128">기반으로 합니다 **클래스 라이브러리** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="d7a44-128">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="d7a44-129">솔루션의 이름을 `CalculatorV1`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-129">Name the solution `CalculatorV1`.</span></span>  
  
## <a name="creating-the-pipeline-directory-structure"></a><span data-ttu-id="d7a44-130">파이프라인 디렉터리 구조 만들기</span><span class="sxs-lookup"><span data-stu-id="d7a44-130">Creating the Pipeline Directory Structure</span></span>  
 <span data-ttu-id="d7a44-131">추가 기능 모델은 지정 된 디렉터리 구조에 배치 될 파이프라인 세그먼트 어셈블리 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-131">The add-in model requires the pipeline segment assemblies to be placed in a specified directory structure.</span></span> <span data-ttu-id="d7a44-132">파이프라인 구조에 대 한 자세한 내용은 참조 하세요. [파이프라인 개발 요구 사항](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-132">For more information about the pipeline structure, see [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
#### <a name="to-create-the-pipeline-directory-structure"></a><span data-ttu-id="d7a44-133">파이프라인 디렉터리 구조를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d7a44-133">To create the pipeline directory structure</span></span>  
  
1.  <span data-ttu-id="d7a44-134">어디서 나 컴퓨터에 응용 프로그램 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-134">Create an application folder anywhere on your computer.</span></span>  
  
2.  <span data-ttu-id="d7a44-135">해당 폴더에서 다음 구조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-135">In that folder, create the following structure:</span></span>  
  
    ```  
    Pipeline  
      AddIns  
        CalcV1  
        CalcV2  
      AddInSideAdapters  
      AddInViews  
      Contracts  
      HostSideAdapters  
    ```  
  
     <span data-ttu-id="d7a44-136">파이프라인 폴더 구조에 응용 프로그램 폴더에 배치할 필요는 없습니다. 편의 위해 여기 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-136">It is not necessary to put the pipeline folder structure in your application folder; it is done here only for convenience.</span></span> <span data-ttu-id="d7a44-137">연습을 적절 한 단계에서 파이프라인 폴더 구조가 다른 위치에 코드를 변경 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-137">At the appropriate step, the walkthrough explains how to change the code if the pipeline folder structure is in a different location.</span></span> <span data-ttu-id="d7a44-138">디렉터리 요구 사항에 파이프라인의 설명을 참조 하세요 [파이프라인 개발 요구 사항](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-138">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d7a44-139">합니다 `CalcV2` 폴더는이 연습에서 사용 되지 않으므로 자리 표시자 [연습: 호스트 변경 내용으로 사용 하도록 설정 하면 이전 버전과 호환성](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-139">The `CalcV2` folder is not used in this walkthrough; it is a placeholder for [Walkthrough: Enabling Backward Compatibility as Your Host Changes](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="creating-the-contract-and-views"></a><span data-ttu-id="d7a44-140">계약 및 뷰 만들기</span><span class="sxs-lookup"><span data-stu-id="d7a44-140">Creating the Contract and Views</span></span>  
 <span data-ttu-id="d7a44-141">이 파이프라인에 대 한 계약 세그먼트를 정의 합니다 `ICalc1Contract` 4 개의 메서드를 정의 하는 인터페이스: `add`를 `subtract`, `multiply`, 및 `divide`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-141">The contract segment for this pipeline defines the `ICalc1Contract` interface, which defines four methods: `add`, `subtract`, `multiply`, and `divide`.</span></span>  
  
#### <a name="to-create-the-contract"></a><span data-ttu-id="d7a44-142">계약을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d7a44-142">To create the contract</span></span>  
  
1.  <span data-ttu-id="d7a44-143">명명 된 Visual Studio 솔루션에서 `CalculatorV1`엽니다는 `Calc1Contract` 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="d7a44-143">In the Visual Studio solution named `CalculatorV1`, open the `Calc1Contract` project.</span></span>  
  
2.  <span data-ttu-id="d7a44-144">**솔루션 탐색기**에 다음 어셈블리에 대 한 참조를 추가 합니다 `Calc1Contract` 프로젝트:</span><span class="sxs-lookup"><span data-stu-id="d7a44-144">In **Solution Explorer**, add references to the following assemblies to the `Calc1Contract` project:</span></span>  
  
     <span data-ttu-id="d7a44-145">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="d7a44-145">System.AddIn.Contract.dll</span></span>  
  
     <span data-ttu-id="d7a44-146">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="d7a44-146">System.AddIn.dll</span></span>  
  
3.  <span data-ttu-id="d7a44-147">**솔루션 탐색기**에 새로 추가 되는 기본 클래스를 제외 **클래스 라이브러리** 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-147">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects.</span></span>  
  
4.  <span data-ttu-id="d7a44-148">**솔루션 탐색기**, 프로젝트에 새 항목 추가 사용 하 여 합니다 **인터페이스** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="d7a44-148">In **Solution Explorer**, add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="d7a44-149">에 **새 항목 추가** 대화 상자에서 이름 인터페이스 `ICalc1Contract`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-149">In the **Add New Item** dialog box, name the interface `ICalc1Contract`.</span></span>  
  
5.  <span data-ttu-id="d7a44-150">인터페이스 파일에 네임 스페이스 참조를 추가 <xref:System.AddIn.Contract> 고 <xref:System.AddIn.Pipeline>입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-150">In the interface file, add namespace references to <xref:System.AddIn.Contract> and <xref:System.AddIn.Pipeline>.</span></span>  
  
6.  <span data-ttu-id="d7a44-151">다음 코드를 사용 하 여이 계약 세그먼트를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-151">Use the following code to complete this contract segment.</span></span> <span data-ttu-id="d7a44-152">이 인터페이스를 포함 해야 하는 참고를 <xref:System.AddIn.Pipeline.AddInContractAttribute> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-152">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInContractAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  <span data-ttu-id="d7a44-153">필요에 따라 Visual Studio 솔루션을 빌드하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7a44-153">Optionally, build the Visual Studio solution.</span></span> <span data-ttu-id="d7a44-154">최종 절차는 있지만 각 프로시저 각 프로젝트 인지 확인 한 후 빌드 수정 될 때까지 솔루션을 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-154">The solution cannot be run until the final procedure, but building it after each procedure ensures that each project is correct.</span></span>  
  
 <span data-ttu-id="d7a44-155">추가 기능 뷰 및 호스트 보기 때문에 추가 기능에서 일반적으로 동일한 코드를 첫 번째 버전의 추가 기능에서 특히가 동시에 뷰를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-155">Because the add-in view and the host view of the add-in usually have the same code, especially in the first version of an add-in, you can easily create the views at the same time.</span></span> <span data-ttu-id="d7a44-156">하나의 인수에 따라 다릅니다: 추가 기능 뷰 필요를 <xref:System.AddIn.Pipeline.AddInBaseAttribute> 특성을 추가 기능의 호스트 뷰 특성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-156">They differ by only one factor: the add-in view requires the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute, while the host view of the add-in does not require any attributes.</span></span>  
  
#### <a name="to-create-the-add-in-view"></a><span data-ttu-id="d7a44-157">추가 기능 뷰를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d7a44-157">To create the add-in view</span></span>  
  
1.  <span data-ttu-id="d7a44-158">라는 새 프로젝트 추가 `Calc1AddInView` 에 `CalculatorV1` 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-158">Add a new project named `Calc1AddInView` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="d7a44-159">기반으로 합니다 **클래스 라이브러리** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="d7a44-159">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="d7a44-160">**솔루션 탐색기**, 탐색기에 대 한 참조를 추가 합니다 `Calc1AddInView` 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-160">In **Solution Explorer**, add a reference to System.AddIn.dll to the `Calc1AddInView` project.</span></span>  
  
3.  <span data-ttu-id="d7a44-161">**솔루션 탐색기**에 새로 추가 되는 기본 클래스를 제외 **클래스 라이브러리** 프로젝트 및 프로젝트에 새 항목 추가 사용 하 여 합니다 **인터페이스** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="d7a44-161">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="d7a44-162">에 **새 항목 추가** 대화 상자에서 이름 인터페이스 `ICalculator`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-162">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
4.  <span data-ttu-id="d7a44-163">인터페이스 파일에 네임 스페이스 참조를 추가 <xref:System.AddIn.Pipeline>합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-163">In the interface file, add a namespace reference to <xref:System.AddIn.Pipeline>.</span></span>  
  
5.  <span data-ttu-id="d7a44-164">다음 코드를 사용 하 여이 추가 기능 뷰를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-164">Use the following code to complete this add-in view.</span></span> <span data-ttu-id="d7a44-165">이 인터페이스를 포함 해야 하는 참고를 <xref:System.AddIn.Pipeline.AddInBaseAttribute> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-165">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  <span data-ttu-id="d7a44-166">필요에 따라 Visual Studio 솔루션을 빌드하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7a44-166">Optionally, build the Visual Studio solution.</span></span>  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a><span data-ttu-id="d7a44-167">추가 기능의 호스트 뷰를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d7a44-167">To create the host view of the add-in</span></span>  
  
1.  <span data-ttu-id="d7a44-168">라는 새 프로젝트 추가 `Calc1HVA` 에 `CalculatorV1` 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-168">Add a new project named `Calc1HVA` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="d7a44-169">기반으로 합니다 **클래스 라이브러리** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="d7a44-169">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="d7a44-170">**솔루션 탐색기**에 새로 추가 되는 기본 클래스를 제외 **클래스 라이브러리** 프로젝트 및 프로젝트에 새 항목 추가 사용 하 여 합니다 **인터페이스** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="d7a44-170">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="d7a44-171">에 **새 항목 추가** 대화 상자에서 이름 인터페이스 `ICalculator`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-171">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
3.  <span data-ttu-id="d7a44-172">인터페이스 파일에 추가 기능의 호스트 뷰를 완료 하려면 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-172">In the interface file, use the following code to complete the host view of the add-in.</span></span>  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  <span data-ttu-id="d7a44-173">필요에 따라 Visual Studio 솔루션을 빌드하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7a44-173">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in-side-adapter"></a><span data-ttu-id="d7a44-174">추가 기능 쪽 어댑터 만들기</span><span class="sxs-lookup"><span data-stu-id="d7a44-174">Creating the Add-in-side Adapter</span></span>  
 <span data-ttu-id="d7a44-175">이 추가 기능 쪽 어댑터 하나 뷰-계약 어댑터 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-175">This add-in-side adapter consists of one view-to-contract adapter.</span></span> <span data-ttu-id="d7a44-176">이 파이프라인 세그먼트 추가 뷰에서 계약 형식을 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-176">This pipeline segment converts the types from the add-in view to the contract.</span></span>  
  
 <span data-ttu-id="d7a44-177">이 파이프라인에서 추가 기능에서 서비스 호스트를 제공 하 고 형식 호스트에 추가 기능에서 흐름입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-177">In this pipeline, the add-in provides a service to the host, and the types flow from the add-in to the host.</span></span> <span data-ttu-id="d7a44-178">형식이 없습니다. 추가 기능에 호스트에서 흐름을 하기 때문에이 파이프라인의 추가 기능 쪽에서 계약-뷰 어댑터를 포함할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-178">Because no types flow from the host to the add-in, you do not have to include a contract-to-view adapter on the add-in side of this pipeline.</span></span>  
  
#### <a name="to-create-the-add-in-side-adapter"></a><span data-ttu-id="d7a44-179">추가 기능 쪽 어댑터를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d7a44-179">To create the add-in-side adapter</span></span>  
  
1.  <span data-ttu-id="d7a44-180">라는 새 프로젝트 추가 `Calc1AddInSideAdapter` 에 `CalculatorV1` 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-180">Add a new project named `Calc1AddInSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="d7a44-181">기반으로 합니다 **클래스 라이브러리** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="d7a44-181">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="d7a44-182">**솔루션 탐색기**에 다음 어셈블리에 대 한 참조를 추가 합니다 `Calc1AddInSideAdapter` 프로젝트:</span><span class="sxs-lookup"><span data-stu-id="d7a44-182">In **Solution Explorer**, add references to the following assemblies to the `Calc1AddInSideAdapter` project:</span></span>  
  
     <span data-ttu-id="d7a44-183">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="d7a44-183">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="d7a44-184">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="d7a44-184">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="d7a44-185">인접 한 파이프라인 세그먼트에 대 한 프로젝트에 프로젝트 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-185">Add project references to the projects for the adjacent pipeline segments:</span></span>  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  <span data-ttu-id="d7a44-186">각 프로젝트 참조를 선택 및 **속성** 설정 **로컬 복사** 하 **False**합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-186">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="d7a44-187">Visual basic에서 사용 하 여는 **참조** 탭 **프로젝트 속성** 설정 하려면 **로컬 복사** 하 **False** 두 프로젝트 참조에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-187">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="d7a44-188">프로젝트의 기본 클래스 이름 바꾸기 `CalculatorViewToContractAddInSideAdapter`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-188">Rename the project's default class `CalculatorViewToContractAddInSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="d7a44-189">클래스 파일에서 네임 스페이스 참조를 추가 <xref:System.AddIn.Pipeline>합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-189">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="d7a44-190">클래스 파일에서 인접 한 세그먼트에 대 한 네임 스페이스 참조를 추가 합니다. `CalcAddInViews` 고 `CalculatorContracts`입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-190">In the class file, add namespace references for the adjacent segments: `CalcAddInViews` and `CalculatorContracts`.</span></span> <span data-ttu-id="d7a44-191">(이러한 네임 스페이스 참조는 Visual basic에서는 `Calc1AddInView.CalcAddInViews` 및 `Calc1Contract.CalculatorContracts`않으면 Visual Basic 프로젝트에서 기본 네임 스페이스를 해제 했습니다.)</span><span class="sxs-lookup"><span data-stu-id="d7a44-191">(In Visual Basic, these namespace references are `Calc1AddInView.CalcAddInViews` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="d7a44-192">적용 합니다 <xref:System.AddIn.Pipeline.AddInAdapterAttribute> 특성을 `CalculatorViewToContractAddInSideAdapter` 클래스에 추가 기능 쪽 어댑터와 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-192">Apply the <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attribute to the `CalculatorViewToContractAddInSideAdapter` class, to identify it as the add-in-side adapter.</span></span>  
  
9. <span data-ttu-id="d7a44-193">확인 합니다 `CalculatorViewToContractAddInSideAdapter` 클래스 상속 <xref:System.AddIn.Pipeline.ContractBase>의 기본 구현을 제공 하는 합니다 <xref:System.AddIn.Contract.IContract> 인터페이스 및 파이프라인에 대 한 계약 인터페이스를 구현 `ICalc1Contract`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-193">Make the `CalculatorViewToContractAddInSideAdapter` class inherit <xref:System.AddIn.Pipeline.ContractBase>, which provides a default implementation of the <xref:System.AddIn.Contract.IContract> interface, and implement the contract interface for the pipeline, `ICalc1Contract`.</span></span>  
  
10. <span data-ttu-id="d7a44-194">받아들이는 public 생성자를 추가 `ICalculator`private 필드에 캐시를 기본 클래스 생성자를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-194">Add a public constructor that accepts an `ICalculator`, caches it in a private field, and calls the base class constructor.</span></span>  
  
11. <span data-ttu-id="d7a44-195">멤버를 구현 하 `ICalc1Contract`, 해당 멤버를 호출 하기만 하면 됩니다는 `ICalculator` 인스턴스 생성자에 전달 되는 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-195">To implement the members of `ICalc1Contract`, simply call the corresponding members of the `ICalculator` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="d7a44-196">이 보기를 조정 (`ICalculator`) 계약 (`ICalc1Contract`).</span><span class="sxs-lookup"><span data-stu-id="d7a44-196">This adapts the view (`ICalculator`) to the contract (`ICalc1Contract`).</span></span>  
  
     <span data-ttu-id="d7a44-197">다음 코드에서는 완성 된 추가 기능 쪽 어댑터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-197">The following code shows the completed add-in-side adapter.</span></span>  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. <span data-ttu-id="d7a44-198">필요에 따라 Visual Studio 솔루션을 빌드하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7a44-198">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host-side-adapter"></a><span data-ttu-id="d7a44-199">호스트 쪽 어댑터 만들기</span><span class="sxs-lookup"><span data-stu-id="d7a44-199">Creating the Host-side Adapter</span></span>  
 <span data-ttu-id="d7a44-200">이 호스트 쪽 어댑터가 하나의 계약-뷰 어댑터 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-200">This host-side adapter consists of one contract-to-view adapter.</span></span> <span data-ttu-id="d7a44-201">이 세그먼트에는 추가 기능의 호스트 뷰를 계약을 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-201">This segment adapts the contract to the host view of the add-in.</span></span>  
  
 <span data-ttu-id="d7a44-202">이 파이프라인에서 추가 기능에서 서비스를 제공 호스트 및 형식 흐름 호스트에 추가 기능에서.</span><span class="sxs-lookup"><span data-stu-id="d7a44-202">In this pipeline, the add-in provides a service to the host and the types flow from the add-in to the host.</span></span> <span data-ttu-id="d7a44-203">형식이 없습니다. 추가 기능에 호스트에서 흐름을 하기 때문에 뷰-계약 어댑터를 포함할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-203">Because no types flow from the host to the add-in, you do not have to include a view-to-contract adapter.</span></span>  
  
 <span data-ttu-id="d7a44-204">수명 관리를 구현 하려면 사용을 <xref:System.AddIn.Pipeline.ContractHandle> 계약의 수명 토큰을 연결 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-204">To implement lifetime management, use a <xref:System.AddIn.Pipeline.ContractHandle> object to attach a lifetime token to the contract.</span></span> <span data-ttu-id="d7a44-205">작업 수명 관리를 위해이 핸들에 대 한 참조를 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-205">You must keep a reference to this handle in order for lifetime management to work.</span></span> <span data-ttu-id="d7a44-206">토큰이 적용 되 면 더 이상 사용 되지 않으며 가비지 수집에 사용할 수 있도록 하는 경우 개체의 추가 기능 시스템을 삭제할 수 때문에 없는 추가 프로그래밍이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-206">After the token is applied, no additional programming is required because the add-in system can dispose of objects when they are no longer being used and make them available for garbage collection.</span></span> <span data-ttu-id="d7a44-207">자세한 내용은 [수명 관리](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7a44-207">For more information, see [Lifetime Management](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span></span>  
  
#### <a name="to-create-the-host-side-adapter"></a><span data-ttu-id="d7a44-208">호스트 쪽 어댑터를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d7a44-208">To create the host-side adapter</span></span>  
  
1.  <span data-ttu-id="d7a44-209">라는 새 프로젝트 추가 `Calc1HostSideAdapter` 에 `CalculatorV1` 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-209">Add a new project named `Calc1HostSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="d7a44-210">기반으로 합니다 **클래스 라이브러리** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="d7a44-210">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="d7a44-211">**솔루션 탐색기**에 다음 어셈블리에 대 한 참조를 추가 합니다 `Calc1HostSideAdapter` 프로젝트:</span><span class="sxs-lookup"><span data-stu-id="d7a44-211">In **Solution Explorer**, add references to the following assemblies to the `Calc1HostSideAdapter` project:</span></span>  
  
     <span data-ttu-id="d7a44-212">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="d7a44-212">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="d7a44-213">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="d7a44-213">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="d7a44-214">인접 한 세그먼트에 대 한 프로젝트에 프로젝트 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-214">Add project references to the projects for the adjacent segments:</span></span>  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  <span data-ttu-id="d7a44-215">각 프로젝트 참조를 선택 및 **속성** 설정 **로컬 복사** 하 **False**합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-215">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="d7a44-216">Visual basic에서 사용 하 여는 **참조** 탭 **프로젝트 속성** 설정 하려면 **로컬 복사** 하 **False** 두 프로젝트 참조에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-216">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="d7a44-217">프로젝트의 기본 클래스 이름 바꾸기 `CalculatorContractToViewHostSideAdapter`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-217">Rename the project's default class `CalculatorContractToViewHostSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="d7a44-218">클래스 파일에서 네임 스페이스 참조를 추가 <xref:System.AddIn.Pipeline>합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-218">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="d7a44-219">클래스 파일에서 인접 한 세그먼트에 대 한 네임 스페이스 참조를 추가 합니다. `CalcHVAs` 고 `CalculatorContracts`입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-219">In the class file, add namespace references for the adjacent segments: `CalcHVAs` and `CalculatorContracts`.</span></span> <span data-ttu-id="d7a44-220">(이러한 네임 스페이스 참조는 Visual basic에서는 `Calc1HVA.CalcHVAs` 및 `Calc1Contract.CalculatorContracts`않으면 Visual Basic 프로젝트에서 기본 네임 스페이스를 해제 했습니다.)</span><span class="sxs-lookup"><span data-stu-id="d7a44-220">(In Visual Basic, these namespace references are `Calc1HVA.CalcHVAs` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="d7a44-221">적용 합니다 <xref:System.AddIn.Pipeline.HostAdapterAttribute> 특성을 `CalculatorContractToViewHostSideAdapter` 클래스에 호스트 측 어댑터 세그먼트로 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-221">Apply the <xref:System.AddIn.Pipeline.HostAdapterAttribute> attribute to the `CalculatorContractToViewHostSideAdapter` class, to identify it as the host-side adapter segment.</span></span>  
  
9. <span data-ttu-id="d7a44-222">확인 합니다 `CalculatorContractToViewHostSideAdapter` 추가 기능의 호스트 뷰를 나타내는 인터페이스를 구현 하는 클래스: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` Visual basic에서).</span><span class="sxs-lookup"><span data-stu-id="d7a44-222">Make the `CalculatorContractToViewHostSideAdapter` class implement the interface that represents the host view of the add-in: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).</span></span>  
  
10. <span data-ttu-id="d7a44-223">파이프라인 계약 형식을 받아들이는 public 생성자를 추가 `ICalc1Contract`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-223">Add a public constructor that accepts the pipeline contract type, `ICalc1Contract`.</span></span> <span data-ttu-id="d7a44-224">생성자는 계약에 대 한 참조를 캐시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-224">The constructor must cache the reference to the contract.</span></span> <span data-ttu-id="d7a44-225">만들기 및 새 캐시도 해야 <xref:System.AddIn.Pipeline.ContractHandle> 추가 기능의 수명을 관리 하는 계약에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-225">It must also create and cache a new <xref:System.AddIn.Pipeline.ContractHandle> for the contract, to manage the lifetime of the add-in.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d7a44-226"><xref:System.AddIn.Pipeline.ContractHandle> 수명 관리 하는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-226">The <xref:System.AddIn.Pipeline.ContractHandle> is critical to lifetime management.</span></span> <span data-ttu-id="d7a44-227">에 대 한 참조를 유지 하지 못하는 경우를 <xref:System.AddIn.Pipeline.ContractHandle> 개체를 가비지 컬렉션 후 회수는 프로그램에서 사용 되지 않는 경우 파이프라인 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-227">If you fail to keep a reference to the <xref:System.AddIn.Pipeline.ContractHandle> object, garbage collection will reclaim it, and the pipeline will shut down when your program does not expect it.</span></span> <span data-ttu-id="d7a44-228">와 같은 진단 하기 어려운 오류가 발생할 수 있습니다이 <xref:System.AppDomainUnloadedException>합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-228">This can lead to errors that are difficult to diagnose, such as <xref:System.AppDomainUnloadedException>.</span></span> <span data-ttu-id="d7a44-229">종료는 파이프라인의 일반 단계 이므로이 조건은 오류로 검색할 수명 관리 코드에 대 한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-229">Shutdown is a normal stage in the life of a pipeline, so there is no way for the lifetime management code to detect that this condition is an error.</span></span>  
  
11. <span data-ttu-id="d7a44-230">멤버를 구현 하 `ICalculator`, 해당 멤버를 호출 하기만 하면 됩니다는 `ICalc1Contract` 인스턴스 생성자에 전달 되는 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-230">To implement the members of `ICalculator`, simply call the corresponding members of the `ICalc1Contract` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="d7a44-231">이 적응 계약 (`ICalc1Contract`) 보기로 (`ICalculator`).</span><span class="sxs-lookup"><span data-stu-id="d7a44-231">This adapts the contract (`ICalc1Contract`) to the view (`ICalculator`).</span></span>  
  
     <span data-ttu-id="d7a44-232">다음 코드에서는 완성 된 호스트 쪽 어댑터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-232">The following code shows the completed host-side adapter.</span></span>  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. <span data-ttu-id="d7a44-233">필요에 따라 Visual Studio 솔루션을 빌드하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7a44-233">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host"></a><span data-ttu-id="d7a44-234">호스트 만들기</span><span class="sxs-lookup"><span data-stu-id="d7a44-234">Creating the Host</span></span>  
 <span data-ttu-id="d7a44-235">호스트 응용 프로그램 추가 기능에서 추가 기능의 호스트 뷰를 통해 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-235">A host application interacts with the add-in through the host view of the add-in.</span></span> <span data-ttu-id="d7a44-236">추가 기능 검색 및 활성화 메서드 제공한 사용 합니다 <xref:System.AddIn.Hosting.AddInStore> 고 <xref:System.AddIn.Hosting.AddInToken> 다음을 수행 하는 클래스:</span><span class="sxs-lookup"><span data-stu-id="d7a44-236">It uses add-in discovery and activation methods provided by the <xref:System.AddIn.Hosting.AddInStore> and <xref:System.AddIn.Hosting.AddInToken> classes to do the following:</span></span>  
  
-   <span data-ttu-id="d7a44-237">파이프라인 및 추가 정보 캐시를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-237">Update the cache of pipeline and add-in information.</span></span>  
  
-   <span data-ttu-id="d7a44-238">호스트 뷰 유형의 추가 기능 찾기 `ICalculator`, 지정 된 파이프라인 루트 디렉터리 아래입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-238">Find add-ins of the host view type, `ICalculator`, under the specified pipeline root directory.</span></span>  
  
-   <span data-ttu-id="d7a44-239">사용자 지정 하는 추가 기능에서 사용 하 라는 메시지가 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-239">Prompt the user to specify which add-in to use.</span></span>  
  
-   <span data-ttu-id="d7a44-240">선택한 추가 기능에 지정 된 보안 신뢰 수준으로 새 응용 프로그램 도메인에서 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-240">Activate the selected add-in in a new application domain with a specified security trust level.</span></span>  
  
-   <span data-ttu-id="d7a44-241">사용자 지정 실행 `RunCalculator` 메서드를 추가 기능에 호스트 뷰로 지정 된 대로 추가-메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-241">Run the custom `RunCalculator` method, which calls the add-in's methods as specified by the host view of the add-in.</span></span>  
  
#### <a name="to-create-the-host"></a><span data-ttu-id="d7a44-242">호스트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d7a44-242">To create the host</span></span>  
  
1.  <span data-ttu-id="d7a44-243">라는 새 프로젝트 추가 `Calc1Host` 에 `CalculatorV1` 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-243">Add a new project named `Calc1Host` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="d7a44-244">기반으로 합니다 **콘솔 응용 프로그램** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="d7a44-244">Base it on the **Console Application** template.</span></span>  
  
2.  <span data-ttu-id="d7a44-245">**솔루션 탐색기**, 탐색기에 대 한 참조를 추가 합니다 `Calc1Host` 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-245">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the `Calc1Host` project.</span></span>  
  
3.  <span data-ttu-id="d7a44-246">프로젝트 참조를 추가 합니다 `Calc1HVA` 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-246">Add a project reference to the `Calc1HVA` project.</span></span> <span data-ttu-id="d7a44-247">프로젝트 참조를 선택 및 **속성** 설정 **로컬 복사** 하 **False**합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-247">Select the project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="d7a44-248">Visual basic에서 사용 하 여는 **참조** 탭 **프로젝트 속성** 설정 하려면 **로컬 복사** 하 **False**합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-248">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False**.</span></span>  
  
4.  <span data-ttu-id="d7a44-249">클래스 파일 (Visual Basic의 모듈)의 이름을 `MathHost1`입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-249">Rename the class file (module in Visual Basic) `MathHost1`.</span></span>  
  
5.  <span data-ttu-id="d7a44-250">Visual basic에서 사용 하 여는 **응용 프로그램** 탭의 **프로젝트 속성** 대화 상자를 **시작 개체** 에 **Sub Main**합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-250">In Visual Basic, use the **Application** tab of the **Project Properties** dialog box to set **Startup object** to **Sub Main**.</span></span>  
  
6.  <span data-ttu-id="d7a44-251">클래스 또는 모듈 파일에서 네임 스페이스 참조를 추가 <xref:System.AddIn.Hosting>합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-251">In the class or module file, add a namespace reference to <xref:System.AddIn.Hosting>.</span></span>  
  
7.  <span data-ttu-id="d7a44-252">클래스 또는 모듈 파일에서의 추가 기능 호스트 뷰에 대 한 네임 스페이스 참조를 추가 합니다. `CalcHVAs`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-252">In the class or module file, add a namespace reference for the host view of the add-in: `CalcHVAs`.</span></span> <span data-ttu-id="d7a44-253">(Visual Basic에서이 네임 스페이스 참조는 `Calc1HVA.CalcHVAs`않으면 Visual Basic 프로젝트에서 기본 네임 스페이스를 해제 했습니다.)</span><span class="sxs-lookup"><span data-stu-id="d7a44-253">(In Visual Basic, this namespace reference is `Calc1HVA.CalcHVAs`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="d7a44-254">**솔루션 탐색기**, 솔루션을 선택 및 합니다 **프로젝트** 메뉴 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-254">In **Solution Explorer**, select the solution and from the **Project** menu choose **Properties**.</span></span> <span data-ttu-id="d7a44-255">에 **솔루션 속성 페이지** 대화 상자에서를 **단일 시작 프로젝트** 이 호스트 응용 프로그램 프로젝트를 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-255">In the **Solution Property Pages** dialog box, set the **Single Startup Project** to be this host application project.</span></span>  
  
9. <span data-ttu-id="d7a44-256">클래스 또는 모듈 파일에서 사용 된 <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> 캐시를 업데이트 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-256">In the class or module file, use the <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> method to update the cache.</span></span> <span data-ttu-id="d7a44-257">사용 된 <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> 토큰의 컬렉션을 가져와서 사용 하는 메서드는 <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> 추가 기능을 활성화 하는 방법.</span><span class="sxs-lookup"><span data-stu-id="d7a44-257">Use the <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> method to get a collection of tokens, and use the <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> method to activate an add-in.</span></span>  
  
     <span data-ttu-id="d7a44-258">다음 코드에서는 완성 된 호스트 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-258">The following code shows the completed host application.</span></span>  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="d7a44-259">이 코드는 파이프라인 폴더 구조가 응용 프로그램 폴더에 있는지를 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-259">This code assumes that the pipeline folder structure is located in the application folder.</span></span> <span data-ttu-id="d7a44-260">에 있는 경우 다른 위치를 설정 하는 코드 줄을 변경 합니다 `addInRoot` 변수 변수의 파이프라인 디렉터리 구조에 대 한 경로 포함 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-260">If you located it elsewhere, change the line of code that sets the `addInRoot` variable, so that the variable contains the path to your pipeline directory structure.</span></span>  
  
     <span data-ttu-id="d7a44-261">코드를 사용 하는 `ChooseCalculator` 토큰을 나열 하 고 추가 기능을 선택 하 라는 메시지가 메서드.</span><span class="sxs-lookup"><span data-stu-id="d7a44-261">The code uses a `ChooseCalculator` method to list the tokens and to prompt the user to choose an add-in.</span></span> <span data-ttu-id="d7a44-262">`RunCalculator` 메서드 간단한 수학 식에 대 한 라는 메시지를 사용 하 여 식을 구문 분석 된 `Parser` 클래스 및 추가 기능에서 반환 하는 결과 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-262">The `RunCalculator` method prompts the user for simple math expressions, parses the expressions using the `Parser` class, and displays the results returned by the add-in.</span></span>  
  
10. <span data-ttu-id="d7a44-263">필요에 따라 Visual Studio 솔루션을 빌드하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7a44-263">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in"></a><span data-ttu-id="d7a44-264">추가 기능 만들기</span><span class="sxs-lookup"><span data-stu-id="d7a44-264">Creating the Add-In</span></span>  
 <span data-ttu-id="d7a44-265">추가 기능에서 추가 기능 뷰 지정한 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-265">An add-in implements the methods specified by the add-in view.</span></span> <span data-ttu-id="d7a44-266">이 추가 기능에서 구현 된 `Add`, `Subtract`, `Multiply`, 및 `Divide` 작업과 호스트에 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-266">This add-in implements the `Add`, `Subtract`, `Multiply`, and `Divide` operations and returns the results to the host.</span></span>  
  
#### <a name="to-create-the-add-in"></a><span data-ttu-id="d7a44-267">추가 기능을 만드는</span><span class="sxs-lookup"><span data-stu-id="d7a44-267">To create the add-in</span></span>  
  
1.  <span data-ttu-id="d7a44-268">라는 새 프로젝트 추가 `AddInCalcV1` 에 `CalculatorV1` 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-268">Add a new project named `AddInCalcV1` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="d7a44-269">기반으로 합니다 **클래스 라이브러리** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="d7a44-269">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="d7a44-270">**솔루션 탐색기**, 프로젝트 탐색기에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-270">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the project.</span></span>  
  
3.  <span data-ttu-id="d7a44-271">프로젝트 참조를 추가 합니다 `Calc1AddInView` 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-271">Add a project reference to the `Calc1AddInView` project.</span></span> <span data-ttu-id="d7a44-272">프로젝트 참조를 선택 및 **속성**설정 **로컬 복사** 하 **False**합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-272">Select the project reference, and in **Properties**, set **Copy Local** to **False**.</span></span> <span data-ttu-id="d7a44-273">Visual basic에서 사용 하 여는 **참조** 탭의 **프로젝트 속성** 설정 하려면 **로컬 복사** 에 **False** 프로젝트 참조에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-273">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the project reference.</span></span>  
  
4.  <span data-ttu-id="d7a44-274">클래스의 이름을 `AddInCalcV1`입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-274">Rename the class `AddInCalcV1`.</span></span>  
  
5.  <span data-ttu-id="d7a44-275">클래스 파일에서 네임 스페이스 참조를 추가 <xref:System.AddIn> , 추가 기능 뷰 세그먼트: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` Visual basic에서).</span><span class="sxs-lookup"><span data-stu-id="d7a44-275">In the class file, add a namespace reference to <xref:System.AddIn> and the add-in view segment: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).</span></span>  
  
6.  <span data-ttu-id="d7a44-276">적용 합니다 <xref:System.AddIn.AddInAttribute> 특성을 `AddInCalcV1` 클래스에 추가 기능으로 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-276">Apply the <xref:System.AddIn.AddInAttribute> attribute to the `AddInCalcV1` class, to identify the class as an add-in.</span></span>  
  
7.  <span data-ttu-id="d7a44-277">확인 합니다 `AddInCalcV1` 추가 기능 뷰를 나타내는 인터페이스를 구현 하는 클래스: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` Visual basic에서).</span><span class="sxs-lookup"><span data-stu-id="d7a44-277">Make the `AddInCalcV1` class implement the interface that represents the add-in view: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).</span></span>  
  
8.  <span data-ttu-id="d7a44-278">멤버를 구현 `ICalculator` 적절 한 계산의 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-278">Implement the members of `ICalculator` by returning the results of the appropriate calculations.</span></span>  
  
     <span data-ttu-id="d7a44-279">다음 코드는 완료 된 추가 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-279">The following code shows the completed add-in.</span></span>  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. <span data-ttu-id="d7a44-280">필요에 따라 Visual Studio 솔루션을 빌드하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7a44-280">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="deploying-the-pipeline"></a><span data-ttu-id="d7a44-281">파이프라인 배포</span><span class="sxs-lookup"><span data-stu-id="d7a44-281">Deploying the Pipeline</span></span>  
 <span data-ttu-id="d7a44-282">이제를 빌드하고 파이프라인 디렉터리 구조에 추가 기능 세그먼트를 배포할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-282">You are now ready to build and deploy the add-in segments to the required pipeline directory structure.</span></span>  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a><span data-ttu-id="d7a44-283">파이프라인 세그먼트를 배포 하려면</span><span class="sxs-lookup"><span data-stu-id="d7a44-283">To deploy the segments to the pipeline</span></span>  
  
1.  <span data-ttu-id="d7a44-284">솔루션의 각 프로젝트에 대해 사용 하 여 합니다 **빌드** 탭 **프로젝트 속성** (합니다 **컴파일** Visual Basic의 탭)의 값을 설정 하는 **출력 경로**  (합니다 **빌드 출력 경로** Visual basic에서).</span><span class="sxs-lookup"><span data-stu-id="d7a44-284">For each project in the solution, use the **Build** tab of **Project Properties** (the **Compile** tab in Visual Basic) to set the value of the **Output path** (the **Build output path** in Visual Basic).</span></span> <span data-ttu-id="d7a44-285">응용 프로그램 폴더 이름을 지정할 경우 `MyApp`, 프로젝트는 다음 폴더에 넣는 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="d7a44-285">If you named your application folder `MyApp`, for example, your projects would build into the following folders:</span></span>  
  
    |<span data-ttu-id="d7a44-286">프로젝트</span><span class="sxs-lookup"><span data-stu-id="d7a44-286">Project</span></span>|<span data-ttu-id="d7a44-287">Path</span><span class="sxs-lookup"><span data-stu-id="d7a44-287">Path</span></span>|  
    |-------------|----------|  
    |<span data-ttu-id="d7a44-288">AddInCalcV1</span><span class="sxs-lookup"><span data-stu-id="d7a44-288">AddInCalcV1</span></span>|<span data-ttu-id="d7a44-289">MyApp\Pipeline\AddIns\CalcV1</span><span class="sxs-lookup"><span data-stu-id="d7a44-289">MyApp\Pipeline\AddIns\CalcV1</span></span>|  
    |<span data-ttu-id="d7a44-290">Calc1AddInSideAdapter</span><span class="sxs-lookup"><span data-stu-id="d7a44-290">Calc1AddInSideAdapter</span></span>|<span data-ttu-id="d7a44-291">MyApp\Pipeline\AddInSideAdapters</span><span class="sxs-lookup"><span data-stu-id="d7a44-291">MyApp\Pipeline\AddInSideAdapters</span></span>|  
    |<span data-ttu-id="d7a44-292">Calc1AddInView</span><span class="sxs-lookup"><span data-stu-id="d7a44-292">Calc1AddInView</span></span>|<span data-ttu-id="d7a44-293">MyApp\Pipeline\AddInViews</span><span class="sxs-lookup"><span data-stu-id="d7a44-293">MyApp\Pipeline\AddInViews</span></span>|  
    |<span data-ttu-id="d7a44-294">Calc1Contract</span><span class="sxs-lookup"><span data-stu-id="d7a44-294">Calc1Contract</span></span>|<span data-ttu-id="d7a44-295">MyApp\Pipeline\Contracts</span><span class="sxs-lookup"><span data-stu-id="d7a44-295">MyApp\Pipeline\Contracts</span></span>|  
    |<span data-ttu-id="d7a44-296">Calc1Host</span><span class="sxs-lookup"><span data-stu-id="d7a44-296">Calc1Host</span></span>|<span data-ttu-id="d7a44-297">MyApp</span><span class="sxs-lookup"><span data-stu-id="d7a44-297">MyApp</span></span>|  
    |<span data-ttu-id="d7a44-298">Calc1HostSideAdapter</span><span class="sxs-lookup"><span data-stu-id="d7a44-298">Calc1HostSideAdapter</span></span>|<span data-ttu-id="d7a44-299">MyApp\Pipeline\HostSideAdapters</span><span class="sxs-lookup"><span data-stu-id="d7a44-299">MyApp\Pipeline\HostSideAdapters</span></span>|  
    |<span data-ttu-id="d7a44-300">Calc1HVA</span><span class="sxs-lookup"><span data-stu-id="d7a44-300">Calc1HVA</span></span>|<span data-ttu-id="d7a44-301">MyApp</span><span class="sxs-lookup"><span data-stu-id="d7a44-301">MyApp</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="d7a44-302">응용 프로그램 폴더 이외의 위치에서 파이프라인 폴더 구조를 결정 하는 경우 그에 따라 표에 표시 된 경로 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-302">If you decided to put your pipeline folder structure in a location other than your application folder, you must modify the paths shown in the table accordingly.</span></span> <span data-ttu-id="d7a44-303">디렉터리 요구 사항에 파이프라인의 설명을 참조 하세요 [파이프라인 개발 요구 사항](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-303">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
2.  <span data-ttu-id="d7a44-304">Visual Studio 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-304">Build the Visual Studio solution.</span></span>  
  
3.  <span data-ttu-id="d7a44-305">응용 프로그램 및 파이프라인 디렉터리 어셈블리 올바른 디렉터리에 복사 된 하 고 어셈블리의 추가 복사본이 된 잘못 된 폴더에 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-305">Check the application and pipeline directories to ensure that the assemblies were copied to the correct directories and that no extra copies of assemblies were installed in the wrong folders.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d7a44-306">변경 되지 않은 경우 **로컬 복사** 에 **False** 에 대 한 합니다 `Calc1AddInView` 프로젝트에서 참조를 `AddInCalcV1` 프로젝트 로더 컨텍스트 문제 못합니다에서 추가 기능을 찾을.</span><span class="sxs-lookup"><span data-stu-id="d7a44-306">If you did not change **Copy Local** to **False** for the `Calc1AddInView` project reference in the `AddInCalcV1` project, loader context problems will prevent the add-in from being located.</span></span>  
  
     <span data-ttu-id="d7a44-307">배포 파이프라인에 대 한 내용은 [파이프라인 개발 요구 사항](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-307">For information about deploying to the pipeline, see [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
## <a name="running-the-host-application"></a><span data-ttu-id="d7a44-308">호스트 응용 프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="d7a44-308">Running the Host Application</span></span>  
 <span data-ttu-id="d7a44-309">이제 호스트를 실행 하 고 추가 기능에서 상호 작용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-309">You are now ready to run the host and interact with the add-in.</span></span>  
  
#### <a name="to-run-the-host-application"></a><span data-ttu-id="d7a44-310">호스트 응용 프로그램을 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="d7a44-310">To run the host application</span></span>  
  
1.  <span data-ttu-id="d7a44-311">명령 프롬프트에서 응용 프로그램 디렉터리로 이동 하 고 호스트 응용 프로그램을 실행 `Calc1Host.exe`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-311">At the command prompt, go to the application directory and run the host application, `Calc1Host.exe`.</span></span>  
  
2.  <span data-ttu-id="d7a44-312">호스트 사용 가능한 추가 기능을 모두 찾습니다 해당 형식의 추가 기능을 선택 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-312">The host finds all available add-ins of its type and prompts you to select an add-in.</span></span> <span data-ttu-id="d7a44-313">입력 **1** 추가 기능에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-313">Enter **1** for the only available add-in.</span></span>  
  
3.  <span data-ttu-id="d7a44-314">와 같은 수식을 계산기에서 입력 **2 + 2**합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-314">Enter an equation for the calculator, such as **2 + 2**.</span></span> <span data-ttu-id="d7a44-315">숫자 및 연산자 사이 공백이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-315">There must be spaces between the numbers and the operator.</span></span>  
  
4.  <span data-ttu-id="d7a44-316">형식 **종료** 누릅니다 합니다 **Enter** 키 응용 프로그램을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a44-316">Type **exit** and press the **Enter** key to close the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7a44-317">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7a44-317">See Also</span></span>  
- [<span data-ttu-id="d7a44-318">연습: 호스트 변경으로 이전 버전과 호환성 설정</span><span class="sxs-lookup"><span data-stu-id="d7a44-318">Walkthrough: Enabling Backward Compatibility as Your Host Changes</span></span>](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
-  [<span data-ttu-id="d7a44-319">연습: 호스트와 추가 기능 간의 컬렉션 전달</span><span class="sxs-lookup"><span data-stu-id="d7a44-319">Walkthrough: Passing Collections Between Hosts and Add-Ins</span></span>](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
-  [<span data-ttu-id="d7a44-320">파이프라인 개발 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7a44-320">Pipeline Development Requirements</span></span>](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
-  [<span data-ttu-id="d7a44-321">계약, 뷰 및 어댑터</span><span class="sxs-lookup"><span data-stu-id="d7a44-321">Contracts, Views, and Adapters</span></span>](https://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c)  
-  [<span data-ttu-id="d7a44-322">파이프라인 개발</span><span class="sxs-lookup"><span data-stu-id="d7a44-322">Pipeline Development</span></span>](../../../docs/framework/add-ins/pipeline-development.md)
