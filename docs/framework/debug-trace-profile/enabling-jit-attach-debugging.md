---
title: JIT 연결 디버깅 설정
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b92592500f0babf29891710cedf1228b0ddcb0e4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43873278"
---
# <a name="enabling-jit-attach-debugging"></a><span data-ttu-id="5eb8f-102">JIT 연결 디버깅 설정</span><span class="sxs-lookup"><span data-stu-id="5eb8f-102">Enabling JIT-Attach Debugging</span></span>
<span data-ttu-id="5eb8f-103">오류가 발생한 경우 JIT 연결 디버깅은 디버거를 프로세스에 연결하는 방법을 설명하는 데 사용되는 구문이고, 오류가 발생하지 않은 경우 특정 메서드 또는 함수에 의해 트리거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eb8f-103">JIT-attach debugging is the phrase used to describe attaching a debugger to a process when you encounter errors, or it can be triggered by specific methods or functions.</span></span>  
  
 <span data-ttu-id="5eb8f-104">JIT 연결 디버깅은 다음 오류 조건에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5eb8f-104">JIT-attach debugging is used under the following fault conditions:</span></span>  
  
-   <span data-ttu-id="5eb8f-105">처리되지 않은 예외(네이티브 및 관리 코드에서 둘 다).</span><span class="sxs-lookup"><span data-stu-id="5eb8f-105">Unhandled exceptions (in both native and managed code).</span></span>  
  
-   <span data-ttu-id="5eb8f-106"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> 메서드 또는 [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) 함수(Windows 7 제품군).</span><span class="sxs-lookup"><span data-stu-id="5eb8f-106"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> method or [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) function (Windows 7 family).</span></span>  
  
-   <span data-ttu-id="5eb8f-107">런타임 오류.</span><span class="sxs-lookup"><span data-stu-id="5eb8f-107">Runtime fatal errors.</span></span>  
  
 <span data-ttu-id="5eb8f-108">JIT 연결 디버깅은 다음 메서드 및 함수에 대한 호출에 의해서도 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="5eb8f-108">JIT-attach debugging is also triggered by calls to the following methods and functions:</span></span>  
  
-   <span data-ttu-id="5eb8f-109"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5eb8f-109"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="5eb8f-110"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5eb8f-110"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="5eb8f-111">[DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) 함수(Win32).</span><span class="sxs-lookup"><span data-stu-id="5eb8f-111">[DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) function (Win32).</span></span>  
  
 <span data-ttu-id="5eb8f-112">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 이전에 .NET Framework에서는 네이티브 및 관리되는 디버거의 동작을 제어하기 위한 개별 레지스트리 키를 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="5eb8f-112">Before the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the .NET Framework provided separate registry keys to control the behavior of native and managed debuggers.</span></span> <span data-ttu-id="5eb8f-113">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]부터 컨트롤은 단일 레지스트리 키 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug 아래에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="5eb8f-113">Starting with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], control is consolidated under a single registry key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span></span> <span data-ttu-id="5eb8f-114">해당 키에 대해 설정할 수 있는 값에 따라 디버거 호출 여부가 결정되고 디버거가 호출되는 경우 사용자 조작이 필요한 대화 상자와 함께 호출되는지 여부가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5eb8f-114">The values you can set for that key determine whether a debugger is invoked, and, if so, whether it is invoked with a dialog box that requires user interaction.</span></span> <span data-ttu-id="5eb8f-115">이 레지스트리 키 설정에 대 한 자세한 내용은 [자동 디버깅 구성](https://go.microsoft.com/fwlink/?LinkId=181767)합니다.</span><span class="sxs-lookup"><span data-stu-id="5eb8f-115">For information about setting this registry key, see [Configuring Automatic Debugging](https://go.microsoft.com/fwlink/?LinkId=181767).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eb8f-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5eb8f-116">See Also</span></span>  
 [<span data-ttu-id="5eb8f-117">디버깅, 추적 및 프로파일링</span><span class="sxs-lookup"><span data-stu-id="5eb8f-117">Debugging, Tracing, and Profiling</span></span>](../../../docs/framework/debug-trace-profile/index.md)  
 [<span data-ttu-id="5eb8f-118">쉽게 디버깅할 수 있도록 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="5eb8f-118">Making an Image Easier to Debug</span></span>](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)  
 [<span data-ttu-id="5eb8f-119">프로파일링 설정</span><span class="sxs-lookup"><span data-stu-id="5eb8f-119">Enabling Profiling</span></span>](https://msdn.microsoft.com/library/3b669676-f0e0-4ebf-8674-68986dd2020d)
