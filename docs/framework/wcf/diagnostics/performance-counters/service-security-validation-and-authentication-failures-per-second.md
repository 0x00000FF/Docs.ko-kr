---
title: '서비스: Security Validation and Authentication Failures Per Second'
ms.date: 03/30/2017
ms.assetid: 4af18009-e778-490b-9ba6-e76485285830
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: fb0d4fdebf07dacfa7f33d8645332348270128e4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43884841"
---
# <a name="service-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="76049-102">서비스: Security Validation and Authentication Failures Per Second</span><span class="sxs-lookup"><span data-stu-id="76049-102">Service: Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="76049-103">카운터 이름: Security Validation and Authentication Failures Per Second</span><span class="sxs-lookup"><span data-stu-id="76049-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="76049-104">설명</span><span class="sxs-lookup"><span data-stu-id="76049-104">Description</span></span>  
 <span data-ttu-id="76049-105">이 카운터는 "Security Calls Not Authorized" 카운터로 처리되지 않는 보안 문제 때문에 메시지가 거부될 때마다 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="76049-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="76049-106">이러한 문제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="76049-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="76049-107">클라이언트 토큰을 메시지에서 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76049-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="76049-108">클라이언트 토큰에서 인증에 실패했습니다(예: 잘못된 암호).</span><span class="sxs-lookup"><span data-stu-id="76049-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="76049-109">서명 확인에 실패했습니다(예: 메시지 변조).</span><span class="sxs-lookup"><span data-stu-id="76049-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="76049-110">메시지가 이전 메시지와 중복됩니다. 이러한 현상은 재생 공격 중에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76049-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="76049-111">해독 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="76049-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="76049-112">일부 필수 요소(예: 타임스탬프 또는 암호화된 데이터 블록)가 메시지에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76049-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="76049-113">TLSNEGO/SPNEGO 핸드셰이크 중에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="76049-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="76049-114">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음 수식을 사용 하 여 계산</span><span class="sxs-lookup"><span data-stu-id="76049-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula,</span></span>  
  
 <span data-ttu-id="76049-115">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="76049-115">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
