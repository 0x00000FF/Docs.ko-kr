---
title: "WCF 확장에 대한 사용자 지정 메타데이터 가져오기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78beb28f-408a-4c75-9c3c-caefe9595b1a
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c00368f466e151466bdf30a89dffe6baa9b57a33
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="importing-custom-metadata-for-a-wcf-extension"></a>WCF 확장에 대한 사용자 지정 메타데이터 가져오기
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 메타데이터 가져오기는 해당 메타데이터에서 서비스 또는 해당 구성 요소 부분의 추상적 표현을 생성하는 프로세스입니다. 예를 들면, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 <xref:System.ServiceModel.Description.ServiceEndpoint> 인스턴스, <xref:System.ServiceModel.Channels.Binding> 인스턴스 또는 <xref:System.ServiceModel.Description.ContractDescription> 인스턴스를 서비스의 WSDL 문서에서 가져올 수 있습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 서비스 메타데이터를 가져오려면 <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> 추상 클래스의 구현을 사용합니다. <xref:System.ServiceModel.Description.MetadataImporter> 클래스에서 파생되는 형식은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 WS-Policy 가져오기 논리를 사용하는 메타데이터 형식 가져오기에 대한 지원을 구현합니다.  
  
 사용자 지정 메타데이터는 시스템에서 제공한 메타데이터 가져오기에서 가져올 수 없는 XML 요소로 구성됩니다. 일반적으로 여기에 사용자 지정 WSDL 확장 및 사용자 지정 정책 어설션이 포함됩니다.  
  
 이 단원에서는 사용자 지정 WSDL 확장 및 정책 어설션을 가져오는 방법에 대해 설명합니다. 가져오기 프로세스 자체에 대해 중점적으로 설명하지는 않습니다. 내보내기 및 가져오기는 메타 데이터 또는 시스템에서 지 원하는 사용자 지정 인지에 관계 없이 메타 데이터 형식을 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [내보내기 및 가져오기는 메타 데이터](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)합니다.  
  
## <a name="overview"></a>개요  
 <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> 형식은 <xref:System.ServiceModel.Description.MetadataImporter>에 포함된 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 추상 클래스의 구현입니다. <xref:System.ServiceModel.Description.WsdlImporter> 형식은 <xref:System.ServiceModel.Description.MetadataSet?displayProperty=nameWithType> 개체에 번들로 제공되는 연결된 정책과 함께 WSDL 메타데이터를 가져옵니다. 기본 가져오기가 인식하지 않는 정책 어설션 및 WSDL 확장은 가져올 등록된 사용자 지정 정책 및 WSDL 가져오기로 전달됩니다. 일반적으로 가져오기는 사용자 정의 바인딩 요소를 지원하거나 가져온 계약을 수정하도록 구현됩니다.  
  
 이 단원의 내용은 다음과 같습니다.  
  
1.  설명과 코드를 생성하기 전에 WSDL 데이터를 사용자 지정 가져오기에 노출하는 <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> 인터페이스를 구현하고 사용하는 방법. 제공된 메타데이터 집합을 사용하면 수행된 설명 형식 및 코드 컴파일을 검사하거나 수정하는 데 이 인터페이스를 사용할 수 있습니다.  
  
2.  설명 개체를 생성하기 전에 정책 어설션을 가져오기에 노출하는 <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> 인터페이스를 구현하고 사용하는 방법. 다운로드된 정책을 기반으로 바인딩 또는 계약을 검사하거나 수정하는 데 이 인터페이스를 사용할 수 있습니다.  
  
 사용자 지정 WSDL 및 정책 어설션을 내보내기에 대 한 자세한 내용은 참조 [WCF 확장에 대 한 메타 데이터 사용자 지정 내보내기](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md)합니다.  
  
## <a name="importing-custom-wsdl-extensions"></a>사용자 지정 WSDL 확장명 가져오기  
 WSDL 확장 가져오기에 대한 지원을 추가하려면 <xref:System.ServiceModel.Description.IWsdlImportExtension> 인터페이스를 구현한 다음 구현 사항을 <xref:System.ServiceModel.Description.WsdlImporter.WsdlImportExtensions%2A> 속성에 추가합니다. <xref:System.ServiceModel.Description.WsdlImporter>에서 응용 프로그램 구성 파일에 등록된 <xref:System.ServiceModel.Description.IWsdlImportExtension> 인터페이스의 구현을 로드할 수도 있습니다. 기본적으로 여러 개의 WSDL 가져오기가 등록되며 등록된 WSDL 가져오기 순서가 중요합니다.  
  
 사용자 지정 WSDL 가져오기가 로드되고 <xref:System.ServiceModel.Description.WsdlImporter>에서 사용되는 경우 가져오기 프로세스 이전에 메타데이터 수정이 가능하도록 <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%2A> 메서드가 먼저 호출됩니다. 그런 다음 메타데이터에서 가져온 계약 수정 사항을 사용할 수 있도록 <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%2A> 메서드가 호출된 후에 계약을 가져옵니다. 마지막으로, 가져온 끝점의 수정 사항을 사용할 수 있도록 <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%2A> 메서드가 호출됩니다.  
  
 자세한 내용은 참조 [하는 방법: 사용자 지정 WSDL 가져오기](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md)합니다.  
  
### <a name="importing-custom-policy-assertions"></a>사용자 지정 정책 어설션 가져오기  
 <xref:System.ServiceModel.Description.WsdlImporter> 유형 및 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 다양 한 정책 어설션이 WSDL 문서에 연결 된 정책 식 형식 처리를 자동으로 처리 합니다. 이러한 도구는 WSDL 바인딩 및 WSDL 포트에 연결된 정책 식을 수집, 정규화 및 병합합니다.  
  
 사용자 지정 정책 어설션 가져오기에 대한 지원을 추가하려면 <xref:System.ServiceModel.Description.IPolicyImportExtension> 인터페이스를 구현한 다음 구현 사항을 <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A> 속성에 추가합니다. <xref:System.ServiceModel.Description.MetadataImporter>에서 응용 프로그램 구성 파일에 등록된 <xref:System.ServiceModel.Description.IPolicyImportExtension> 인터페이스의 구현을 로드할 수도 있습니다. 기본적으로 여러 개의 정책 가져오기가 등록되며 등록된 정책 가져오기 순서가 중요합니다.  
  
 메타데이터 시스템은 메시지, 작업 및 끝점 정책 주제에 연결된 정책 대안의 각 조합에 대해 등록된 모든 정책 가져오기 확장에서 <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType> 메서드를 반복해서 호출합니다. WSDL 포트를 가져올 때 해당 포트 및 해당 WSDL 바인딩에 연결된 정책은 정책 가져오기 확장을 호출하기 전에 병합됩니다. 정책 대안은 <xref:System.ServiceModel.Description.PolicyConversionContext>를 통해 <xref:System.ServiceModel.Description.PolicyAssertionCollection> 개체로 사용할 수 있습니다. 각 <xref:System.ServiceModel.Description.PolicyAssertionCollection>은 <xref:System.Xml.XmlElement> 개체로 나타낸 정책 어설션의 컬렉션입니다.  
  
 <xref:System.ServiceModel.Description.PolicyConversionContext.Contract%2A> 개체의 <xref:System.ServiceModel.Description.PolicyConversionContext.BindingElements%2A> 및 <xref:System.ServiceModel.Description.PolicyConversionContext> 속성은 WSDL에서 가져온 <xref:System.ServiceModel.Description.ContractDescription> 및 <xref:System.ServiceModel.Channels.BindingElement> 개체를 노출합니다. 정책 가져오기 확장은 특정 정책 어설션 형식의 인스턴스를 찾고, <xref:System.ServiceModel.Description.ContractDescription> 또는 <xref:System.ServiceModel.Channels.BindingElement> 개체를 변경한 다음 해당 <xref:System.ServiceModel.Description.PolicyAssertionCollection> 인스턴스에서 정책 어설션을 제거하여 정책 어설션을 처리합니다.  
  
 `wsp:Optional` 특성 및 중첩된 정책 식이 정규화되지 않으므로 정책 가져오기 확장이 이러한 정책 구성을 처리해야 합니다. 또한 같은 <xref:System.ServiceModel.Description.ContractDescription> 및 <xref:System.ServiceModel.Channels.BindingElement> 개체를 사용하여 정책 가져오기 확장을 여러 번 호출할 수 있으므로 정책 가져오기 확장은 이 동작을 보호할 수 있을 정도로 강력해야 합니다.  
  
> [!IMPORTANT]
>  잘못되었거나 부적절한 메타데이터를 가져오기로 전달할 수 없습니다. 사용자 지정 가져오기가 모든 형태의 XML을 보호할 수 있을 정도로 강력해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 사용자 지정 WSDL 가져오기](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md)  
 [방법: 사용자 지정 정책 어설션의 가져오기](../../../../docs/framework/wcf/extending/how-to-import-custom-policy-assertions.md)  
 [방법: ServiceContractGenerator에 대 한 확장을 작성 합니다.](../../../../docs/framework/wcf/extending/how-to-write-an-extension-for-the-servicecontractgenerator.md)
