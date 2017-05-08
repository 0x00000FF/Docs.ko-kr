---
title: "&lt;xmlSchemaImporterExtensions&gt;의 요소 &lt;add&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<xmlSchemaImporterExtensions> 요소의 <add> 요소"
  - "XML serialization, configuration"
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;xmlSchemaImporterExtensions&gt;의 요소 &lt;add&gt;
<xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET Framework 형식으로 매핑하는 데 사용하는 형식을 추가합니다.  구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../../docs/framework/configure-apps/file-schema/index.md)을 참조하세요.  
  
 \<XmlSchemaImporterExtensions\>  
\<add\>  
  
## 구문  
  
```  
  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|**name**|인스턴스를 찾는 데 사용되는 단순한 이름입니다.|  
|**type**|필수 요소.  추가할 스키마 확장 클래스를 지정합니다.  **type** 특성 값은 한 줄로 표시되어야 하며 정규화된 형식 이름을 포함해야 합니다.  GAC\(전역 어셈블리 캐시\)에 추가되는 어셈블리에는 서명된 어셈블리의 버전, 문화권 및 공개 키 토큰도 포함되어 있어야 합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|\<xmlSchemaImporterExtensions\>|<xref:System.Xml.Serialization.XmlSchemaImporter>에서 사용하는 형식을 포함합니다.|  
  
## 예제  
 다음 코드 예제에서는 XmlSchemaImporter가 형식을 매핑할 때 사용할 수 있는 확장 형식을 추가합니다.  
  
```  
<configuration>  
  <system.xml.serialization>  
    <xmlSchemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,   
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a" />   
    </xmlSchemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 [\<system.xml.serialization\> 요소](../../../docs/framework/serialization/system-xml-serialization-element.md)   
 [\<schemaImporterExtensions\> 요소](../../../docs/framework/serialization/schemaimporterextensions-element.md)