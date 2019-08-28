---
ms.openlocfilehash: f70452cbadc8927521f0fcfda693586c277e4d0f
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70041159"
---
> [!CAUTION]
> <span data-ttu-id="70147-101">코드 액세스 보안 및 부분적으로 신뢰할 수 있는 코드</span><span class="sxs-lookup"><span data-stu-id="70147-101">Code Access Security and Partially Trusted Code</span></span>
>
> <span data-ttu-id="70147-102">.NET Framework는 동일한 애플리케이션에서 실행되는 다른 코드에 다양한 신뢰 수준을 적용하기 위한 CAS(코드 액세스 보안)라는 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="70147-102">The .NET Framework provides a mechanism for the enforcement of varying levels of trust on different code running in the same application called Code Access Security (CAS).</span></span>  <span data-ttu-id="70147-103">.NET Framework의 코드 액세스 보안은 코드 발생 위치 또는 코드의 다른 ID 측면에 따라 보안 경계를 적용하기 위한 메커니즘으로 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70147-103">Code Access Security in .NET Framework should not  be used as a mechanism for enforcing security boundaries based on code origination or other identity aspects.</span></span> <span data-ttu-id="70147-104">앞으로 코드 액세스 보안 및 보안 투명 코드를 부분적으로 신뢰할 수 있는 코드, 특히 출처를 알 수 없는 코드의 보안 경계로 사용할 수 없음을 나타내도록 지침이 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70147-104">We are updating our guidance to reflect that Code Access Security and Security-Transparent Code will not be supported as a security boundary with partially trusted code, especially code of unknown origin.</span></span> <span data-ttu-id="70147-105">대체 보안 조치를 적용하지 않고 출처를 알 수 없는 코드를 로드 및 실행하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="70147-105">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span>
>
> <span data-ttu-id="70147-106">이 정책은 모든 버전의 .NET Framework에 적용되지만 Silverlight에 포함된 .NET Framework에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70147-106">This policy applies to all versions of .NET Framework, but does not apply to the .NET Framework included in Silverlight.</span></span>
