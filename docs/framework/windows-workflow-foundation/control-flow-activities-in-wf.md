---
title: "WF의 흐름 제어 활동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6892885b-f7c5-4aea-8f5e-28863fb4ae75
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 825f2487a89805365d3376986af0b0d098c20bca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="control-flow-activities-in-wf"></a><span data-ttu-id="bd299-102">WF의 흐름 제어 활동</span><span class="sxs-lookup"><span data-stu-id="bd299-102">Control Flow Activities in WF</span></span>
<span data-ttu-id="bd299-103">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]에서는 워크플로 내의 실행 흐름 제어를 위한 다양한 활동을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bd299-103">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] provides several activities for controlling flow of execution within a workflow.</span></span> <span data-ttu-id="bd299-104">`Switch` 및 `If`와 같은 활동은 프로그래밍 환경(예: [!INCLUDE[csprcs](../../../includes/csprcs-md.md)])에서와 비슷한 흐름 제어 구조를 구현하지만, `Pick`과 같은 활동은 새 프로그래밍 구조를 모델링합니다.</span><span class="sxs-lookup"><span data-stu-id="bd299-104">Some of these activities (such as `Switch` and `If`) implement flow control structures similar to those in programming environments such as [!INCLUDE[csprcs](../../../includes/csprcs-md.md)], while others (such as `Pick`) model new programming structures.</span></span>  
  
 <span data-ttu-id="bd299-105">`Parallel` 및 `ParallelForEach`와 같은 활동은 동시에 실행할 여러 자식 활동을 예약하지만, 스레드는 워크플로별로 하나씩만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd299-105">Note that while activities such as the `Parallel` and `ParallelForEach` activities schedule multiple child activities for execution simultaneously, only a single thread is used for a workflow.</span></span> <span data-ttu-id="bd299-106">이러한 활동의 각 자식 활동은 순차적으로 실행되며 이전 활동이 완료되거나 유휴 상태로 전환될 때까지는 다음 활동이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd299-106">Each child activity of these activities executes sequentially and successive activities do not execute until previous activities either complete or go idle.</span></span> <span data-ttu-id="bd299-107">따라서 이러한 활동은 다른 활동을 차단하는 여러 활동을 인터리브하게 실행해야 하는 응용 프로그램에 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="bd299-107">As a result, these activities are most useful for applications in which several potentially blocking activities must execute in an interleaved fashion.</span></span> <span data-ttu-id="bd299-108">이러한 활동의 자식 활동이 유휴 상태로 전환되지 않는 경우에는 `Parallel` 활동은 `Sequence` 활동처럼 실행되고 `ParallelForEach` 활동은 `ForEach` 활동처럼 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd299-108">If none of the child activities of these activities go idle, a `Parallel` activity executes just like a `Sequence` activity, and a `ParallelForEach` activity executes just like a `ForEach` activity.</span></span> <span data-ttu-id="bd299-109">하지만 비동기 활동(예: <xref:System.Activities.AsyncCodeActivity>에서 파생된 활동) 또는 메시징 활동이 사용되는 경우에는 자식 활동이 메시지를 받거나 비동기 작업을 완료할 때가지 기다리는 동안 제어가 다음 분기로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd299-109">If, however, asynchronous activities (such as activities that derive from <xref:System.Activities.AsyncCodeActivity>) or messaging activities are used, control will pass to the next branch while the child activity waits for its message to be received or its asynchronous work to be completed.</span></span>  
  
## <a name="flow-control-activities"></a><span data-ttu-id="bd299-110">흐름 제어 활동</span><span class="sxs-lookup"><span data-stu-id="bd299-110">Flow control activities</span></span>  
  
|<span data-ttu-id="bd299-111">동작</span><span class="sxs-lookup"><span data-stu-id="bd299-111">Activity</span></span>|<span data-ttu-id="bd299-112">설명</span><span class="sxs-lookup"><span data-stu-id="bd299-112">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.DoWhile>|<span data-ttu-id="bd299-113">포함된 활동을 한 번 실행하면 조건이 `true`인 동안 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd299-113">Executes the contained activities once and continues to do so while a condition is `true`.</span></span>|  
|<xref:System.Activities.Statements.ForEach%601>|<span data-ttu-id="bd299-114">컬렉션의 각 요소에 대한 포함 문을 직렬로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bd299-114">Executes an embedded statement in sequence for each element in a collection.</span></span> <span data-ttu-id="bd299-115"><xref:System.Activities.Statements.ForEach%601>는 키워드 `foreach`와 유사하지만 언어 문이 아니라 작업으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd299-115"><xref:System.Activities.Statements.ForEach%601> is similar to the keyword `foreach`, but is implemented as an activity rather than a language statement.</span></span>|  
|<xref:System.Activities.Statements.If>|<span data-ttu-id="bd299-116">조건이 `true`이면 포함된 활동을 실행하고, 조건이 <xref:System.Activities.Statements.If.Else%2A>이면 `false` 속성에 포함된 활동을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd299-116">Executes contained activities if a condition is `true`, and can execute activities contained in the <xref:System.Activities.Statements.If.Else%2A> property if the condition is `false`.</span></span>|  
|<xref:System.Activities.Statements.Parallel>|<span data-ttu-id="bd299-117">포함된 활동을 병렬로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bd299-117">Executes contained activities in parallel.</span></span>|  
|<xref:System.Activities.Statements.ParallelForEach%601>|<span data-ttu-id="bd299-118">컬렉션의 각 요소에 대한 포함 문을 병렬로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bd299-118">Executes an embedded statement in parallel for each element in a collection.</span></span>|  
|<xref:System.Activities.Statements.Pick>|<span data-ttu-id="bd299-119">이벤트 기반 제어 흐름 모델링을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bd299-119">Provides event-based control flow modeling.</span></span>|  
|<xref:System.Activities.Statements.PickBranch>|<span data-ttu-id="bd299-120"><xref:System.Activities.Statements.Pick> 활동의 잠재적 실행 경로를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bd299-120">Represents a potential path of execution in a <xref:System.Activities.Statements.Pick> activity.</span></span>|  
|<xref:System.Activities.Statements.Sequence>|<span data-ttu-id="bd299-121">포함된 활동을 차례로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bd299-121">Executes contained activities in sequence.</span></span>|  
|<xref:System.Activities.Statements.Switch%601>|<span data-ttu-id="bd299-122">지정된 식의 값을 기준으로 많은 활동 중에서 실행할 활동 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bd299-122">Selects one choice from a number of activities to execute, based on the value of a given expression.</span></span>|  
|<xref:System.Activities.Statements.While>|<span data-ttu-id="bd299-123">조건이 `true`이면 포함된 활동을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bd299-123">Executes contained activities while a condition is `true`.</span></span>|
