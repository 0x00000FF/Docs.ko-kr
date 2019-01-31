---
title: <system.serviceModel.activation>
ms.date: 03/30/2017
ms.assetid: c0cae85f-56cb-4030-8807-6f96edff8d2d
ms.openlocfilehash: ddb9c03c2d4ec17198719544fba9da989a6b0eb4
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271150"
---
# <a name="systemservicemodelactivation"></a><span data-ttu-id="37484-102">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="37484-102">\<system.serviceModel.activation></span></span>
<span data-ttu-id="37484-103">이 구성 섹션은 SMSvcHost.exe 도구에 대한 구성 설정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="37484-103">This configuration section represents the configuration settings for the SMSvcHost.exe tool.</span></span> <span data-ttu-id="37484-104">해당 구성 요소는 SMSvcHost.exe.config 파일에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37484-104">The configuration elements can be configured in the SMSvcHost.exe.config file.</span></span> <span data-ttu-id="37484-105">특히 여기에는 구성해야 하는 모든 시스템 수준의 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="37484-105">Specifically, it includes all machine-wide settings that must be configured.</span></span>  
  
## <a name="sample-configuration-file"></a><span data-ttu-id="37484-106">샘플 구성 파일</span><span class="sxs-lookup"><span data-stu-id="37484-106">Sample Configuration File</span></span>  
 <span data-ttu-id="37484-107">다음은 수신기 프로세스 SMSvcHost.exe가 사용하는 샘플 구성 파일(SMSvcHost.exe.config)입니다.</span><span class="sxs-lookup"><span data-stu-id="37484-107">The following is a sample configuration file (SMSvcHost.exe.config), which is used by the listener process SMSvcHost.exe.</span></span>  
  
```xml  
<configuration>
  <runtime>
    <gcConcurrent enabled="false" />
  </runtime>
  <system.serviceModel.activation>
    <net.tcp listenBacklog="10"
             maxPendingAccepts="2"
             maxPendingConnections="100"
             receiveTimeout="00:00:10"
             teredoEnabled="false">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18"/>
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19"/>
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-20"/>
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568"/>
      </allowAccounts>
    </net.tcp>
    <net.pipe maxConnectionsPendingDispatch="100"
              maxPendingAccepts="2"
              receiveTimeout="00:00:10">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18" />
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19" />
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-20" />
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568" />
      </allowAccounts>
    </net.pipe>
    <diagnostics performanceCountersEnabled="true" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="37484-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="37484-108">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration>
