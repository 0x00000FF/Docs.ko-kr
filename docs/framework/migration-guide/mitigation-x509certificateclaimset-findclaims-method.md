---
title: "완화: X509CertificiateClaimSet.FindClaims 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 3
---
# 완화: X509CertificiateClaimSet.FindClaims 메서드
[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 하는 앱부터 <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName> 메서드는 `claimType` 인수를 해당 SAN 필드의 모든 DNS 항목과 일치시키려 합니다.  
  
## 영향  
 이러한 변경은 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 하는 앱에만 영향을 줍니다.  
  
 이전 버전의 .NET Framework를 대상으로 하는 앱의 경우 <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName> 메서드는 `claimType` 인수를 마지막 DNS 항목에만 일치시키려 합니다.  
  
## 완화  
 이러한 변경을 원치 않는 경우 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 하는 앱은 앱 구성 파일의 [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이 동작을 사용하지 않을 수 있습니다.  
  
```xml  
  
<runtime> <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" /> </runtime>  
  
```  
  
 또한 이전 버전의 .NET Framework를 대상으로 하지만 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에서 실행되는 앱은 앱 구성 파일의 [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이 동작을 옵트인\(opt in\)할 수 있습니다.  
  
```xml  
  
<runtime> <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" /> </runtime>  
  
```  
  
## 참고 항목  
 [대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)