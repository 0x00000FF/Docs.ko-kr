---
title: "활동 유효성 검사 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25a4eccb-b8fc-4857-a01d-2683b6341219
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d17a640db012730ae8f5329f4e625823a4f5bff2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="configuring-activity-validation"></a><span data-ttu-id="9e0b6-102">활동 유효성 검사 구성</span><span class="sxs-lookup"><span data-stu-id="9e0b6-102">Configuring Activity Validation</span></span>
<span data-ttu-id="9e0b6-103">활동 유효성 검사를 사용하면 활동 작성자 및 사용자가 활동을 실행하기 이전에 활동 구성 오류를 식별하여 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-103">Activity validation enables activity authors and users to identify and report errors in an activity’s configuration prior to its execution.</span></span> [!INCLUDE[wf](../../../includes/wf-md.md)]<span data-ttu-id="9e0b6-104">에서는 다음과 같은 3가지 유형의 활동 유효성 검사를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-104"> provides the following three types of activity validation:</span></span>  
  
-   <span data-ttu-id="9e0b6-105">`RequiredArgument` 및 `OverloadGroup` 특성</span><span class="sxs-lookup"><span data-stu-id="9e0b6-105">`RequiredArgument` and `OverloadGroup` attributes.</span></span>  
  
-   <span data-ttu-id="9e0b6-106">필수 코드 기반 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="9e0b6-106">Imperative code-based validation.</span></span>  
  
-   <span data-ttu-id="9e0b6-107">선언적 제약 조건</span><span class="sxs-lookup"><span data-stu-id="9e0b6-107">Declarative constraints.</span></span>  
  
 <span data-ttu-id="9e0b6-108">`RequiredArgument` 및 `OverloadGroup` 특성은 활동의 특정 인수가 필수 항목임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-108">`RequiredArgument` and `OverloadGroup` attributes indicate that certain arguments on an activity are required.</span></span> <span data-ttu-id="9e0b6-109">필수 코드 기반 유효성 검사를 사용하면 활동 자체에 대한 유효성을 쉽게 검사할 수 있고, 선언적 제약 조건을 사용하면 활동 및 활동과 포함된 워크플로와의 관계에 대한 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-109">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and declarative constraints enable validation about the activity and its relationship with the containing workflow.</span></span> <span data-ttu-id="9e0b6-110">활동이 유효성 검사 요구 사항에 따라 적절하게 구성되지 않은 경우 유효성 검사 오류 및 경고가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-110">If an activity is not configured properly according to the validation requirements, validation errors and warnings are returned.</span></span> <span data-ttu-id="9e0b6-111">Workflow Designer를 사용하여 포함된 워크플로를 만드는 경우에는 유효성 검사 오류 및 경고가 디자이너에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-111">If the containing workflow is created using the workflow designer, any validation errors and warnings are displayed in the designer.</span></span> <span data-ttu-id="9e0b6-112">Workflow Designer 외부에서 워크플로를 만드는 경우에는 워크플로가 호출되면 유효성 검사 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-112">If the workflow is created outside of the workflow designer any validation errors are returned when the workflow is invoked.</span></span> <span data-ttu-id="9e0b6-113">워크플로를 만드는 방법에 상관없이 유효성 검사 오류가 있는 워크플로는 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-113">Regardless of how the workflow was created, a workflow with validation errors is never allowed to execute.</span></span> <span data-ttu-id="9e0b6-114">이 단원에서는 이러한 유형의 활동 유효성 검사의 개요와 활동 유효성 검사를 호출하는 방법을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-114">This section provides an overview of these types of activity validation and how activity validation is invoked.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e0b6-115">단원 내용</span><span class="sxs-lookup"><span data-stu-id="9e0b6-115">In This Section</span></span>  
 [<span data-ttu-id="9e0b6-116">필수 인수 및 오버로드 그룹</span><span class="sxs-lookup"><span data-stu-id="9e0b6-116">Required Arguments and Overload Groups</span></span>](../../../docs/framework/windows-workflow-foundation/required-arguments-and-overload-groups.md)  
 <span data-ttu-id="9e0b6-117">`RequiredArgument` 및 `OverloadGroup` 특성을 사용하여 유효성 검사를 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-117">Describes how to use the `RequiredArgument` and `OverloadGroup` attributes to provide validation.</span></span>  
  
 [<span data-ttu-id="9e0b6-118">명령형 코드 기반 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="9e0b6-118">Imperative Code-Based Validation</span></span>](../../../docs/framework/windows-workflow-foundation/imperative-code-based-validation.md)  
 <span data-ttu-id="9e0b6-119"><xref:System.Activities.CodeActivity> 및 <xref:System.Activities.NativeActivity> 기반 활동에 대해 코드 기반 유효성 검사를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-119">Describes how to use code-based validation for <xref:System.Activities.CodeActivity> and <xref:System.Activities.NativeActivity> based activities.</span></span>  
  
 [<span data-ttu-id="9e0b6-120">선언적 제약 조건</span><span class="sxs-lookup"><span data-stu-id="9e0b6-120">Declarative Constraints</span></span>](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md)  
 <span data-ttu-id="9e0b6-121">선언적 제약 조건을 사용하여 복잡한 활동 유효성 검사를 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-121">Describes how to use declarative constraints to provide complex activity validation.</span></span>  
  
 [<span data-ttu-id="9e0b6-122">활동 유효성 검사 호출</span><span class="sxs-lookup"><span data-stu-id="9e0b6-122">Invoking Activity Validation</span></span>](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md)  
 <span data-ttu-id="9e0b6-123">활동 유효성 검사가 자동으로 호출되는 시기와 유효성 검사를 명시적으로 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-123">Discusses when activity validation is invoked automatically and how to explicitly invoke validation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9e0b6-124">참조</span><span class="sxs-lookup"><span data-stu-id="9e0b6-124">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9e0b6-125">관련 단원</span><span class="sxs-lookup"><span data-stu-id="9e0b6-125">Related Sections</span></span>
