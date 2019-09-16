---
title: 네트워크 추적 해석
ms.date: 03/30/2017
helpviewer_keywords:
- TraceMode attribute
- hexidecimal data, network tracing output
- network tracing, analyzing
- protocolonly
- text, network tracing output
- includehex
ms.assetid: ad22b4b8-00af-4778-9cca-cb609ce1f8ff
ms.openlocfilehash: 09f77a60255accc3e4b1c4fa5ea3d7526444e4cb
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894732"
---
# <a name="interpreting-network-tracing"></a><span data-ttu-id="fcfcf-102">네트워크 추적 해석</span><span class="sxs-lookup"><span data-stu-id="fcfcf-102">Interpreting Network Tracing</span></span>
<span data-ttu-id="fcfcf-103">네트워크 추적이 사용하도록 설정되면 추적 기능을 사용하여 애플리케이션이 다양한 <xref:System.Net> 클래스 멤버에 대해 실행하는 호출을 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfcf-103">When network tracing is enabled, you can use tracing to capture calls your application makes to various <xref:System.Net> class members.</span></span> <span data-ttu-id="fcfcf-104">이러한 호출의 출력은 다음 예제와 비슷할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfcf-104">The output from these calls may be similar to the following examples.</span></span>  
  
```output
[588]   (4357)   Entering Socket#33574638::Send()  
[588]   (4387)   Exiting Socket#33574638::Send()-> 61#61
```  
  
 <span data-ttu-id="fcfcf-105">이전 예제에서 [588]은 현재 스레드의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="fcfcf-105">In the preceding example, [588] is the current thread's unique identifier.</span></span> <span data-ttu-id="fcfcf-106">(4357) 및 (4387)은 애플리케이션이 시작된 이후 경과한 시간(밀리초)을 나타내는 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="fcfcf-106">(4357) and (4387) are timestamps denoting the number of milliseconds that have elapsed since the application started.</span></span> <span data-ttu-id="fcfcf-107">타임스탬프 뒤의 데이터는 애플리케이션이 **Socket.Send** 메서드를 시작 및 종료하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fcfcf-107">The data following the timestamp shows the application entering and exiting the method **Socket.Send**.</span></span> <span data-ttu-id="fcfcf-108">**Send** 메서드를 실행하는 개체의 고유 식별자는 33574638입니다.</span><span class="sxs-lookup"><span data-stu-id="fcfcf-108">The object executing the **Send** method has 33574638 as its unique identifier.</span></span> <span data-ttu-id="fcfcf-109">메서드 종료 추적에는 반환 값이 포함됩니다(이전 예제의 경우 61).</span><span class="sxs-lookup"><span data-stu-id="fcfcf-109">The method exit trace includes the return value (61 in the preceding example).</span></span>  
  
 <span data-ttu-id="fcfcf-110">네트워크 추적은 HTTP(Hypertext Transfer Protocol)와 같은 애플리케이션 수준 프로토콜을 사용하여 애플리케이션이 보내고 받은 네트워크 트래픽을 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfcf-110">Network traces can capture network traffic that is sent from or received by your application using application-level protocols such as Hypertext Transfer Protocol (HTTP).</span></span> <span data-ttu-id="fcfcf-111">이 데이터는 텍스트로 캡처할 수 있고 필요한 경우 16진수 데이터로 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfcf-111">This data can be captured as text and, optionally, hexadecimal data.</span></span> <span data-ttu-id="fcfcf-112">16진수 데이터는 **includehex**를 **tracemode** 특성 값으로 지정할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfcf-112">Hexadecimal data is available when you specify **includehex** as the value of the **tracemode** attribute.</span></span> <span data-ttu-id="fcfcf-113">(이 특성에 대한 자세한 내용은 [방법: 네트워크 추적 구성](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)을 참조하세요.) 다음 예제 추적은 **includehex**를 사용하여 생성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfcf-113">(For detailed information about this attribute, see [How to: Configure Network Tracing](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).) The following example trace was generated using **includehex**.</span></span>  
  
 `[1692]   (1142)   00000000 : 47 45 54 20 2F 77 70 61-64 2E 64 61 74 20 48 54 : GET /wpad.dat HT`  
  
 `[1692]   (1142)   00000010 : 54 50 2F 31 2E 31 0D 0A-48 6F 73 74 3A 20 69 74 : TP/1.1..Host: it`  
  
 `[1692]   (1142)   00000020 : 67 70 72 6F 78 79 0D 0A-43 6F 6E 6E 65 63 74 69 : gproxy..Connecti`  
  
 `[1692]   (1142)   00000030 : 6F 6E 3A 20 43 6C 6F 73-65 0D 0A 0D 0A     : on: Close....`  
  
 <span data-ttu-id="fcfcf-114">16진수 데이터를 제외하려면 **protocolonly**를 **tracemode** 특성 값으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfcf-114">To omit hexadecimal data, specify **protocolonly** as the value for the **tracemode** attribute.</span></span> <span data-ttu-id="fcfcf-115">다음 예제에서는 **protocolonly**가 지정될 경우의 추적을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fcfcf-115">The following example shows the trace when **protocolonly** is specified.</span></span>  
  
 `[2444]   (594)   Data from ConnectStream#33574638::WriteHeaders<<GET /wpad.dat HTTP/1.1`  
  
 `Host: itgproxy`  
  
 `Connection: Close`  
  
## <a name="see-also"></a><span data-ttu-id="fcfcf-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fcfcf-116">See also</span></span>

- [<span data-ttu-id="fcfcf-117">네트워크 추적 사용</span><span class="sxs-lookup"><span data-stu-id="fcfcf-117">Enabling Network Tracing</span></span>](../../../docs/framework/network-programming/enabling-network-tracing.md)
- [<span data-ttu-id="fcfcf-118">방법: 네트워크 추적 구성</span><span class="sxs-lookup"><span data-stu-id="fcfcf-118">How to: Configure Network Tracing</span></span>](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)
- [<span data-ttu-id="fcfcf-119">.NET Framework의 네트워크 추적</span><span class="sxs-lookup"><span data-stu-id="fcfcf-119">Network Tracing in the .NET Framework</span></span>](../../../docs/framework/network-programming/network-tracing.md)
