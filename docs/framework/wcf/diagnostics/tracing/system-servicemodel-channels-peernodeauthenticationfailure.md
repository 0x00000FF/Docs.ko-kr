---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 38abf80f81a8a885f719603bc93bf1b3687e9938
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a><span data-ttu-id="03b71-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span><span class="sxs-lookup"><span data-stu-id="03b71-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span></span>
<span data-ttu-id="03b71-103">잠재적인 환경이 있는 보안 핸드셰이크가 성공하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="03b71-103">The security handshake with a potential neighbor was not successful.</span></span>  
  
## <a name="description"></a><span data-ttu-id="03b71-104">설명</span><span class="sxs-lookup"><span data-stu-id="03b71-104">Description</span></span>  
 <span data-ttu-id="03b71-105">이 추적은 보안 환경 연결을 설정하는 동안 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="03b71-105">This trace occurs while attempting to establish a secure neighbor connection.</span></span> <span data-ttu-id="03b71-106">이는 자격 증명이 충분하지 않거나 올바르지 않기 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03b71-106">This can happen due to insufficient or incorrect credentials.</span></span>  
  
 <span data-ttu-id="03b71-107">PeerChannel은 강력한 ID인 X.509 인증서에 대한 단일 토큰 형식을 인식합니다. 이는 구현 가능한 인증 및 권한 부여의 형식을 기반으로 강력한 ID 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03b71-107">PeerChannel recognizes a single token type for strong identification, X.509 certificates, which provide a strong identity model based on the type of authentication and authorization that can be implemented.</span></span> <span data-ttu-id="03b71-108">PeerChannel은 암호를 사용하여 간단한 응용 프로그램에 대한 지원도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03b71-108">PeerChannel also provides support for simple applications through the use of passwords.</span></span> <span data-ttu-id="03b71-109">암호는 세션 입장을 허용하는 용도로만 사용할 수 있으며, 메시지 인증에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03b71-109">Passwords can be used only to allow entry to the session; they cannot be used to perform message authentication.</span></span> <span data-ttu-id="03b71-110">이는 피어 그룹이 공유하는 대칭 토큰을 소스 인증에 사용하기에는 어렵고 적절하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="03b71-110">This is because a symmetric token that a group of peers share is difficult and inappropriate to use for source authentication.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="03b71-111">문제 해결</span><span class="sxs-lookup"><span data-stu-id="03b71-111">Troubleshooting</span></span>  
 <span data-ttu-id="03b71-112">모든 환경에 적합한 보안 자격 증명이 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="03b71-112">Ensure that all neighbors have the appropriate security credentials.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03b71-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03b71-113">See Also</span></span>  
 [<span data-ttu-id="03b71-114">피어 채널 보안</span><span class="sxs-lookup"><span data-stu-id="03b71-114">Peer Channel Security</span></span>](../../../../../docs/framework/wcf/feature-details/peer-channel-security.md)  
 [<span data-ttu-id="03b71-115">추적</span><span class="sxs-lookup"><span data-stu-id="03b71-115">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="03b71-116">추적을 사용 하 여 응용 프로그램 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="03b71-116">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="03b71-117">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="03b71-117">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
