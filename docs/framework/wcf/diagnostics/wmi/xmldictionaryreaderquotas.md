---
title: XmlDictionaryReaderQuotas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06c0ff11752ae1030e574182cfb825fb87ddc8c7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="xmldictionaryreaderquotas"></a>XmlDictionaryReaderQuotas
XmlDictionaryReaderQuotas  
  
## <a name="syntax"></a>구문  
  
```  
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a>메서드  
 XmlDictionaryReaderQuotas 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  
 XmlDictionaryReaderQuotas 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="maxarraylength"></a>MaxArrayLength  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 허용된 최대 배열 길이입니다.  
  
### <a name="maxbytesperread"></a>MaxBytesPerRead  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 각 읽기에 대해 반환되는 최대 허용 바이트입니다.  
  
### <a name="maxdepth"></a>MaxDepth  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 각 읽기에 대한 최대 중첩 노드 깊이입니다.  
  
### <a name="maxnametablecharcount"></a>MaxNameTableCharCount  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 표 이름에 허용된 최대 문자 수입니다.  
  
### <a name="maxstringcontentlength"></a>MaxStringContentLength  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 XML 요소 콘텐츠에 허용되는 최대 문자 수입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
