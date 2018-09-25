---
title: '&lt;제거&gt; schemeSettings (Uri 설정)에 대 한'
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 3f4e3dbdc3dae425e44cd1c0890e8fef9d42a780
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47072724"
---
# <a name="ltremovegt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="9a3f0-102">&lt;제거&gt; schemeSettings (Uri 설정)에 대 한</span><span class="sxs-lookup"><span data-stu-id="9a3f0-102">&lt;remove&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="9a3f0-103">스키마 이름에 대 한 스키마 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3f0-103">Removes a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="9a3f0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9a3f0-104">\<configuration></span></span>  
<span data-ttu-id="9a3f0-105">\<uri ></span><span class="sxs-lookup"><span data-stu-id="9a3f0-105">\<uri></span></span>  
<span data-ttu-id="9a3f0-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="9a3f0-106">\<schemeSettings></span></span>  
<span data-ttu-id="9a3f0-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="9a3f0-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a3f0-108">구문</span><span class="sxs-lookup"><span data-stu-id="9a3f0-108">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a3f0-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9a3f0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9a3f0-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3f0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a3f0-111">특성</span><span class="sxs-lookup"><span data-stu-id="9a3f0-111">Attributes</span></span>  
  
|<span data-ttu-id="9a3f0-112">특성</span><span class="sxs-lookup"><span data-stu-id="9a3f0-112">Attribute</span></span>|<span data-ttu-id="9a3f0-113">설명</span><span class="sxs-lookup"><span data-stu-id="9a3f0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9a3f0-114">name</span><span class="sxs-lookup"><span data-stu-id="9a3f0-114">name</span></span>|<span data-ttu-id="9a3f0-115">이 설정은 적용 되는 체계 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3f0-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="9a3f0-116">이름과 "http"만 지원 되는 값 이름 = = "https"입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3f0-116">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a3f0-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9a3f0-117">Child Elements</span></span>  
 <span data-ttu-id="9a3f0-118">없음</span><span class="sxs-lookup"><span data-stu-id="9a3f0-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9a3f0-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9a3f0-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9a3f0-120">요소</span><span class="sxs-lookup"><span data-stu-id="9a3f0-120">Element</span></span>|<span data-ttu-id="9a3f0-121">설명</span><span class="sxs-lookup"><span data-stu-id="9a3f0-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a3f0-122">\<schemeSettings> 요소 (URI 설정)</span><span class="sxs-lookup"><span data-stu-id="9a3f0-122">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="9a3f0-123">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3f0-123">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a3f0-124">설명</span><span class="sxs-lookup"><span data-stu-id="9a3f0-124">Remarks</span></span>  
 <span data-ttu-id="9a3f0-125">기본적으로 <xref:System.Uri?displayProperty=nameWithType> 클래스 이스케이프 해제 백분율로 인코딩된 경로 압축을 실행 하기 전에 경로 구분 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3f0-125">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="9a3f0-126">다음과 같은 공격에 대 한 보안 메커니즘으로 구현 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9a3f0-126">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="9a3f0-127">이 URI에 전달 하는 경우 모듈까지 %를 처리 하지 못할 경우 인코딩된 문자를 올바르게, 서버에서 실행 되 고 다음 명령에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a3f0-127">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="9a3f0-128">이러한 이유로 <xref:System.Uri?displayProperty=nameWithType> 클래스가 먼저 이스케이프 해제 경로 구분 기호 및 경로 압축을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3f0-128">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="9a3f0-129">위의 악성 URL을 전달 하는 결과 <xref:System.Uri?displayProperty=nameWithType> 클래스 생성자에 다음 URI:</span><span class="sxs-lookup"><span data-stu-id="9a3f0-129">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="9a3f0-130">SchemeSettings 구성 옵션을 사용 하 여 특정 스키마에 대 한 이스케이프 해제 백분율로 인코딩된 경로 구분 되지에이 기본 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a3f0-130">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9a3f0-131">구성 파일</span><span class="sxs-lookup"><span data-stu-id="9a3f0-131">Configuration Files</span></span>  
 <span data-ttu-id="9a3f0-132">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a3f0-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a3f0-133">예제</span><span class="sxs-lookup"><span data-stu-id="9a3f0-133">Example</span></span>  
 <span data-ttu-id="9a3f0-134">다음 예제에서 사용 하는 구성을 보여 줍니다는 <xref:System.Uri> http 체계에 대 한 스키마 설정을 제거 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3f0-134">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a3f0-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a3f0-135">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="9a3f0-136">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="9a3f0-136">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
