---
title: NameValueSectionHandler 및 DictionarySectionHandler에 대 한 사용자 지정 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 731e52958b89886c2bc069c4c181c0cc3928d487
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57845711"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>NameValueSectionHandler 및 DictionarySectionHandler에 대 한 사용자 지정 요소

사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 합니다 <xref:System.Configuration.NameValueSectionHandler> 고 <xref:System.Configuration.DictionarySectionHandler> 클래스입니다.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)\
&nbsp;&nbsp;**\<sectionName>**

## <a name="attributes"></a>특성

없음

## <a name="parent-element"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) | 공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다. |

## <a name="child-elements"></a>자식 요소

|     | 설명 |
| --- | ----------- |
| [**\<추가 >** ](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) 에 대 한 <xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler>  | 사용자 지정 응용 프로그램 설정을 추가합니다. |
| [**\<제거 >** ](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) 에 대 한 <xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler> | 이전에 정의 된 설정을 제거합니다. |
| [**\<지우기 >** ](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) 에 대 한 <xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler> | 섹션에서 이전에 정의 된 모든 설정을 지웁니다. |

## <a name="remarks"></a>설명

합니다  **\<sectionName >** 정의한 사용자 지정 요소입니다를  **\<섹션 >** 태그를  **\<configSections >** 요소입니다.

다음 표에서 각 구성 섹션 처리기에 대 한 반환 ConfigurationSettings.GetConfig 메서드 개체의 형식을 보여 줍니다.

| 구성 섹션 처리기                        | 반환 형식                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a>예제

다음 예제를 사용 하는 섹션을 선언 하는 방법을 보여 줍니다 합니다 <xref:System.Configuration.DictionarySectionHandler> 고 <xref:System.Configuration.NameValueSectionHandler> 클래스입니다.

첫 번째 사용자 지정 요소  **\<dictionarySample >**, 읽은 설정을 포함 하는 합니다 <xref:System.Configuration.DictionarySectionHandler> 클래스는 `System.dll` 어셈블리입니다. 두 번째 사용자 지정 요소는  **\<mySection >**, 읽은 설정을 포함 하는 합니다 <xref:System.Configuration.NameValueSectionHandler> 클래스는 `System.dll` 어셈블리입니다.

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a>구성 파일

응용 프로그램 구성 파일을 컴퓨터 구성 파일에서이 요소를 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.

## <a name="see-also"></a>참고자료

- [.NET Framework의 구성 파일 스키마](~/docs/framework/configure-apps/file-schema/index.md)
