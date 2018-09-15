---
title: Security Validation and Authentication Failures Per Second
ms.date: 03/30/2017
ms.assetid: 266c3bd3-2ffc-4471-94b7-3675443be1ac
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 4836a5076401de2f7c3112b298cdadc0e0307962
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2018
ms.locfileid: "45641061"
---
# <a name="security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="e5fac-102">Security Validation and Authentication Failures Per Second</span><span class="sxs-lookup"><span data-stu-id="e5fac-102">Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="e5fac-103">카운터 이름: Security Validation and Authentication Failures Per Second</span><span class="sxs-lookup"><span data-stu-id="e5fac-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e5fac-104">설명</span><span class="sxs-lookup"><span data-stu-id="e5fac-104">Description</span></span>  
 <span data-ttu-id="e5fac-105">이 카운터는 "Security Calls Not Authorized" 카운터로 처리되지 않는 보안 문제 때문에 메시지가 거부될 때마다 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fac-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="e5fac-106">이러한 문제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e5fac-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="e5fac-107">클라이언트 토큰을 메시지에서 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5fac-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="e5fac-108">클라이언트 토큰에서 인증에 실패했습니다(예: 잘못된 암호).</span><span class="sxs-lookup"><span data-stu-id="e5fac-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="e5fac-109">서명 확인에 실패했습니다(예: 메시지 변조).</span><span class="sxs-lookup"><span data-stu-id="e5fac-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="e5fac-110">메시지가 이전 메시지와 중복됩니다. 이러한 현상은 재생 공격 중에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5fac-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="e5fac-111">해독 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="e5fac-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="e5fac-112">일부 필수 요소(예: 타임스탬프 또는 암호화된 데이터 블록)가 메시지에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5fac-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="e5fac-113">TLSNEGO/SPNEGO 핸드셰이크 중에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="e5fac-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="e5fac-114">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음 수식을 사용 하 여 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5fac-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="e5fac-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="e5fac-115">(N1-N0)/((D1-D0)/F)</span></span>
