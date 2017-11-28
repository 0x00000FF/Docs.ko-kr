---
title: "메타데이터 형식"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d250b57282d24780dcdd1e045f18d7528bd86a90
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="metadata-formats"></a>메타데이터 형식
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서는 다음 표의 메타데이터 형식을 지원합니다.  
  
## <a name="metadata-specifications-and-usage"></a>메타데이터 사양 및 사용  
  
|프로토콜|사양 및 사용|  
|--------------|-----------------------------|  
|WSDL 1.1|[웹 서비스 기술 언어 (WSDL) 1.1](http://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 WSDL(웹 서비스 기술 언어)을 사용하여 서비스를 설명합니다.|  
|XML 스키마|[XML 스키마 2 부: Datatypes Second Edition](http://go.microsoft.com/fwlink/?LinkId=94861) 및 [XML 스키마 1 부: 구조 Second Edition](http://go.microsoft.com/fwlink/?LinkId=94862)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 XML 스키마를 사용하여 메시지에 사용되는 데이터 형식에 대해 설명합니다.|  
|WS Policy|[웹 서비스 정책 1.2-프레임 워크 (Ws-policy)](http://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [웹 서비스 정책 1.5-프레임 워크](http://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 WS-Policy 1.2 또는 1.5 사양을 도메인별 어설션과 함께 사용하여 서비스 요구 사항 및 기능에 대해 설명합니다.|  
|WS Policy 첨부 파일|[웹 서비스 정책 1.2-첨부 파일 (Ws-policyattachment)](http://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 WS-Policy 첨부 파일을 구현하여 WSDL에서 다양한 범위의 정책 식을 연결합니다.|  
|WS Metadata Exchange|[웹 서비스 메타 데이터 교환 (Ws-metadataexchange) 버전 1.1](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 WS-MetadataExchange를 구현하여 XML 스키마, WSDL 및 WS-Policy를 검색합니다.|  
|WSDL에 대한 WS-Addressing 바인딩|[Web Services Addressing 1.0-WSDL 바인딩](http://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 WSDL에 대한 WS-Addressing 바인딩을 구현하여 WSDL에서 주소 지정 정보를 연결합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [웹 서비스 시스템 제공 상호 운용성 바인딩에서 지 원하는 프로토콜](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
 [WSDL 및 정책](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
