---
title: dirtyCastAndCallOnInterface MDA
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), early bound calls AutoDispatch
- dispatch-only mode
- dirtyCastAndCallOnInterface
- early-bound managed classes
- early bound calls on AutoDispatch
- MDAs (managed debugging assistants), early bound calls AutoDispatch
- EarlyBoundCallOnAutorDispatchClassInteface MDA
ms.assetid: aa388ed3-7e3d-48ea-a0b5-c47ae19cec38
ms.openlocfilehash: 6e4f0074958e8a6a8ca322968e9c29e89481c0c8
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216506"
---
# <a name="dirtycastandcalloninterface-mda"></a><span data-ttu-id="cf249-102">dirtyCastAndCallOnInterface MDA</span><span class="sxs-lookup"><span data-stu-id="cf249-102">dirtyCastAndCallOnInterface MDA</span></span>
<span data-ttu-id="cf249-103">`dirtyCastAndCallOnInterface` MDA(관리 디버깅 도우미)는 런타임에만 바인딩됨으로 표시된 클래스 인터페이스에 대해 vtable을 통해 초기에 바인딩된 호출을 시도할 때 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf249-103">The `dirtyCastAndCallOnInterface` managed debugging assistant (MDA) is activated when an early-bound call through a vtable is attempted on a class interface that has been marked late-bound only.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="cf249-104">증상</span><span class="sxs-lookup"><span data-stu-id="cf249-104">Symptoms</span></span>  
 <span data-ttu-id="cf249-105">COM을 통해 초기에 바인딩된 호출을 CLR에 배치하는 경우 애플리케이션에서 액세스 위반이나 예기치 않은 동작이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="cf249-105">An application throws an access violation or has unexpected behavior when placing an early-bound call via COM into the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="cf249-106">원인</span><span class="sxs-lookup"><span data-stu-id="cf249-106">Cause</span></span>  
 <span data-ttu-id="cf249-107">코드에서 런타임에만 바인딩되는 클래스 인터페이스에 대해 vtable을 통해 초기에 바인딩된 호출을 시도 중입니다.</span><span class="sxs-lookup"><span data-stu-id="cf249-107">Code is attempting an early-bound call through a vtable via a class interface that is late-bound only.</span></span> <span data-ttu-id="cf249-108">기본적으로 클래스 인터페이스는 런타임에만 바인딩됨으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf249-108">Note that by default class interfaces are identified as being late-bound only.</span></span> <span data-ttu-id="cf249-109"><xref:System.Runtime.InteropServices.ClassInterfaceAttribute> 특성에 <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> 값(`[ClassInterface(ClassInterfaceType.AutoDispatch)]`)을 사용하여 런타임에 바인딩됨으로 식별할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf249-109">They can also be identified as late-bound with the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute with an <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> value (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`).</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="cf249-110">해결 방법</span><span class="sxs-lookup"><span data-stu-id="cf249-110">Resolution</span></span>  
 <span data-ttu-id="cf249-111">권장되는 해결 방법은 COM에서 사용할 명시적 인터페이스를 정의하고 자동으로 생성된 클래스 인터페이스 대신 이 인터페이스를 통해 COM 클라이언트가 호출하도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cf249-111">The recommended resolution is to define an explicit interface for use by COM and have the COM clients call through this interface instead of through the automatically generated class interface.</span></span> <span data-ttu-id="cf249-112">또는 `IDispatch`를 통해 COM 호출을 런타임에 바인딩된 호출로 변형할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf249-112">Alternatively, the call from COM can be transformed into a late-bound call via `IDispatch`.</span></span>  
  
 <span data-ttu-id="cf249-113">끝으로, 클래스를 <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual>(`[ClassInterface(ClassInterfaceType.AutoDual)]`)로 식별하여 COM에서 초기에 바인딩된 호출을 배치할 수 있도록 허용할 수 있습니다. 그러나 <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual>에 설명된 버전 관리 제한 사항 때문에 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>은 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cf249-113">Finally, it is possible to identify the class as <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) to allow early bound calls to be placed from COM; however, using <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> is strongly discouraged because of the versioning limitations described in <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="cf249-114">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="cf249-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="cf249-115">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf249-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="cf249-116">런타임에 바인딩된 인터페이스에 대한 초기에 바인딩된 호출 데이터만 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="cf249-116">It only reports data about early-bound calls on late-bound interfaces.</span></span>  
  
## <a name="output"></a><span data-ttu-id="cf249-117">출력</span><span class="sxs-lookup"><span data-stu-id="cf249-117">Output</span></span>  
 <span data-ttu-id="cf249-118">초기에 바인딩됨으로 액세스되는 필드 이름 또는 메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cf249-118">The name of the method or name of the field being accessed early-bound.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="cf249-119">구성</span><span class="sxs-lookup"><span data-stu-id="cf249-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dirtyCastAndCallOnInterface />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf249-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf249-120">See also</span></span>

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>
- [<span data-ttu-id="cf249-121">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="cf249-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
