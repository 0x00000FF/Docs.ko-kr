---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 3ea99d360ceb1e3fe6e97cbf9c8827dd7c853f63
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55256526"
---
# <a name="persistabletype"></a>\<persistableType>
모든 지속 형식을 지정합니다.  
  
 \<system.ServiceModel>  
\<comContracts>  
\<comContract>  
  
## <a name="syntax"></a>구문  
  
```xml  
<comContracts>
  <comContract>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="type"></a>형식  
 `Type`  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|id|지속 형식에 대한 고유 식별자를 지정하는 문자열이 포함된 필수적 특성입니다.|  
|name|지속 형식의 이름을 지정하는 문자열이 포함된 선택적 특성입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<persistableTypes>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|`persistableType` 요소의 컬렉션입니다.|  
  
## <a name="see-also"></a>참고자료
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [\<comContracts>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [COM+ 애플리케이션과 통합](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [방법: COM + 서비스 설정 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
