---
title: "XmlSerializer를 통한 사용자 지정 Serialization 순서 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 975abd20-2a1d-42db-aed3-e898025ccce7
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# XmlSerializer를 통한 사용자 지정 Serialization 순서
[샘플 다운로드](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/CustomOrder.zip.exe)  
  
 이 샘플에서는 XML serialization에서 serialize 및 deserialize되는 요소의 순서를 제어하는 방법을 보여 줍니다.  
  
 serialization에 대한 자세한 내용은 build.proj 파일 및 소스 코드의 주석을 참조하십시오.  
  
### 명령 프롬프트를 사용하여 샘플을 빌드하려면  
  
1.  명령 프롬프트 창을 열고 샘플에 대한 언어별 하위 디렉터리 중 하나로 이동합니다.  
  
2.  명령줄에 **msbuild CustomOrder.sln**을 입력합니다.  
  
### Visual Studio를 사용하여 샘플을 빌드하려면  
  
1.  [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)]를 열고 샘플에 대한 언어별 하위 디렉터리 중 하나로 이동합니다.  
  
2.  CustomOrder.sln의 아이콘을 두 번 클릭하여 Visual Studio에서 파일을 엽니다.  
  
3.  **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.  
  
4.  샘플 응용 프로그램이 기본 \\bin 또는 \\bin\\Debug 하위 디렉터리에 빌드됩니다.  
  
## 참고 항목  
 [System.Runtime.Serialization 네임스페이스](frlrfSystemRuntimeSerialization)   
 [System. Xml.Serialization 네임스페이스](frlrfSystemXmlSerialization)   
 [기본 Serialization](../../../docs/framework/serialization/basic-serialization.md)   
 [이진 Serialization](../../../docs/framework/serialization/binary-serialization.md)   
 [특성을 사용하여 XML Serialization 제어](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md)   
 [XML Serialization 소개](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [Serialization](../../../docs/framework/serialization/index.md)   
 [SOAP Service](http://msdn.microsoft.com/ko-kr/2051c992-28d1-499e-961f-17e9b675cec9)   
 [XML 및 SOAP Serialization](../../../docs/framework/serialization/xml-and-soap-serialization.md)