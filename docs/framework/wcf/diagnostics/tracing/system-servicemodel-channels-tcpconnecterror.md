---
title: System.ServiceModel.Channels.TcpConnectError
ms.date: 03/30/2017
ms.assetid: 22d93797-072e-405d-a3e0-5c519ddf290b
ms.openlocfilehash: 68c3ecaf1009cf46db55b362cce0d1ab6c386c7e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548065"
---
# <a name="systemservicemodelchannelstcpconnecterror"></a><span data-ttu-id="1c43d-102">System.ServiceModel.Channels.TcpConnectError</span><span class="sxs-lookup"><span data-stu-id="1c43d-102">System.ServiceModel.Channels.TcpConnectError</span></span>
<span data-ttu-id="1c43d-103">TCP 연결 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c43d-103">The TCP connect operation failed.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1c43d-104">설명</span><span class="sxs-lookup"><span data-stu-id="1c43d-104">Description</span></span>  
 <span data-ttu-id="1c43d-105">이 경고 수준 추적은 TCP 엔드포인트에 연결하지 못했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c43d-105">This warning level trace indicates a failure to connect to a TCP endpoint.</span></span> <span data-ttu-id="1c43d-106">이 오류는 원격 엔드포인트가 지정된 IP 주소 및 포트에서 응답하지 않는 경우 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c43d-106">This could happen if the remote endpoint is not responding at a given IP address and port.</span></span> <span data-ttu-id="1c43d-107">이후에 다른 유효한 IP 주소(예를 들어 IPv4 또는 IPv6 주소 또는 지정된 호스트 이름을 나타내는 다른 IP 주소)에 대한 연결을 시도하여 성공한 경우 이 추적은 무시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c43d-107">This trace can be ignored if subsequent attempts to connect to other valid IP addresses (such as IPv4 or IPv6 addresses, or other IP addresses representing a given hostname) succeed.</span></span> <span data-ttu-id="1c43d-108">이 추적 내의 예외는 오류에 대한 추가 정보를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c43d-108">The exception within this trace can reveal additional information about the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c43d-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="1c43d-109">See also</span></span>
- [<span data-ttu-id="1c43d-110">추적</span><span class="sxs-lookup"><span data-stu-id="1c43d-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="1c43d-111">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1c43d-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="1c43d-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="1c43d-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
