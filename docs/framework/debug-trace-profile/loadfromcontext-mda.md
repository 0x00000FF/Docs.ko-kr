---
title: loadFromContext MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), LoadFrom context
- managed debugging assistants (MDAs), LoadFrom context
- LoadFrom context
- LoadFromContext MDA
ms.assetid: a9b14db1-d3a9-4150-a767-dcf3aea0071a
ms.openlocfilehash: 28ef6e12c82cf5ca56962756b9ea964d0ae9baaa
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216167"
---
# <a name="loadfromcontext-mda"></a><span data-ttu-id="a3384-102">loadFromContext MDA</span><span class="sxs-lookup"><span data-stu-id="a3384-102">loadFromContext MDA</span></span>
<span data-ttu-id="a3384-103">`loadFromContext` MDA(관리 디버깅 도우미)는 어셈블리가 `LoadFrom` 컨텍스트에 로드되면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-103">The `loadFromContext` managed debugging assistant (MDA) is activated if an assembly is loaded into the `LoadFrom` context.</span></span> <span data-ttu-id="a3384-104">이 상황은 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>을 호출하거나 비슷한 메서드를 호출한 결과 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-104">This situation can occur as a result of calling <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> or other similar methods.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a3384-105">증상</span><span class="sxs-lookup"><span data-stu-id="a3384-105">Symptoms</span></span>  
 <span data-ttu-id="a3384-106">일부 로더 메서드를 사용하면 어셈블리가 `LoadFrom` 컨텍스트에 로드될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-106">The use of some loader methods can result in assemblies being loaded in the `LoadFrom` context.</span></span> <span data-ttu-id="a3384-107">이 컨텍스트를 사용하면 예기치 않은 serialization, 캐스팅 및 종속성 확인 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-107">The use of this context can result in unexpected behavior for serialization, casting, and dependency resolution.</span></span> <span data-ttu-id="a3384-108">일반적으로 이러한 문제점을 방지하기 위해 어셈블리를 `Load` 컨텍스트에 로드하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-108">In general, it is recommended that assemblies be loaded into the `Load` context to avoid these problems.</span></span> <span data-ttu-id="a3384-109">이 MDA 없으면 어셈블리가 로드된 컨텍스트를 판별하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-109">It is difficult to determine which context an assembly has been loaded into without this MDA.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a3384-110">원인</span><span class="sxs-lookup"><span data-stu-id="a3384-110">Cause</span></span>  
 <span data-ttu-id="a3384-111">일반적으로 `LoadFrom` 컨텍스트 외부의 경로에서 로드된 경우(예: 전역 어셈블리 캐시 또는 `Load` 속성) 어셈블리가 <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType> 컨텍스트에 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-111">Generally, an assembly was loaded into the `LoadFrom` context if it was loaded from a path outside the `Load` context, such as the global assembly cache or the <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="a3384-112">해결 방법</span><span class="sxs-lookup"><span data-stu-id="a3384-112">Resolution</span></span>  
 <span data-ttu-id="a3384-113">더 이상 <xref:System.Reflection.Assembly.LoadFrom%2A>을 호출하지 않아도 되도록 애플리케이션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-113">Configure applications such that <xref:System.Reflection.Assembly.LoadFrom%2A> calls are no longer needed.</span></span> <span data-ttu-id="a3384-114">이 작업을 수행할 때 다음 기술을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-114">You can use the following techniques for doing so:</span></span>  
  
- <span data-ttu-id="a3384-115">전역 어셈블리 캐시에 어셈블리 설치</span><span class="sxs-lookup"><span data-stu-id="a3384-115">Install assemblies in the global assembly cache.</span></span>  
  
- <span data-ttu-id="a3384-116"><xref:System.AppDomainSetup.ApplicationBase%2A>의 <xref:System.AppDomain> 디렉터리에 어셈블리를 둡니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-116">Place assemblies in the <xref:System.AppDomainSetup.ApplicationBase%2A> directory for the <xref:System.AppDomain>.</span></span> <span data-ttu-id="a3384-117">기본 도메인의 경우 <xref:System.AppDomainSetup.ApplicationBase%2A> 디렉터리에 프로세스를 시작하는 실행 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-117">In the case of the default domain, the <xref:System.AppDomainSetup.ApplicationBase%2A> directory is the one that contains the executable file that started the process.</span></span> <span data-ttu-id="a3384-118">어셈블리를 쉽게 이동할 수 없는 경우 새로운 <xref:System.AppDomain>을 만들어야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-118">This might also require creating a new <xref:System.AppDomain> if it is not convenient to move the assembly.</span></span>  
  
- <span data-ttu-id="a3384-119">종속 어셈블리가 실행 파일과 관련된 하위 디렉터리에 있는 경우 보조 애플리케이션 도메인 또는 애플리케이션 구성(.config) 파일에 검색 경로를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-119">Add a probing path to your application configuration (.config) file or to secondary  application domains if dependent assemblies are in child directories relative to the executable.</span></span>  
  
 <span data-ttu-id="a3384-120">각각의 경우 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 메서드를 사용하도록 코드를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-120">In each case, the code can be changed to use the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a3384-121">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="a3384-121">Effect on the Runtime</span></span>  
 <span data-ttu-id="a3384-122">MDA는 CLR에 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-122">The MDA does not have any effect on the CLR.</span></span> <span data-ttu-id="a3384-123">로드 요청 결과로 사용된 컨텍스트를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-123">It reports the context that was used as a result of a load request.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a3384-124">출력</span><span class="sxs-lookup"><span data-stu-id="a3384-124">Output</span></span>  
 <span data-ttu-id="a3384-125">MDA는 어셈블리가 `LoadFrom` 컨텍스트에 로드되었음을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-125">The MDA reports that the assembly was loaded into the `LoadFrom` context.</span></span> <span data-ttu-id="a3384-126">어셈블리의 단순한 이름과 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-126">It specifies the simple name of the assembly and the path.</span></span> <span data-ttu-id="a3384-127">`LoadFrom` 컨텍스트를 사용하지 못하게 완화하도록 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-127">It also suggests mitigations to avoid using the `LoadFrom` context.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a3384-128">구성</span><span class="sxs-lookup"><span data-stu-id="a3384-128">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <loadFromContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="a3384-129">예제</span><span class="sxs-lookup"><span data-stu-id="a3384-129">Example</span></span>  
 <span data-ttu-id="a3384-130">다음 코드 예제에서는 이 MDA를 활성화할 수 있는 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3384-130">The following code example demonstrates a situation that can activate this MDA:</span></span>  
  
```csharp
using System.Reflection;  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // The following call caused the LoadFrom context to be used  
            // because the assembly is loaded using LoadFrom and the path is   
            // located outside of the Load context probing path.   
            Assembly.LoadFrom(@"C:\Text\Test.dll");  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3384-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3384-131">See also</span></span>

- [<span data-ttu-id="a3384-132">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="a3384-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
