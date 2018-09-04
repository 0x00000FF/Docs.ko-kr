---
title: '&lt;GCCpuGroup&gt; 요소'
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21ab18cded2b9a16fe2520547287198d3cfe6b74
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529313"
---
# <a name="ltgccpugroupgt-element"></a>&lt;GCCpuGroup&gt; 요소
가비지 수집에서 여러 CPU 그룹을 지원할지를 지정합니다.  
  
 \<configuration>  
\<runtime>  
\<GCCpuGroup>  
  
## <a name="syntax"></a>구문  
  
```xml  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 가비지 수집에서 여러 CPU 그룹을 지원할지를 지정합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|가비지 수집에서 여러 CPU 그룹을 지원 하지 않습니다. 이 값이 기본값입니다.|  
|`true`|가비지 수집이 서버 가비지 수집을 사용 하는 경우 여러 CPU 그룹을 지원 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 컴퓨터에 여러 CPU 그룹이 시간과 서버 가비지 컬렉션이 설정 되었는지 (참조를 [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) 요소), 모든 CPU 그룹에 걸쳐 가비지 컬렉션을 확장 하 고 모든 코어에는이 요소를 사용 하도록 설정 계정 만들기 및 힙 분산 하는 경우입니다.  
  
> [!NOTE]
>  이 요소는 가비지 수집 스레드에만 적용 됩니다. 런타임이 모든 CPU 그룹에 사용자 스레드를 분산할 수 있도록 설정할 수도 있습니다는 [< Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) 요소입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 여러 CPU 그룹에 대 한 가비지 수집을 사용 하도록 설정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [방법: 동시 가비지 수집을 사용 하지 않도록 설정](https://msdn.microsoft.com/library/ba2c6c67-5778-497c-9fac-5f793b5500c7)  
 [워크스테이션 및 서버 가비지 수집](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
