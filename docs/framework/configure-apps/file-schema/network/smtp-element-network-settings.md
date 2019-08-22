---
title: <smtp> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: ac9405fdc6123a5a1352de06f94fefb6d7d4014b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659117"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="e71b0-102">\<smtp > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="e71b0-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="e71b0-103">전자 메일을 보내기 위한 배달 형식, 배달 방법 및 보낸 사람 주소를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
 <span data-ttu-id="e71b0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e71b0-104">\<configuration></span></span>  
<span data-ttu-id="e71b0-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e71b0-105">\<system.net></span></span>  
<span data-ttu-id="e71b0-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="e71b0-106">\<mailSettings></span></span>  
<span data-ttu-id="e71b0-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="e71b0-107">\<smtp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e71b0-108">구문</span><span class="sxs-lookup"><span data-stu-id="e71b0-108">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e71b0-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e71b0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e71b0-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e71b0-111">특성</span><span class="sxs-lookup"><span data-stu-id="e71b0-111">Attributes</span></span>  
  
|<span data-ttu-id="e71b0-112">특성</span><span class="sxs-lookup"><span data-stu-id="e71b0-112">Attribute</span></span>|<span data-ttu-id="e71b0-113">Description</span><span class="sxs-lookup"><span data-stu-id="e71b0-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="e71b0-114">보내는 전자 메일의 배달 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="e71b0-115">허용 가능한 값은 SevenBit와 International입니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="e71b0-116">전자 메일에 대 한 배달 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="e71b0-117">허용 되는 값은 Network, PickupDirectoryFromIis 및 SpecifiedPickupDirectory입니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="e71b0-118">보내는 전자 메일의 보낸 사람 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e71b0-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e71b0-119">Child Elements</span></span>  
  
|<span data-ttu-id="e71b0-120">특성</span><span class="sxs-lookup"><span data-stu-id="e71b0-120">Attribute</span></span>|<span data-ttu-id="e71b0-121">Description</span><span class="sxs-lookup"><span data-stu-id="e71b0-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="e71b0-122">SMTP (Simple Mail Transport Protocol) 서버에 대 한 로컬 디렉터리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="e71b0-123">외부 SMTP 서버에 대 한 네트워크 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e71b0-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e71b0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="e71b0-125">**요소**</span><span class="sxs-lookup"><span data-stu-id="e71b0-125">**Element**</span></span>|<span data-ttu-id="e71b0-126">**설명**</span><span class="sxs-lookup"><span data-stu-id="e71b0-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e71b0-127">\<mailSettings> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="e71b0-127">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="e71b0-128">메일 전송 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e71b0-129">예제</span><span class="sxs-lookup"><span data-stu-id="e71b0-129">Example</span></span>  
 <span data-ttu-id="e71b0-130">다음 예에서는 기본 네트워크 자격 증명을 사용 하 여 전자 메일을 보낼 적절 한 SMTP 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e71b0-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="e71b0-131">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="e71b0-132">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="e71b0-132">Network Settings Schema</span></span>](index.md)
