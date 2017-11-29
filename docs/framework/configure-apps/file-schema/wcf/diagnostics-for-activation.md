---
title: "활성화를 위한 &lt;diagnostics&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 29f2e56dd18da9dc3ce3206f5c3c80f4a47a7ff0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="72018-102">활성화를 위한 &lt;diagnostics&gt;</span><span class="sxs-lookup"><span data-stu-id="72018-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="72018-103">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 수신기의 진단 기능을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="72018-103">Configures [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="72018-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="72018-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="72018-105">\<진단 ></span><span class="sxs-lookup"><span data-stu-id="72018-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72018-106">구문</span><span class="sxs-lookup"><span data-stu-id="72018-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <diagnostics performanceCountersEnabled="Boolean" />  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="72018-107">형식</span><span class="sxs-lookup"><span data-stu-id="72018-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72018-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="72018-108">Attributes and Elements</span></span>  
 <span data-ttu-id="72018-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72018-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72018-110">특성</span><span class="sxs-lookup"><span data-stu-id="72018-110">Attributes</span></span>  
  
|<span data-ttu-id="72018-111">특성</span><span class="sxs-lookup"><span data-stu-id="72018-111">Attribute</span></span>|<span data-ttu-id="72018-112">설명</span><span class="sxs-lookup"><span data-stu-id="72018-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="72018-113">진단 용도로 성능 카운터를 사용할지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="72018-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72018-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="72018-114">Child Elements</span></span>  
 <span data-ttu-id="72018-115">없음</span><span class="sxs-lookup"><span data-stu-id="72018-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72018-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="72018-116">Parent Elements</span></span>  
  
|<span data-ttu-id="72018-117">요소</span><span class="sxs-lookup"><span data-stu-id="72018-117">Element</span></span>|<span data-ttu-id="72018-118">설명</span><span class="sxs-lookup"><span data-stu-id="72018-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72018-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="72018-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="72018-120">수신기 프로세스 SMSvcHost.exe에 대한 구성 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="72018-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="72018-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72018-121">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
