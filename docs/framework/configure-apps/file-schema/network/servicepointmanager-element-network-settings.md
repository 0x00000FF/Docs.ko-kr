---
title: <servicePointManager> 요소 (네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: 407ed85de109a671030eccff8ddd92af91628014
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202211"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="93f0b-102">\<servicePointManager > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="93f0b-102">\<servicePointManager> Element (Network Settings)</span></span>
<span data-ttu-id="93f0b-103">네트워크 리소스에 대 한 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-103">Configures connections to network resources.</span></span>  
  
 <span data-ttu-id="93f0b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="93f0b-104">\<configuration></span></span>  
<span data-ttu-id="93f0b-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="93f0b-105">\<system.net></span></span>  
<span data-ttu-id="93f0b-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="93f0b-106">\<settings></span></span>  
<span data-ttu-id="93f0b-107">\<servicePointManager></span><span class="sxs-lookup"><span data-stu-id="93f0b-107">\<servicePointManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93f0b-108">구문</span><span class="sxs-lookup"><span data-stu-id="93f0b-108">Syntax</span></span>  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93f0b-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="93f0b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="93f0b-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93f0b-111">특성</span><span class="sxs-lookup"><span data-stu-id="93f0b-111">Attributes</span></span>  
  
|**<span data-ttu-id="93f0b-112">특성</span><span class="sxs-lookup"><span data-stu-id="93f0b-112">Attribute</span></span>**|**<span data-ttu-id="93f0b-113">설명</span><span class="sxs-lookup"><span data-stu-id="93f0b-113">Description</span></span>**|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="93f0b-114">시스템은 인증서의 이름과 인증서를 사용 하기 전에 서버 호스트 이름과 일치 하는지 확인 해야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-114">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="93f0b-115">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-115">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="93f0b-116">시스템 인증서를 사용 하기 전에 인증서를 해지 되었는지 여부를 확인 해야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-116">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="93f0b-117">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-117">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="93f0b-118">밀리초 단위로 DNS 라운드 로빈 옵션을 함께 기간 서비스 DNS (도메인 이름) 해상도 캐시를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-118">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="93f0b-119">기본값은 120,000밀리초(2분)입니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-119">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="93f0b-120">모든 주소 또는 하나의 항목만 반환 여러 IP (인터넷 프로토콜) 주소를 사용 하 여 호스트의 DNS 확인 이름을 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-120">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="93f0b-121">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-121">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="93f0b-122">SSL/TLS 세션에 적용 된 암호화 정책을 지정을 <xref:System.Net.ServicePointManager> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="93f0b-122">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="93f0b-123">가능한 값은 값에 해당 하는 <xref:System.Net.Security.EncryptionPolicy> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-123">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="93f0b-124">사용 <xref:System.Security.Authentication.CipherAlgorithmType.Null> 암호화 정책으로 설정 된 경우 반드시 `NoEncryption`입니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-124">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="93f0b-125">기본값은 `RequireEncryption`입니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-125">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="93f0b-126">POST 메서드를 받을 예상 해야 하는지 여부를 지정 된 `100-continue` 서버에서 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-126">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="93f0b-127">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-127">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="93f0b-128">서비스 지점 관리자에 의해 제어 되는 연결에 Nagle 알고리즘을 사용 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-128">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="93f0b-129">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-129">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93f0b-130">자식 요소</span><span class="sxs-lookup"><span data-stu-id="93f0b-130">Child Elements</span></span>  
 <span data-ttu-id="93f0b-131">없음</span><span class="sxs-lookup"><span data-stu-id="93f0b-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93f0b-132">부모 요소</span><span class="sxs-lookup"><span data-stu-id="93f0b-132">Parent Elements</span></span>  
  
|**<span data-ttu-id="93f0b-133">요소</span><span class="sxs-lookup"><span data-stu-id="93f0b-133">Element</span></span>**|**<span data-ttu-id="93f0b-134">설명</span><span class="sxs-lookup"><span data-stu-id="93f0b-134">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="93f0b-135">설정</span><span class="sxs-lookup"><span data-stu-id="93f0b-135">Settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="93f0b-136"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-136">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93f0b-137">설명</span><span class="sxs-lookup"><span data-stu-id="93f0b-137">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="93f0b-138">구성 파일</span><span class="sxs-lookup"><span data-stu-id="93f0b-138">Configuration Files</span></span>  
 <span data-ttu-id="93f0b-139">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93f0b-139">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93f0b-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="93f0b-140">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="93f0b-141">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="93f0b-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
