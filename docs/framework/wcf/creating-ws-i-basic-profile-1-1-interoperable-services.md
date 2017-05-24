---
title: "WS-I Basic Profile 1.1 상호 운용할 수 있는 서비스 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "구성 [WCF], 상호 운용 가능 서비스"
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# WS-I Basic Profile 1.1 상호 운용할 수 있는 서비스 만들기
[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 끝점을 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 웹 서비스 클라이언트와 상호 운용할 수 있도록 구성하려면  
  
-   사용 하 여 <xref:System.ServiceModel.BasicHttpBinding?displayProperty=fullName> 형식을 서비스 끝점에 대 한 바인딩 형식으로.  
  
-   서비스 끝점에서 콜백 및 세션 계약 기능이나 트랜잭션 동작을 사용하면 안 됩니다.  
  
 바인딩에서 HTTPS 및 전송 수준 클라이언트 인증에 대한 지원을 선택적으로 사용할 수 있습니다.  
  
 다음 기능은 <xref:System.ServiceModel.BasicHttpBinding> 클래스 WS 이상의 기능이 필요-Basic Profile 1.1.  
  
-   에 의해 제어 메시지 전송 최적화 메커니즘 (MTOM) 메시지 인코딩는 <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=fullName> 속성입니다. 이 속성의 기본값을 그대로 두고 <xref:System.ServiceModel.WSMessageEncoding?displayProperty=fullName> MTOM을 사용 하지 않도록 합니다.  
  
-   메시지 보안에 의해 제어는 <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=fullName> 값은 호환 WS 보안 지원 제공-기본 보안 프로필 1.0입니다. 이 속성의 기본값을 그대로 두고 <xref:System.ServiceModel.SecurityMode?displayProperty=fullName> Ws-security를 사용 하지 않도록 합니다.  
  
 메타 데이터에 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 사용할 수 있는 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], 웹 서비스 클라이언트 생성 도구를 사용 하 여: [웹 서비스 설명 언어 도구 (Wsdl.exe)](http://msdn.microsoft.com/ko-kr/b9210348-8bc2-4367-8c91-d1a04b403e88), [웹 서비스 검색 도구 (Disco.exe)](http://msdn.microsoft.com/ko-kr/acd88078-c581-42bc-94ca-6633e2851979), 및 `Add Web Reference` 기능을 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]; 메타 데이터 게시를 사용 하도록 설정 해야 합니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][메타 데이터 끝점 게시](../../../docs/framework/wcf/publishing-metadata-endpoints.md)합니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제 코드에서는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 웹 서비스 클라이언트와 호환되는 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 끝점을 코드 또는 구성 파일에 추가하는 방법에 대해 보여 줍니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
  
 <!-- TODO: review snippet reference [!code[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/common/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  -->  
  
## <a name="see-also"></a>참고 항목  
 [ASP.NET 웹 서비스와의 상호 운용성](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)