---
title: marshaling MDA
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, run-time errors
- marshaling MDA
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: 5433b1f8-b0e5-40c9-a49a-0e5bd213363d
ms.openlocfilehash: f7bb630d3a1e832cf6bf083ce4cf603034248ceb
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217329"
---
# <a name="marshaling-mda"></a><span data-ttu-id="acbdd-102">marshaling MDA</span><span class="sxs-lookup"><span data-stu-id="acbdd-102">marshaling MDA</span></span>
<span data-ttu-id="acbdd-103">`marshaling` MDA(관리 디버깅 도우미)는 CLR이 메서드 매개 변수 또는 구조체 필드에 대한 마샬링 정보를 설정할 때 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbdd-103">The `marshaling` managed debugging assistant (MDA) is activated when the CLR sets up marshaling information for a method parameter or a field of a structure.</span></span> <span data-ttu-id="acbdd-104">이 MDA는 JIT 컴파일된 어셈블리에 대해 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acbdd-104">This MDA does not work for JIT-compiled assemblies.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="acbdd-105">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="acbdd-105">Effect on the Runtime</span></span>  
 <span data-ttu-id="acbdd-106">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acbdd-106">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="acbdd-107">출력</span><span class="sxs-lookup"><span data-stu-id="acbdd-107">Output</span></span>  
 <span data-ttu-id="acbdd-108">MDA에서 관리되는 컨텍스트 및 관리되지 않는 컨텍스트의 매개 변수 또는 필드 형식과 해당 형식을 포함하는 구조체 또는 메서드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="acbdd-108">The MDA displays the type of the parameter or field in the managed and unmanaged contexts, and the structure or method containing the type.</span></span>  <span data-ttu-id="acbdd-109">다음은 필드에 대한 출력 예입니다.</span><span class="sxs-lookup"><span data-stu-id="acbdd-109">The following is an example of the output for a field:</span></span>  
  
```output
Marshaling from 'Char' to 'ANSI char'  
name="assembly!Namespace.Class::myChar  
```  
  
## <a name="configuration"></a><span data-ttu-id="acbdd-110">구성</span><span class="sxs-lookup"><span data-stu-id="acbdd-110">Configuration</span></span>  
 <span data-ttu-id="acbdd-111">MDA 구성을 통해 관련된 필드 또는 메서드 이름에 따라 보고된 마샬링 정보를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acbdd-111">The MDA configuration allows you to filter the reported marshaling information based on the involved field or method names.</span></span>  <span data-ttu-id="acbdd-112">다음 예제에서는 `methodFilter`, `fieldFilter` 및 `match` 요소를 사용하여 필터를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="acbdd-112">The following example shows the use of the `methodFilter`, `fieldFilter`, and `match` elements to specify filters.</span></span>  <span data-ttu-id="acbdd-113">`name` 특성을 별표 (\*)로 설정 하면 모든 항목과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="acbdd-113">Setting the `name` attribute to an asterisk (\*) will match everything.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshaling>  
      <methodFilter>  
        <match name="Method1"/>  
        <match name="Method2"/>  
      </methodFilter>  
      <fieldFilter>  
        <match name="Field1"/>  
        <match name="Field2"/>  
       </fieldFilter>  
    </marshaling>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="acbdd-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="acbdd-114">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="acbdd-115">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="acbdd-115">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="acbdd-116">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="acbdd-116">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
