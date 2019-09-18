---
title: exceptionSwallowedOnCallFromCom MDA
ms.date: 03/30/2017
helpviewer_keywords:
- messages, informational
- informational messages
- managed debugging assistants (MDAs), exceptions
- exception handling, managed debugging assistants
- MDAs (managed debugging assistants), exceptions
- ExceptionSwallowedOnCallFromCOM MDA
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3a49bdce78c1445cd25de8755ded0f27a4902937
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052813"
---
# <a name="exceptionswallowedoncallfromcom-mda"></a><span data-ttu-id="63796-102">exceptionSwallowedOnCallFromCom MDA</span><span class="sxs-lookup"><span data-stu-id="63796-102">exceptionSwallowedOnCallFromCom MDA</span></span>
<span data-ttu-id="63796-103">`exceptionSwallowedOnCallFromCOM` MDA(관리 디버깅 도우미)는 관리되지 않는 HRESULT 반환 형식이 없는 메서드를 통해 COM에서 호출된 CLR(공용 언어 런타임) 코드에서 예외가 throw되면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="63796-103">The `exceptionSwallowedOnCallFromCOM` managed debugging assistant (MDA) is activated when an exception is thrown from common language runtime (CLR) code called from COM via a method that does not have an unmanaged HRESULT return type.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="63796-104">증상</span><span class="sxs-lookup"><span data-stu-id="63796-104">Symptoms</span></span>  
 <span data-ttu-id="63796-105">COM에서 관리되는 구성 요소에 대한 호출이 FALSE 또는 0 값으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="63796-105">A call to a managed component from COM returns with a value of FALSE or 0.</span></span> <span data-ttu-id="63796-106">또는 메서드의 반환 형식이 void인 경우 메서드 실행 중에 예외가 throw되었음을 나타내는 표시가 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63796-106">Alternatively, if the method has a void return type, there may be no indication that an exception was thrown during the execution of the method.</span></span> <span data-ttu-id="63796-107">이 경우 예외가 자동으로 catch되고 실행이 COM 호출자에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="63796-107">In this case, the exception will be silently caught and execution will return to the COM caller.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="63796-108">원인</span><span class="sxs-lookup"><span data-stu-id="63796-108">Cause</span></span>  
 <span data-ttu-id="63796-109">예외가 throw되었지만 해당 예외를 보고할 유효한 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63796-109">An exception was thrown, but there is no valid way to report it.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="63796-110">해결 방법</span><span class="sxs-lookup"><span data-stu-id="63796-110">Resolution</span></span>  
 <span data-ttu-id="63796-111">정보 제공의 목적이며, 반드시 버그를 의미하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="63796-111">Informational only, not necessarily indicative of a bug.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="63796-112">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="63796-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="63796-113">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63796-113">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="63796-114">자동으로 catch된 예외에 대한 데이터를 보고할 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="63796-114">It only reports data about silently caught exceptions.</span></span>  
  
## <a name="output"></a><span data-ttu-id="63796-115">출력</span><span class="sxs-lookup"><span data-stu-id="63796-115">Output</span></span>  
 <span data-ttu-id="63796-116">메서드 이름, 형식 이름 및 예외 메시지를 포함하는 정보 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="63796-116">Informational message containing the method name, type name, and exception message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="63796-117">Configuration</span><span class="sxs-lookup"><span data-stu-id="63796-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="63796-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="63796-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="63796-119">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="63796-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="63796-120">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="63796-120">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
