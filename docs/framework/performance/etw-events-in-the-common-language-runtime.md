---
title: 공용 언어 런타임의 ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d059a5d4df402b309f628bf3e9393114c4cdeec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191395"
---
# <a name="etw-events-in-the-common-language-runtime"></a><span data-ttu-id="b7a5f-102">공용 언어 런타임의 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="b7a5f-102">ETW Events in the Common Language Runtime</span></span>
<span data-ttu-id="b7a5f-103">CLR(공용 언어 런타임)은 다양한 디버깅 및 프로파일링 이벤트를 통해 ETW(Windows용 이벤트 추적) 진단 정보에 대한 유용한 이벤트 추적을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a5f-103">The common language runtime (CLR) provides useful event tracing for Windows (ETW) diagnostic information through a large variety of debugging and profiling events.</span></span> <span data-ttu-id="b7a5f-104">CLR ETW 이벤트는 Windows ETW 추적 시스템을 사용하여 공용 언어 런타임에서 제공되는 기존 프로파일링 및 디버깅 지원을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a5f-104">CLR ETW events leverage the Windows ETW tracing system to augment the existing profiling and debugging support provided by the common language runtime.</span></span>  
  
 <span data-ttu-id="b7a5f-105">ETW에 대한 자세한 내용은 MSDN의 [Improve Debugging and Performance Tuning with ETW](https://go.microsoft.com/fwlink/?LinkID=161142)(ETW를 사용한 디버깅 및 성능 조정 개선)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7a5f-105">More information about ETW is available in the article [Improve Debugging and Performance Tuning with ETW](https://go.microsoft.com/fwlink/?LinkID=161142) on MSDN.</span></span> <span data-ttu-id="b7a5f-106">Xperf에 대한 자세한 내용은 NTDebugging 블로그의 [Windows Performance Toolkit - Xperf](https://go.microsoft.com/fwlink/?LinkID=161144)(Windows 성능 도구 키트 - Xperf) 항목에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a5f-106">Information about Xperf can be found in the entry [Windows Performance Toolkit - Xperf](https://go.microsoft.com/fwlink/?LinkID=161144) in the NTDebugging blog.</span></span>  
  
 <span data-ttu-id="b7a5f-107">이벤트 항목에 설명된 모든 이벤트를 지원하려면 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a5f-107">The [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] or later is required for all the events described in the event topics.</span></span> <span data-ttu-id="b7a5f-108">Windows Vista 운영 체제가 최소 지원 클라이언트이고, Windows Server 2008이 최소 지원 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a5f-108">The Windows Vista operating system is the minimum supported client, and Windows Server 2008 is the minimum supported server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b7a5f-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="b7a5f-109">In This Section</span></span>  
 [<span data-ttu-id="b7a5f-110">.NET Framework 로깅 제어</span><span class="sxs-lookup"><span data-stu-id="b7a5f-110">Controlling .NET Framework Logging</span></span>](../../../docs/framework/performance/controlling-logging.md)  
 <span data-ttu-id="b7a5f-111">ETW 이벤트를 캡처하고 보기 위한 도구와 명령을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a5f-111">Describes the tools and commands for capturing and viewing ETW events.</span></span>  
  
 [<span data-ttu-id="b7a5f-112">CLR ETW 공급자</span><span class="sxs-lookup"><span data-stu-id="b7a5f-112">CLR ETW Providers</span></span>](../../../docs/framework/performance/clr-etw-providers.md)  
 <span data-ttu-id="b7a5f-113">런타임 및 런다운 공급자와 ETW 데이터 수집에 이러한 공급자를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a5f-113">Provides information about the runtime and rundown providers, and how you can use them for ETW data collection.</span></span>  
  
 [<span data-ttu-id="b7a5f-114">CLR ETW 키워드 및 수준</span><span class="sxs-lookup"><span data-stu-id="b7a5f-114">CLR ETW Keywords and Levels</span></span>](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)  
 <span data-ttu-id="b7a5f-115">범주별 이벤트 필터링을 가능하게 하는 런타임 및 런다운 공급자에 대한 키워드를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a5f-115">Describes the keywords for the Runtime and Rundown providers that enable the filtering of events by category.</span></span>  
  
 [<span data-ttu-id="b7a5f-116">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="b7a5f-116">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)  
 <span data-ttu-id="b7a5f-117">CLR ETW 이벤트, 해당 키워드 및 이벤트 데이터를 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a5f-117">Provides detailed information about CLR ETW events, their keywords, levels, and event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7a5f-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="b7a5f-118">See also</span></span>

- [<span data-ttu-id="b7a5f-119">ETW Events in the .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b7a5f-119">ETW Events in the .NET Framework</span></span>](../../../docs/framework/performance/etw-events.md)
