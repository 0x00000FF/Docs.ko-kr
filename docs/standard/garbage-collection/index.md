---
title: 가비지 컬렉션
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- memory, garbage collection
- garbage collection, automatic memory management
- GC [.NET Framework]
- memory, allocating
- common language runtime, garbage collection
- garbage collector
- cleanup operations
- garbage collection
- memory, releasing
- common language runtime, automatic memory management
- automatic memory management
- runtime, automatic memory management
- runtime, garbage collection
- garbage collection, about
ms.assetid: 22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f61b63f78ea3c6131d4d1ab4e421be25149035b
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45964126"
---
# <a name="garbage-collection"></a><span data-ttu-id="e785c-102">가비지 컬렉션</span><span class="sxs-lookup"><span data-stu-id="e785c-102">Garbage Collection</span></span>
<span data-ttu-id="e785c-103">.NET의 가비지 수집기는 응용 프로그램의 메모리 할당 및 해제를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="e785c-103">.NET's garbage collector manages the allocation and release of memory for your application.</span></span> <span data-ttu-id="e785c-104">새 개체를 만들 때마다 공용 언어 런타임이 관리되는 힙에서 개체에 대해 메모리를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e785c-104">Each time you create a new object, the common language runtime allocates memory for the object from the managed heap.</span></span> <span data-ttu-id="e785c-105">관리되는 힙에서 주소 공간을 사용할 수 있다면 런타임은 계속해서 새 개체에 공간을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e785c-105">As long as address space is available in the managed heap, the runtime continues to allocate space for new objects.</span></span> <span data-ttu-id="e785c-106">그러나 메모리는 무한하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e785c-106">However, memory is not infinite.</span></span> <span data-ttu-id="e785c-107">결국 가비지 수집기는 메모리를 확보하기 위해 수집을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e785c-107">Eventually the garbage collector must perform a collection in order to free some memory.</span></span> <span data-ttu-id="e785c-108">가비지 수집기의 최적화 엔진은 수행 중인 할당에 따라 수집을 수행하기에 가장 적합한 시간을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e785c-108">The garbage collector's optimizing engine determines the best time to perform a collection, based upon the allocations being made.</span></span> <span data-ttu-id="e785c-109">가비지 수집기는 수집을 수행할 때 응용 프로그램에서 더 이상 사용하고 있지 않은 관리되는 힙에 있는 개체를 확인하고 해당 메모리를 회수하는 데 필요한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e785c-109">When the garbage collector performs a collection, it checks for objects in the managed heap that are no longer being used by the application and performs the necessary operations to reclaim their memory.</span></span>  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="e785c-110">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e785c-110">Related Topics</span></span>  
  
|<span data-ttu-id="e785c-111">제목</span><span class="sxs-lookup"><span data-stu-id="e785c-111">Title</span></span>|<span data-ttu-id="e785c-112">설명</span><span class="sxs-lookup"><span data-stu-id="e785c-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e785c-113">가비지 수집 기본 사항</span><span class="sxs-lookup"><span data-stu-id="e785c-113">Fundamentals of Garbage Collection</span></span>](../../../docs/standard/garbage-collection/fundamentals.md)|<span data-ttu-id="e785c-114">가비지 수집이 작동하는 방법, 관리되는 힙에 개체를 할당하는 방법 및 기타 핵심 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e785c-114">Describes how garbage collection works, how objects are allocated on the managed heap, and other core concepts.</span></span>|  
|[<span data-ttu-id="e785c-115">가비지 수집 및 성능</span><span class="sxs-lookup"><span data-stu-id="e785c-115">Garbage Collection and Performance</span></span>](../../../docs/standard/garbage-collection/performance.md)|<span data-ttu-id="e785c-116">가비지 수집 및 성능 문제를 진단하는 데 사용할 수 있는 성능 검사에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e785c-116">Describes the performance checks you can use to diagnose garbage collection and performance issues.</span></span>|  
|[<span data-ttu-id="e785c-117">인덱싱된 컬렉션</span><span class="sxs-lookup"><span data-stu-id="e785c-117">Induced Collections</span></span>](../../../docs/standard/garbage-collection/induced.md)|<span data-ttu-id="e785c-118">가비지 수집을 발생시키는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e785c-118">Describes how to make a garbage collection occur.</span></span>|  
|[<span data-ttu-id="e785c-119">대기 시간 모드</span><span class="sxs-lookup"><span data-stu-id="e785c-119">Latency Modes</span></span>](../../../docs/standard/garbage-collection/latency.md)|<span data-ttu-id="e785c-120">가비지 수집의 실행 시기를 결정하는 모드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e785c-120">Describes the modes that determine the intrusiveness of garbage collection.</span></span>|  
|[<span data-ttu-id="e785c-121">공유 웹 호스팅을 위한 최적화</span><span class="sxs-lookup"><span data-stu-id="e785c-121">Optimization for Shared Web Hosting</span></span>](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|<span data-ttu-id="e785c-122">여러 개의 작은 웹 사이트에서 공유하는 서버에서 가비지 수집을 최적화하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e785c-122">Describes how to optimize garbage collection on servers shared by several small Web sites.</span></span>|  
|[<span data-ttu-id="e785c-123">가비지 수집 알림</span><span class="sxs-lookup"><span data-stu-id="e785c-123">Garbage Collection Notifications</span></span>](../../../docs/standard/garbage-collection/notifications.md)|<span data-ttu-id="e785c-124">전체 가비지 수집이 끝나갈 때와 완료될 때를 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e785c-124">Describes how to determine when a full garbage collection is approaching and when it has completed.</span></span>|  
|[<span data-ttu-id="e785c-125">응용 프로그램 도메인 리소스 모니터링</span><span class="sxs-lookup"><span data-stu-id="e785c-125">Application Domain Resource Monitoring</span></span>](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|<span data-ttu-id="e785c-126">응용 프로그램 도메인별로 CPU 및 메모리 사용량을 모니터링하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e785c-126">Describes how to monitor CPU and memory usage by an application domain.</span></span>|  
|[<span data-ttu-id="e785c-127">약한 참조</span><span class="sxs-lookup"><span data-stu-id="e785c-127">Weak References</span></span>](../../../docs/standard/garbage-collection/weak-references.md)|<span data-ttu-id="e785c-128">응용 프로그램에서 개체에 계속 액세스하는 동안 가비지 수집기에서 해당 개체를 수집할 수 있도록 하는 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e785c-128">Describes features that permit the garbage collector to collect an object while still allowing the application to access that object.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="e785c-129">참조</span><span class="sxs-lookup"><span data-stu-id="e785c-129">Reference</span></span>  
 <xref:System.GC?displayProperty=nameWithType>  
  
 <xref:System.GCCollectionMode?displayProperty=nameWithType>  
  
 <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
  
 <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="e785c-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e785c-130">See also</span></span>

- [<span data-ttu-id="e785c-131">관리되지 않는 리소스 정리</span><span class="sxs-lookup"><span data-stu-id="e785c-131">Cleaning Up Unmanaged Resources</span></span>](../../../docs/standard/garbage-collection/unmanaged.md)
