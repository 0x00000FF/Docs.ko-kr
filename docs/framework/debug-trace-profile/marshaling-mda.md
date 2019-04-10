---
title: marshaling MDA
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, run-time errors
- marshaling MDA
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: 5433b1f8-b0e5-40c9-a49a-0e5bd213363d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 463c8e42e76a61eb0820c1af72c20d004161ad25
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184472"
---
# <a name="marshaling-mda"></a><span data-ttu-id="cfce8-102">marshaling MDA</span><span class="sxs-lookup"><span data-stu-id="cfce8-102">marshaling MDA</span></span>
<span data-ttu-id="cfce8-103">`marshaling` MDA(관리 디버깅 도우미)는 CLR이 메서드 매개 변수 또는 구조체 필드에 대한 마샬링 정보를 설정할 때 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfce8-103">The `marshaling` managed debugging assistant (MDA) is activated when the CLR sets up marshaling information for a method parameter or a field of a structure.</span></span> <span data-ttu-id="cfce8-104">이 MDA는 JIT 컴파일된 어셈블리에 대해 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfce8-104">This MDA does not work for JIT-compiled assemblies.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="cfce8-105">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="cfce8-105">Effect on the Runtime</span></span>  
 <span data-ttu-id="cfce8-106">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfce8-106">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="cfce8-107">출력</span><span class="sxs-lookup"><span data-stu-id="cfce8-107">Output</span></span>  
 <span data-ttu-id="cfce8-108">MDA에서 관리되는 컨텍스트 및 관리되지 않는 컨텍스트의 매개 변수 또는 필드 형식과 해당 형식을 포함하는 구조체 또는 메서드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cfce8-108">The MDA displays the type of the parameter or field in the managed and unmanaged contexts, and the structure or method containing the type.</span></span>  <span data-ttu-id="cfce8-109">다음은 필드에 대한 출력 예입니다.</span><span class="sxs-lookup"><span data-stu-id="cfce8-109">The following is an example of the output for a field:</span></span>  
  
```  
Marshaling from 'Char' to 'ANSI char'  
name="assembly!Namespace.Class::myChar  
```  
  
## <a name="configuration"></a><span data-ttu-id="cfce8-110">구성</span><span class="sxs-lookup"><span data-stu-id="cfce8-110">Configuration</span></span>  
 <span data-ttu-id="cfce8-111">MDA 구성을 통해 관련된 필드 또는 메서드 이름에 따라 보고된 마샬링 정보를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfce8-111">The MDA configuration allows you to filter the reported marshaling information based on the involved field or method names.</span></span>  <span data-ttu-id="cfce8-112">다음 예제에서는 `methodFilter`, `fieldFilter` 및 `match` 요소를 사용하여 필터를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cfce8-112">The following example shows the use of the `methodFilter`, `fieldFilter`, and `match` elements to specify filters.</span></span>  <span data-ttu-id="cfce8-113">`name` 특성을 별표(\*)로 설정하면 모든 항목과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="cfce8-113">Setting the `name` attribute to an asterisk (\*) will match everything.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cfce8-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="cfce8-114">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="cfce8-115">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="cfce8-115">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="cfce8-116">Interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="cfce8-116">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
