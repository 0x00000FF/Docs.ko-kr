---
title: <appDomainManagerAssembly> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4fe1dfbd62a6967ae51031fa12f80e9c5563dc44
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182353"
---
# <a name="appdomainmanagerassembly-element"></a>\<appDomainManagerAssembly> Element
프로세스의 기본 애플리케이션 도메인용 애플리케이션 도메인 관리자를 제공하는 어셈블리를 지정합니다.  
  
 \<configuration>  
\<runtime>  
\<appDomainManagerAssembly>  
  
## <a name="syntax"></a>구문  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`value`|필수 특성입니다. 프로세스에서 기본 응용 프로그램 도메인에 대 한 응용 프로그램 도메인 관리자를 제공 하는 어셈블리의 표시 이름을 지정 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 응용 프로그램 도메인 관리자의 형식을 지정 하려면이 두 요소를 지정 해야 하며 [ \<appDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) 요소입니다. 이러한 요소 중 하나를 지정 하지 않은 경우 다른 무시 됩니다.  
  
 기본 응용 프로그램 도메인 로드 되 면 <xref:System.TypeLoadException> 없으면 지정된 된 어셈블리 또는 어셈블리에 지정 된 형식 없는 경우 throw 되는 [ \<appDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) 요소 및 프로세스가 시작 되지 않습니다. 어셈블리를 찾았지만 버전 정보와 일치 하지 않는 경우는 <xref:System.IO.FileLoadException> throw 됩니다.  
  
 기본 응용 프로그램 도메인에 대 한 응용 프로그램 도메인 관리자 종류를 지정 하면 기본 응용 프로그램 도메인에서 만든 응용 프로그램 도메인을 다른 응용 프로그램 도메인 관리자 형식을 상속 합니다. 사용 된 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> 및 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> 새 응용 프로그램 도메인의 다른 응용 프로그램 도메인 관리자 유형을 지정 하는 속성입니다.  
  
 응용 프로그램 도메인 관리자 유형을 지정 하는 응용 프로그램에 완전 신뢰에 필요 합니다. (예를 들어, 데스크톱에서 실행 중인 응용 프로그램에 완전 신뢰) 응용 프로그램에 완전 신뢰가 없는 경우는 <xref:System.TypeLoadException> throw 됩니다.  
  
 형식의 어셈블리 표시 이름에 대 한 참조를 <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> 속성입니다.  
  
 이 구성 요소는 에서만 사용할 수는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 이상.  
  
## <a name="example"></a>예제  
 다음 예제에서는 프로세스의 기본 응용 프로그램 도메인에 대 한 응용 프로그램 도메인 관리자는 지정 하는 방법을 보여 줍니다 합니다 `MyMgr` 입력을 `AdMgrExample` 어셈블리입니다.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [\<appDomainManagerType> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)
- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [SetAppDomainManagerType 메서드](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
