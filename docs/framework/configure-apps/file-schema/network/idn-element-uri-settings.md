---
title: <idn> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 2d2729f9120d6b6fe673904ad2bf6d005ddf5469
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705118"
---
# <a name="idn-element-uri-settings"></a><span data-ttu-id="20c9b-102">\<idn > 요소 (Uri 설정)</span><span class="sxs-lookup"><span data-stu-id="20c9b-102">\<idn> Element (Uri Settings)</span></span>
<span data-ttu-id="20c9b-103">다국어 도메인 이름 (IDN) 구문 분석 된 도메인 이름에 적용 됩니다 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="20c9b-104">스키마 계층 구조</span><span class="sxs-lookup"><span data-stu-id="20c9b-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="20c9b-105">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="20c9b-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="20c9b-106">\<Uri > 요소 (Uri 설정)</span><span class="sxs-lookup"><span data-stu-id="20c9b-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="20c9b-107">\<idn></span><span class="sxs-lookup"><span data-stu-id="20c9b-107">\<idn></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="20c9b-108">구문</span><span class="sxs-lookup"><span data-stu-id="20c9b-108">Syntax</span></span>  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20c9b-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="20c9b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="20c9b-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20c9b-111">특성</span><span class="sxs-lookup"><span data-stu-id="20c9b-111">Attributes</span></span>  
  
|<span data-ttu-id="20c9b-112">**요소**</span><span class="sxs-lookup"><span data-stu-id="20c9b-112">**Element**</span></span>|<span data-ttu-id="20c9b-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="20c9b-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="20c9b-114">도메인 이름에 적용 되는 다국어 도메인 이름 (IDN) 구문 분석 하는 경우 기본값은 none을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-114">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="20c9b-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="20c9b-115">Child Elements</span></span>  
 <span data-ttu-id="20c9b-116">없음</span><span class="sxs-lookup"><span data-stu-id="20c9b-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="20c9b-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="20c9b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="20c9b-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="20c9b-118">**Element**</span></span>|<span data-ttu-id="20c9b-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="20c9b-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="20c9b-120">uri</span><span class="sxs-lookup"><span data-stu-id="20c9b-120">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="20c9b-121">.NET Framework uniform resource identifier (Uri)를 사용 하 여 표현 하는 웹 주소를 처리 하는 방법을 지정 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20c9b-122">설명</span><span class="sxs-lookup"><span data-stu-id="20c9b-122">Remarks</span></span>  
 <span data-ttu-id="20c9b-123">기존 <xref:System.Uri> 클래스는.NET Framework 3.5에서 확장 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="20c9b-124">3.0 SP1 및 2.0 SP1 식별자 IRI (International Resource) 및 이름을 IDN (Internationalized Domain)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-124">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="20c9b-125">IRI 및 IDN 구체적으로 설정 하지 않으면 현재 사용자가.NET Framework 2.0 동작에서 표시 되지 것입니다 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="20c9b-126">이 덕분에 .NET Framework 이전 버전과의 애플리케이션 호환성이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="20c9b-127">Iri 지원을 사용 하는 다음 두 변경이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="20c9b-128">.NET Framework 2.0 디렉터리 아래에 있는 machine.config 파일에 다음 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="20c9b-129">다국어 도메인 이름 (IDN) 구문 분석 된 도메인 이름에 적용할 것인지와 IRI 구문 분석 규칙을 적용 해야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-129">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="20c9b-130">이 설정은 machine.config 또는 app.config 파일에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="20c9b-131">세 가지 idn 관련 값을 사용 하는 DNS 서버에 따라 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-131">There are three possible values for IDN depending on the DNS servers that are used:</span></span>  
  
- <span data-ttu-id="20c9b-132">idn 사용 = All</span><span class="sxs-lookup"><span data-stu-id="20c9b-132">idn enabled = All</span></span>  
  
     <span data-ttu-id="20c9b-133">이 값은 모든 유니코드 도메인 이름을 해당하는 Punycode 항목(IDN 이름)으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-133">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>  
  
- <span data-ttu-id="20c9b-134">사용 하도록 설정 하는 idn AllExceptIntranet =</span><span class="sxs-lookup"><span data-stu-id="20c9b-134">idn enabled = AllExceptIntranet</span></span>  
  
     <span data-ttu-id="20c9b-135">이 값은 Punycode 항목 (IDN 이름)을 사용 하려면 로컬 인트라넷에 없는 모든 유니코드 도메인 이름을 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-135">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="20c9b-136">이 경우를 처리 하기 위해 로컬 인트라넷에 있는 국가별 이름을 인트라넷에 사용 되는 DNS 서버가 유니코드 이름 확인을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-136">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>  
  
- <span data-ttu-id="20c9b-137">idn 사용 = 없음</span><span class="sxs-lookup"><span data-stu-id="20c9b-137">idn enabled = None</span></span>  
  
     <span data-ttu-id="20c9b-138">이 값은 Punycode를 사용하도록 어떠한 유니코드 도메인 이름도 변환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-138">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="20c9b-139">.NET Framework 2.0 동작을 사용 하 여 일치 하는 기본 값입니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-139">This is the default value which is consistent with the .NET Framework 2.0 behaviour.</span></span>  
  
 <span data-ttu-id="20c9b-140">IDN을 사용하면 도메인 이름의 모든 유니코드 레이블이 해당 Punycode 문자로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-140">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="20c9b-141">Punycode 이름에는 ASCII 문자만 사용되며 항상 xn-- 접두사로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-141">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="20c9b-142">대부분의 DNS 서버는 ASCII 문자만 지원하므로(RFC 3940 참조) 이렇게 해야 인터넷에서 기존 DNS 서버를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-142">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="20c9b-143">구성 파일</span><span class="sxs-lookup"><span data-stu-id="20c9b-143">Configuration Files</span></span>  
 <span data-ttu-id="20c9b-144">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="20c9b-145">예제</span><span class="sxs-lookup"><span data-stu-id="20c9b-145">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="20c9b-146">설명</span><span class="sxs-lookup"><span data-stu-id="20c9b-146">Description</span></span>  
 <span data-ttu-id="20c9b-147">다음 예제에서 사용 하는 구성을 보여 줍니다는 <xref:System.Uri> IRI 구문 분석 및 IDN 이름이 지원 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="20c9b-147">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="20c9b-148">코드</span><span class="sxs-lookup"><span data-stu-id="20c9b-148">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="20c9b-149">참고자료</span><span class="sxs-lookup"><span data-stu-id="20c9b-149">See also</span></span>

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="20c9b-150">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="20c9b-150">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
