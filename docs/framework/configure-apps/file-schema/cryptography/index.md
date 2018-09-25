---
title: 암호화 설정 스키마
ms.date: 03/30/2017
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 71d2edac1dd9a84c9d3c92049d2494c7c5bd54b0
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47083706"
---
# <a name="cryptography-settings-schema"></a>암호화 설정 스키마
암호 설정 스키마에는 암호화 알고리즘을 구현하는 클래스에 알고리즘 이름을 매핑하는 방법을 지정하는 요소가 포함되어 있습니다.  
  
 [**\<configuration>**](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [**\<mscorlib>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)  
  
 [**\<cryptographySettings>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)  
  
 [**\<cryptoNameMapping>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)  
  
 [**\<cryptoClasses>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)  
  
 [**\<cryptoClass>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)  
  
 [**\<nameEntry>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)  
  
 [**\<oidMap>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)  
  
 [**\<oidEntry>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)  
  
|요소|설명|  
|-------------|-----------------|  
|[**\<cryptoClasses**>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)|**\<nameEntry>** 요소에 있는 이름에 매핑되는 암호화 클래스의 목록이 포함되어 있습니다.|  
|[**\<cryptoClass**>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|**\<nameEntry>** 요소에 있는 이름에 매핑되는 암호화 클래스가 포함되어 있습니다.|  
|[**\<cryptographySettings**>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)|암호화 설정이 포함되어 있습니다.|  
|[**\<cryptoNameMapping**>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|이름에 대한 클래스의 매핑이 포함되어 있습니다.|  
|[암호화 설정에 대한 **\<mscorlib>** 요소](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)|**\<cryptographySettings>** 요소가 포함되어 있습니다.|  
|[**\<nameEntry>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)|클래스 이름을 알고리즘 이름에 매핑하며, 이를 통해 하나의 클래스가 여러 이름을 가질 수 있습니다.|  
|[**\<oidEntry>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|ASN.1 OID(개체 식별자)를 이름에 매핑합니다.|  
|[**\<oidMap>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|클래스에 대한 ASN.1 OID 매핑이 포함되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [암호화 서비스](../../../../../docs/standard/security/cryptographic-services.md)
