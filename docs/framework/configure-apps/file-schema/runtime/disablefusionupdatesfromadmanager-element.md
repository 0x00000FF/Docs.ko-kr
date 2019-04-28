---
title: <disableFusionUpdatesFromADManager> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27c8c1cac68aca1c40826ff549d62d9636d9b0c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704910"
---
# <a name="disablefusionupdatesfromadmanager-element"></a>\<disableFusionUpdatesFromADManager > 요소
런타임 호스트가 애플리케이션 도메인에 대한 구성 설정을 재정의할 수 있도록 허용하는 기본 동작을 사용하지 않도록 설정할지를 지정합니다.  
  
 \<구성 > 요소  
\<런타임 > 요소  
\<disableFusionUpdatesFromADManager>  
  
## <a name="syntax"></a>구문  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|사용|필수 특성입니다.<br /><br /> Fusion 설정을 재정의 하는 기본 기능을 사용할 수 있는지 여부를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|0|Fusion 설정을 재정의 하는 기능을 해제 하지 않습니다. 이 기본 동작을 사용 하 여 시작 된 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]합니다.|  
|1|Fusion 설정을 재정의 하는 기능을 사용 하지 않도록 설정 합니다. 이.NET Framework의 이전 버전의 동작으로 돌아갑니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 부터 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], 기본 동작은 허용 하는 <xref:System.AppDomainManager> 개체를 사용 하 여 구성 설정을 재정의 하려면를 <xref:System.AppDomainSetup.ConfigurationFile%2A> 속성 또는 <xref:System.AppDomainSetup.SetConfigurationBytes%2A> 메서드의 <xref:System.AppDomainSetup> 구현에 전달 되는 개체 <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> 의 서브 클래스에서 메서드를 <xref:System.AppDomainManager>입니다. 기본 응용 프로그램 도메인에 대 한 설정을 변경 하면 응용 프로그램 구성 파일에 지정 된 설정을 재정의 합니다. 에 전달 된 구성 설정을 다른 응용 프로그램 도메인에 대 한 재정의 <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> 또는 <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> 메서드.  
  
 새 구성 정보를 전달 하거나 null을 전달 (`Nothing` Visual Basic에서)에 전달 된 구성 정보를 제거 합니다.  
  
 둘 다에 구성 정보를 전달 하지 마십시오 합니다 <xref:System.AppDomainSetup.ConfigurationFile%2A> 속성 및 <xref:System.AppDomainSetup.SetConfigurationBytes%2A> 메서드. 둘 다에 구성 정보를 전달 하는 경우 정보를 전달 하는 <xref:System.AppDomainSetup.ConfigurationFile%2A> 때문에 속성이 무시 됩니다는 <xref:System.AppDomainSetup.SetConfigurationBytes%2A> 메서드는 응용 프로그램 구성 파일에서 구성 정보를 재정의 합니다. 사용 하는 경우는 <xref:System.AppDomainSetup.ConfigurationFile%2A> 속성에 null을 전달할 수 (`Nothing` Visual Basic의)에 <xref:System.AppDomainSetup.SetConfigurationBytes%2A> 메서드 호출에 지정 된 모든 구성 바이트를 제거 하는 <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> 또는 <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> 메서드.  
  
 구성 정보 외에도 다음 설정에서 변경할 수 있습니다 합니다 <xref:System.AppDomainSetup> 의 구현에 전달 되는 개체를 <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> 메서드: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>를 <xref:System.AppDomainSetup.CachePath%2A>를 <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>를 <xref:System.AppDomainSetup.PrivateBinPath%2A>를 <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>를 <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, 및 <xref:System.AppDomainSetup.ShadowCopyFiles%2A>합니다.  
  
 사용 하 여 대 안으로 `<disableFusionUpdatesFromADManager>` 요소인 레지스트리 설정을 만들어 또는 환경 변수를 설정 하 여 기본 동작을 비활성화할 수 있습니다. 레지스트리에서 라는 dword를 만듭니다 `COMPLUS_disableFusionUpdatesFromADManager` 아래에서 `HKCU\Software\Microsoft\.NETFramework` 또는 `HKLM\Software\Microsoft\.NETFramework`, 값을 1로 설정 합니다. 명령줄에서 환경 변수를 설정 `COMPLUS_disableFusionUpdatesFromADManager` 1입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하 여 Fusion 설정을 재정의 하는 기능을 사용 하지 않도록 설정 하는 방법의 `<disableFusionUpdatesFromADManager>` 요소입니다.  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [런타임에서 어셈블리를 찾는 방법](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
