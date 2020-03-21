---
title: WebContentTypeMapper 샘플
ms.date: 03/30/2017
ms.assetid: a4fe59e7-44d8-43c6-a1f8-40c45223adca
ms.openlocfilehash: 540e5e775cf7b2a5a5b585d98772415653fa833a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143566"
---
# <a name="webcontenttypemapper-sample"></a>WebContentTypeMapper 샘플
이 샘플에서는 새 콘텐츠 형식을 WCF(Windows 통신 Foundation) 메시지 본문 형식에 매핑하는 방법을 보여 줍니다.  
  
 이 <xref:System.ServiceModel.Description.WebHttpEndpoint> 요소는 웹 메시지 인코더에 연결되어 WCF가 동일한 끝점에서 JSON, XML 또는 원시 이진 메시지를 수신할 수 있습니다. 인코더는 요청의 HTTP 콘텐츠 형식을 확인하여 메시지의 본문 형식을 확인합니다. 이 샘플에서는 콘텐츠 형식과 본문 형식 간의 매핑을 사용자가 제어할 수 있게 하는 <xref:System.ServiceModel.Channels.WebContentTypeMapper> 클래스를 소개합니다.  
  
 WCF는 콘텐츠 형식에 대한 기본 매핑 집합을 제공합니다. 예를 들어, `application/json`은  JSON에 매핑되고 `text/xml`은 XML에 매핑됩니다. JSON 또는 XML에 매핑되지 않는 모든 콘텐츠 형식은 원시 이진 형식에 매핑됩니다.  
  
 푸시 스타일 API와 같은 일부 시나리오에서 서비스 개발자는 클라이언트가 반환하는 콘텐츠 형식을 제어하지 않습니다. 예를 들어, 클라이언트가 JSON을 `text/javascript` 대신에 `application/json`로 반환할 수 있습니다. 이 경우 서비스 개발자는 다음 샘플 코드와 같이 지정된 콘텐츠 형식을 올바르게 처리하기 위해 <xref:System.ServiceModel.Channels.WebContentTypeMapper>에서 파생되는 형식을 제공해야 합니다.  
  
```csharp  
public class JsonContentTypeMapper : WebContentTypeMapper  
{  
    public override WebContentFormat  
               GetMessageFormatForContentType(string contentType)  
    {  
        if (contentType == "text/javascript")  
        {  
            return WebContentFormat.Json;  
        }  
        else  
        {  
            return WebContentFormat.Default;  
        }  
    }  
}  
```  
  
 이 형식은 <xref:System.ServiceModel.Channels.WebContentTypeMapper.GetMessageFormatForContentType%28System.String%29> 메서드를 재정의해야 합니다. 이 메서드는 `contentType` 인수를 평가하고 <xref:System.ServiceModel.Channels.WebContentFormat.Json>, <xref:System.ServiceModel.Channels.WebContentFormat.Xml>, <xref:System.ServiceModel.Channels.WebContentFormat.Raw> 또는 <xref:System.ServiceModel.Channels.WebContentFormat.Default> 값 중 하나를 반환해야 합니다. <xref:System.ServiceModel.Channels.WebContentFormat.Default> 반환은 기본 웹 메시지 인코더 매핑을 따릅니다. 위의 샘플 코드에서 `text/javascript` 콘텐츠 형식은 JSON에 매핑되고 다른 모든 매핑은 변경되지 않은 상태로 유지됩니다.  
  
 `JsonContentTypeMapper` 클래스를 사용하여 Web.config에서 다음을 사용합니다.  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <standardEndpoint name="" contentTypeMapper="Microsoft.Samples.WebContentTypeMapper.JsonContentTypeMapper, JsonContentTypeMapper, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 JsonContentTypeMapper 사용을 위한 요구 사항을 확인하려면 위의 구성 파일에서 contentTypeMapper 특성을 제거합니다. 그러면 `text/javascript`를 사용하여 JSON 콘텐츠를 보내려고 할 때 클라이언트 페이지를 로드하는 데 실패합니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1. Windows 통신 기초 [샘플에 대한 일회성 설치 절차를](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)수행했어야 합니다.  
  
2. Windows 통신 기초 샘플 빌드에 설명된 대로 솔루션 WebContentTypeMapperSample.sln을 [빌드합니다.](../../../../docs/framework/wcf/samples/building-the-samples.md)  
  
3. 로 `http://localhost/ServiceModelSamples/JCTMClientPage.htm` 이동합니다(프로젝트 디렉터리 내에서 브라우저에서 JCTMClientPage.htm을 열지 마십시오).  
  
> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다. 이 샘플은 다음 디렉터리에 있습니다.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Ajax\WebContentTypeMapper`  
