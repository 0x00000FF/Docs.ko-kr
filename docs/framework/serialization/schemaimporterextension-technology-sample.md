---
title: "SchemaImporterExtension 기술 샘플 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3f5eb78f-0ef6-433a-b095-3a63b1ce0bc9
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# SchemaImporterExtension 기술 샘플
[샘플 다운로드](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/SchemaImporterExtension.zip.exe)  
  
 이 샘플에서는 XML 스키마를 가져올 때의 코드 생성을 자세히 제어할 수 있는 사용자 지정 <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>을 보여 줍니다.이 응용 프로그램에서는 이러한 확장을 빌드, 등록 및 호출하는 방법을 보여 줍니다.  
  
### 명령 프롬프트를 사용하여 샘플을 빌드하려면  
  
1.  명령 프롬프트 창을 열고 샘플에 대한 언어별 하위 디렉터리 중 하나로 이동합니다.  
  
2.  명령줄에 **msbuild.exe OrderSchemaImporterExtension.sln**을 입력합니다.  
  
### Visual Studio를 사용하여 샘플을 빌드하려면  
  
1.  [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)]를 열고 샘플에 대한 언어별 하위 디렉터리 중 하나로 이동합니다.  
  
2.  OrderSchemaImporterExtension.sln의 아이콘을 두 번 클릭하여 Visual Studio에서 파일을 엽니다.  
  
3.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
 응용 프로그램이 기본 \\bin 또는 \\bin\\Debug 디렉터리에 빌드됩니다.  
  
### 이 샘플을 실행하려면  
  
1.  명령 프롬프트를 사용하여 새 실행 파일이 있는 디렉터리로 이동합니다.  
  
2.  명령줄에 **\[실행 이름\]**을 입력합니다.  
  
## 설명  
 샘플의 이진 생성 및 등록 단계에 대한 자세한 내용은 소스 코드의 주석 및 build.proj 파일을 참조하십시오.  
  
## 참고 항목  
 <xref:System.CodeDom.CodeCompileUnit>   
 <xref:System.CodeDom.CodeNamespace>   
 <xref:System.CodeDom.CodeNamespaceImport>   
 <xref:Microsoft.CSharp.CSharpCodeProvider>   
 <xref:System.Xml.Serialization.IXmlSerializable>   
 <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>   
 <xref:System.CodeDom>   
 <xref:System.CodeDom.Compiler>   
 <xref:System.Web.Services.Description>   
 <xref:System.Web.Services.Discovery>   
 <xref:System.Xml.Serialization>   
 <xref:System.Uri>   
 <xref:Microsoft.VisualBasic.VBCodeProvider>   
 <xref:System.Web.Services.Description.WebReference>   
 <xref:System.Xml.Serialization.XmlSchemaImporter>