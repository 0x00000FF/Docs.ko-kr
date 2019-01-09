---
title: 활성화를 위한 &lt;diagnostics&gt;
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 28f051a7ab06dbc1b40f804c56071818eb37e88b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54144979"
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="f6545-102">활성화를 위한 &lt;diagnostics&gt;</span><span class="sxs-lookup"><span data-stu-id="f6545-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="f6545-103">Windows Communication Foundation (WCF) 수신기의 진단 기능을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f6545-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="f6545-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="f6545-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="f6545-105">\<진단 ></span><span class="sxs-lookup"><span data-stu-id="f6545-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6545-106">구문</span><span class="sxs-lookup"><span data-stu-id="f6545-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="f6545-107">형식</span><span class="sxs-lookup"><span data-stu-id="f6545-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6545-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f6545-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f6545-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6545-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6545-110">특성</span><span class="sxs-lookup"><span data-stu-id="f6545-110">Attributes</span></span>  
  
|<span data-ttu-id="f6545-111">특성</span><span class="sxs-lookup"><span data-stu-id="f6545-111">Attribute</span></span>|<span data-ttu-id="f6545-112">설명</span><span class="sxs-lookup"><span data-stu-id="f6545-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="f6545-113">진단 용도로 성능 카운터를 사용할지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f6545-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6545-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f6545-114">Child Elements</span></span>  
 <span data-ttu-id="f6545-115">없음</span><span class="sxs-lookup"><span data-stu-id="f6545-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f6545-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f6545-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f6545-117">요소</span><span class="sxs-lookup"><span data-stu-id="f6545-117">Element</span></span>|<span data-ttu-id="f6545-118">설명</span><span class="sxs-lookup"><span data-stu-id="f6545-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6545-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="f6545-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="f6545-120">수신기 프로세스 SMSvcHost.exe에 대한 구성 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f6545-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f6545-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6545-121">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
