---
title: ARM(응용 프로그램 도메인 리소스 모니터링) ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2bb2b0dd95877fc6492f6d23a19c14688cd78f7c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133824"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="1795b-102">ARM(응용 프로그램 도메인 리소스 모니터링) ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="1795b-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="1795b-103">이들 이벤트는 응용 프로그램 도메인 상태에 대한 자세한 진단 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="1795b-104">이들 이벤트를 사용하거나 애플리케이션 도메인 리소스 모니터링(ARM) 기능을 사용하여 같은 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="1795b-105">이 범주는 다음 이벤트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="1795b-106">ThreadCreated 이벤트</span><span class="sxs-lookup"><span data-stu-id="1795b-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
-   [<span data-ttu-id="1795b-107">AppDomainMemAllocated 이벤트</span><span class="sxs-lookup"><span data-stu-id="1795b-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
-   [<span data-ttu-id="1795b-108">AppDomainMemSurvived 이벤트</span><span class="sxs-lookup"><span data-stu-id="1795b-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
-   [<span data-ttu-id="1795b-109">ThreadAppDomainEnter 이벤트</span><span class="sxs-lookup"><span data-stu-id="1795b-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
-   [<span data-ttu-id="1795b-110">ThreadTerminated 이벤트</span><span class="sxs-lookup"><span data-stu-id="1795b-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="1795b-111">ThreadCreated 이벤트</span><span class="sxs-lookup"><span data-stu-id="1795b-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="1795b-112">이 이벤트는 런다운 공급자에서만 `ThreadDC` 로서 발생합니다( `AppDomainResourceManagementRundownKeyword` 키워드에서).</span><span class="sxs-lookup"><span data-stu-id="1795b-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="1795b-113">이 이벤트는 이 범주의 런다운 공급자에서 발생하는 유일한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="1795b-114">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="1795b-115">자세한 내용은 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1795b-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="1795b-116">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="1795b-116">Keyword for raising the event</span></span>|<span data-ttu-id="1795b-117">수준</span><span class="sxs-lookup"><span data-stu-id="1795b-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1795b-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="1795b-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="1795b-119">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="1795b-119">Informational(4)</span></span>|  
|<span data-ttu-id="1795b-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="1795b-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="1795b-121">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="1795b-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="1795b-122">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1795b-123">이벤트</span><span class="sxs-lookup"><span data-stu-id="1795b-123">Event</span></span>|<span data-ttu-id="1795b-124">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="1795b-124">Event ID</span></span>|<span data-ttu-id="1795b-125">발생 시기</span><span class="sxs-lookup"><span data-stu-id="1795b-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="1795b-126">85</span><span class="sxs-lookup"><span data-stu-id="1795b-126">85</span></span>|<span data-ttu-id="1795b-127">애플리케이션 도메인에 대한 스레드가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="1795b-128">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="1795b-129">필드 이름</span><span class="sxs-lookup"><span data-stu-id="1795b-129">Field name</span></span>|<span data-ttu-id="1795b-130">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1795b-130">Data type</span></span>|<span data-ttu-id="1795b-131">설명</span><span class="sxs-lookup"><span data-stu-id="1795b-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="1795b-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="1795b-132">ThreadID</span></span>|<span data-ttu-id="1795b-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1795b-133">win:UInt64</span></span>|<span data-ttu-id="1795b-134">만들어진 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="1795b-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="1795b-135">AppDomainID</span></span>|<span data-ttu-id="1795b-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1795b-136">win:UInt64</span></span>|<span data-ttu-id="1795b-137">스레드 활동이 보고되는 애플리케이션 도메인의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="1795b-138">플래그</span><span class="sxs-lookup"><span data-stu-id="1795b-138">Flags</span></span>|<span data-ttu-id="1795b-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1795b-139">win:UInt32</span></span>|<span data-ttu-id="1795b-140">스레드 만들기 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="1795b-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="1795b-141">ManagedThreadIndex</span></span>|<span data-ttu-id="1795b-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1795b-142">win:UInt32</span></span>|<span data-ttu-id="1795b-143">만들어진 스레드의 관리되는 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="1795b-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="1795b-144">OSThreadID</span></span>|<span data-ttu-id="1795b-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1795b-145">win:UInt32</span></span>|<span data-ttu-id="1795b-146">만들어진 스레드의 운영 체제 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="1795b-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1795b-147">ClrInstanceID</span></span>|<span data-ttu-id="1795b-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1795b-148">win:UInt16</span></span>|<span data-ttu-id="1795b-149">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="1795b-150">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1795b-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="1795b-151">AppDomainMemAllocated 이벤트</span><span class="sxs-lookup"><span data-stu-id="1795b-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="1795b-152">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1795b-153">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="1795b-153">Keyword for raising the event</span></span>|<span data-ttu-id="1795b-154">수준</span><span class="sxs-lookup"><span data-stu-id="1795b-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1795b-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="1795b-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="1795b-156">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="1795b-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="1795b-157">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1795b-158">이벤트</span><span class="sxs-lookup"><span data-stu-id="1795b-158">Event</span></span>|<span data-ttu-id="1795b-159">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="1795b-159">Event ID</span></span>|<span data-ttu-id="1795b-160">발생 시기</span><span class="sxs-lookup"><span data-stu-id="1795b-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="1795b-161">83</span><span class="sxs-lookup"><span data-stu-id="1795b-161">83</span></span>|<span data-ttu-id="1795b-162">약 4MB의 모든 메모리가 애플리케이션 도메인에서 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="1795b-163">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="1795b-164">필드 이름</span><span class="sxs-lookup"><span data-stu-id="1795b-164">Field name</span></span>|<span data-ttu-id="1795b-165">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1795b-165">Data type</span></span>|<span data-ttu-id="1795b-166">설명</span><span class="sxs-lookup"><span data-stu-id="1795b-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="1795b-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="1795b-167">AppDomainID</span></span>|<span data-ttu-id="1795b-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1795b-168">win:UInt64</span></span>|<span data-ttu-id="1795b-169">리소스 사용량이 보고되는 애플리케이션 도메인의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="1795b-170">Allocated</span><span class="sxs-lookup"><span data-stu-id="1795b-170">Allocated</span></span>|<span data-ttu-id="1795b-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1795b-171">win:UInt64</span></span>|<span data-ttu-id="1795b-172">애플리케이션 도메인이 만들어진 후 이 애플리케이션 도메인에서 할당된 총 바이트 수입니다(해제된 메모리 양을 빼지 않음).</span><span class="sxs-lookup"><span data-stu-id="1795b-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="1795b-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1795b-173">ClrInstanceID</span></span>|<span data-ttu-id="1795b-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1795b-174">win:UInt16</span></span>|<span data-ttu-id="1795b-175">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="1795b-176">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1795b-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="1795b-177">AppDomainMemSurvived 이벤트</span><span class="sxs-lookup"><span data-stu-id="1795b-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="1795b-178">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1795b-179">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="1795b-179">Keyword for raising the event</span></span>|<span data-ttu-id="1795b-180">수준</span><span class="sxs-lookup"><span data-stu-id="1795b-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1795b-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="1795b-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="1795b-182">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="1795b-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="1795b-183">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1795b-184">이벤트</span><span class="sxs-lookup"><span data-stu-id="1795b-184">Event</span></span>|<span data-ttu-id="1795b-185">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="1795b-185">Event ID</span></span>|<span data-ttu-id="1795b-186">발생 시기</span><span class="sxs-lookup"><span data-stu-id="1795b-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="1795b-187">84</span><span class="sxs-lookup"><span data-stu-id="1795b-187">84</span></span>|<span data-ttu-id="1795b-188">각 가비지 수집이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="1795b-189">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="1795b-190">필드 이름</span><span class="sxs-lookup"><span data-stu-id="1795b-190">Field name</span></span>|<span data-ttu-id="1795b-191">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1795b-191">Data type</span></span>|<span data-ttu-id="1795b-192">설명</span><span class="sxs-lookup"><span data-stu-id="1795b-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="1795b-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="1795b-193">AppDomainID</span></span>|<span data-ttu-id="1795b-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1795b-194">win:UInt64</span></span>|<span data-ttu-id="1795b-195">리소스 사용량이 보고되는 도메인의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="1795b-196">Survived</span><span class="sxs-lookup"><span data-stu-id="1795b-196">Survived</span></span>|<span data-ttu-id="1795b-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1795b-197">win:UInt64</span></span>|<span data-ttu-id="1795b-198">마지막 수집 후에도 유지되고 이 애플리케이션 도메인에 저장되는 것으로 알려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="1795b-199">이 수는 전체 수집 후에 정확하고 완전하지만 임시 수집 후에는 불완전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="1795b-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="1795b-200">ProcessSurvived</span></span>|<span data-ttu-id="1795b-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1795b-201">win:UInt64</span></span>|<span data-ttu-id="1795b-202">마지막 수집에서 유지된 총 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="1795b-203">전체 수집 후에 이 수는 관리되는 힙에 실시간으로 저장되는 바이트 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="1795b-204">임시 수집 후에 이 수는 임시 생성에 실시간으로 저장되는 바이트 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="1795b-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1795b-205">ClrInstanceID</span></span>|<span data-ttu-id="1795b-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1795b-206">win:UInt16</span></span>|<span data-ttu-id="1795b-207">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="1795b-208">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1795b-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="1795b-209">ThreadAppDomainEnter 이벤트</span><span class="sxs-lookup"><span data-stu-id="1795b-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="1795b-210">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1795b-211">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="1795b-211">Keyword for raising the event</span></span>|<span data-ttu-id="1795b-212">수준</span><span class="sxs-lookup"><span data-stu-id="1795b-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1795b-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="1795b-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="1795b-214">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="1795b-214">Informational(4)</span></span>|  
|<span data-ttu-id="1795b-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="1795b-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="1795b-216">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="1795b-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="1795b-217">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1795b-218">이벤트</span><span class="sxs-lookup"><span data-stu-id="1795b-218">Event</span></span>|<span data-ttu-id="1795b-219">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="1795b-219">Event ID</span></span>|<span data-ttu-id="1795b-220">발생 시기</span><span class="sxs-lookup"><span data-stu-id="1795b-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="1795b-221">87</span><span class="sxs-lookup"><span data-stu-id="1795b-221">87</span></span>|<span data-ttu-id="1795b-222">스레드가 애플리케이션 도메인에 들어갑니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="1795b-223">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="1795b-224">필드 이름</span><span class="sxs-lookup"><span data-stu-id="1795b-224">Field name</span></span>|<span data-ttu-id="1795b-225">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1795b-225">Data type</span></span>|<span data-ttu-id="1795b-226">설명</span><span class="sxs-lookup"><span data-stu-id="1795b-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="1795b-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="1795b-227">ThreadID</span></span>|<span data-ttu-id="1795b-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1795b-228">win:UInt64</span></span>|<span data-ttu-id="1795b-229">스레드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-229">The thread identifier.</span></span>|  
|<span data-ttu-id="1795b-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="1795b-230">AppDomainID</span></span>|<span data-ttu-id="1795b-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1795b-231">win:UInt64</span></span>|<span data-ttu-id="1795b-232">애플리케이션 도메인 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="1795b-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1795b-233">ClrInstanceID</span></span>|<span data-ttu-id="1795b-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1795b-234">win:UInt16</span></span>|<span data-ttu-id="1795b-235">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="1795b-236">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1795b-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="1795b-237">ThreadTerminated 이벤트</span><span class="sxs-lookup"><span data-stu-id="1795b-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="1795b-238">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1795b-239">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="1795b-239">Keyword for raising the event</span></span>|<span data-ttu-id="1795b-240">수준</span><span class="sxs-lookup"><span data-stu-id="1795b-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1795b-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="1795b-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="1795b-242">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="1795b-242">Informational(4)</span></span>|  
|<span data-ttu-id="1795b-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="1795b-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="1795b-244">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="1795b-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="1795b-245">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1795b-246">이벤트</span><span class="sxs-lookup"><span data-stu-id="1795b-246">Event</span></span>|<span data-ttu-id="1795b-247">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="1795b-247">Event ID</span></span>|<span data-ttu-id="1795b-248">발생 시기</span><span class="sxs-lookup"><span data-stu-id="1795b-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="1795b-249">86</span><span class="sxs-lookup"><span data-stu-id="1795b-249">86</span></span>|<span data-ttu-id="1795b-250">스레드가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="1795b-251">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="1795b-252">필드 이름</span><span class="sxs-lookup"><span data-stu-id="1795b-252">Field name</span></span>|<span data-ttu-id="1795b-253">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1795b-253">Data type</span></span>|<span data-ttu-id="1795b-254">설명</span><span class="sxs-lookup"><span data-stu-id="1795b-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="1795b-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="1795b-255">ThreadID</span></span>|<span data-ttu-id="1795b-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1795b-256">win:UInt64</span></span>|<span data-ttu-id="1795b-257">스레드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-257">The thread identifier.</span></span>|  
|<span data-ttu-id="1795b-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="1795b-258">AppDomainID</span></span>|<span data-ttu-id="1795b-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1795b-259">win:UInt64</span></span>|<span data-ttu-id="1795b-260">애플리케이션 도메인 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="1795b-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1795b-261">ClrInstanceID</span></span>|<span data-ttu-id="1795b-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1795b-262">win:UInt16</span></span>|<span data-ttu-id="1795b-263">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1795b-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1795b-264">참고자료</span><span class="sxs-lookup"><span data-stu-id="1795b-264">See also</span></span>

- [<span data-ttu-id="1795b-265">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="1795b-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
