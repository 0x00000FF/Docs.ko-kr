---
title: 보안 ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5cd5e660778b852cfee84359bb4d7253ca8f118d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608078"
---
# <a name="security-etw-events"></a><span data-ttu-id="e4dcf-102">보안 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="e4dcf-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="e4dcf-103">보안 이벤트는 강력한 이름 확인 및 Authenticode 확인 중에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="e4dcf-104">이 범주는 다음 이벤트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="e4dcf-105">StrongNameVerificationStart_V1 및 StrongNameVerificationStop_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="e4dcf-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [<span data-ttu-id="e4dcf-106">AuthenticodeVerificationStart_V1 및 AuthenticodeVerificationStop_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="e4dcf-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="e4dcf-107">StrongNameVerificationStart_V1 및 StrongNameVerificationStop_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="e4dcf-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="e4dcf-108">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="e4dcf-109">자세한 내용은 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="e4dcf-110">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="e4dcf-110">Keyword for raising the event</span></span>|<span data-ttu-id="e4dcf-111">수준</span><span class="sxs-lookup"><span data-stu-id="e4dcf-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e4dcf-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="e4dcf-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="e4dcf-113">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="e4dcf-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="e4dcf-114">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e4dcf-115">이벤트</span><span class="sxs-lookup"><span data-stu-id="e4dcf-115">Event</span></span>|<span data-ttu-id="e4dcf-116">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="e4dcf-116">Event ID</span></span>|<span data-ttu-id="e4dcf-117">발생 시기</span><span class="sxs-lookup"><span data-stu-id="e4dcf-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="e4dcf-118">181</span><span class="sxs-lookup"><span data-stu-id="e4dcf-118">181</span></span>|<span data-ttu-id="e4dcf-119">강력한 이름 확인의 시작입니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="e4dcf-120">182</span><span class="sxs-lookup"><span data-stu-id="e4dcf-120">182</span></span>|<span data-ttu-id="e4dcf-121">강력한 이름 확인의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="e4dcf-122">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e4dcf-123">필드 이름</span><span class="sxs-lookup"><span data-stu-id="e4dcf-123">Field name</span></span>|<span data-ttu-id="e4dcf-124">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e4dcf-124">Data type</span></span>|<span data-ttu-id="e4dcf-125">설명</span><span class="sxs-lookup"><span data-stu-id="e4dcf-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e4dcf-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="e4dcf-126">VerificationFlags</span></span>|<span data-ttu-id="e4dcf-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4dcf-127">win:UInt32</span></span>|<span data-ttu-id="e4dcf-128">확인 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-128">The verification flags.</span></span>|  
|<span data-ttu-id="e4dcf-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="e4dcf-129">ErrorCode</span></span>|<span data-ttu-id="e4dcf-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4dcf-130">win:UInt32</span></span>|<span data-ttu-id="e4dcf-131">HResult 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-131">The HResult error code.</span></span>|  
|<span data-ttu-id="e4dcf-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="e4dcf-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="e4dcf-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="e4dcf-133">win:UnicodeString</span></span>|<span data-ttu-id="e4dcf-134">정규화된 어셈블리 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="e4dcf-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e4dcf-135">ClrInstanceID</span></span>|<span data-ttu-id="e4dcf-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e4dcf-136">win:UInt16</span></span>|<span data-ttu-id="e4dcf-137">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="e4dcf-138">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="e4dcf-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="e4dcf-139">AuthenticodeVerificationStart_V1 및 AuthenticodeVerificationStop_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="e4dcf-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="e4dcf-140">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e4dcf-141">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="e4dcf-141">Keyword for raising the event</span></span>|<span data-ttu-id="e4dcf-142">수준</span><span class="sxs-lookup"><span data-stu-id="e4dcf-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e4dcf-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="e4dcf-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="e4dcf-144">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="e4dcf-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="e4dcf-145">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e4dcf-146">이벤트</span><span class="sxs-lookup"><span data-stu-id="e4dcf-146">Event</span></span>|<span data-ttu-id="e4dcf-147">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="e4dcf-147">Event ID</span></span>|<span data-ttu-id="e4dcf-148">발생 시기</span><span class="sxs-lookup"><span data-stu-id="e4dcf-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="e4dcf-149">183</span><span class="sxs-lookup"><span data-stu-id="e4dcf-149">183</span></span>|<span data-ttu-id="e4dcf-150">Authenticode 확인의 시작입니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="e4dcf-151">184</span><span class="sxs-lookup"><span data-stu-id="e4dcf-151">184</span></span>|<span data-ttu-id="e4dcf-152">Authenticode 확인의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="e4dcf-153">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e4dcf-154">필드 이름</span><span class="sxs-lookup"><span data-stu-id="e4dcf-154">Field name</span></span>|<span data-ttu-id="e4dcf-155">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e4dcf-155">Data type</span></span>|<span data-ttu-id="e4dcf-156">설명</span><span class="sxs-lookup"><span data-stu-id="e4dcf-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e4dcf-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="e4dcf-157">VerificationFlags</span></span>|<span data-ttu-id="e4dcf-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4dcf-158">win:UInt32</span></span>|<span data-ttu-id="e4dcf-159">확인 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-159">The verification flags.</span></span>|  
|<span data-ttu-id="e4dcf-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="e4dcf-160">ErrorCode</span></span>|<span data-ttu-id="e4dcf-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e4dcf-161">win:UInt32</span></span>|<span data-ttu-id="e4dcf-162">HResult 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-162">The HResult error code.</span></span>|  
|<span data-ttu-id="e4dcf-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="e4dcf-163">ModulePath</span></span>|<span data-ttu-id="e4dcf-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="e4dcf-164">win:UnicodeString</span></span>|<span data-ttu-id="e4dcf-165">모듈 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-165">The module path.</span></span>|  
|<span data-ttu-id="e4dcf-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e4dcf-166">ClrInstanceID</span></span>|<span data-ttu-id="e4dcf-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e4dcf-167">win:UInt16</span></span>|<span data-ttu-id="e4dcf-168">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e4dcf-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4dcf-169">참고자료</span><span class="sxs-lookup"><span data-stu-id="e4dcf-169">See also</span></span>
- [<span data-ttu-id="e4dcf-170">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="e4dcf-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
