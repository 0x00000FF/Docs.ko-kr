---
title: '방법: HTTPS를 사용하여 신뢰할 수 있는 사용자 지정 세션 바인딩 만들기'
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: f39325829cf4b548482a6a570a5aa1fd65e61a1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62039535"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a>방법: HTTPS를 사용하여 신뢰할 수 있는 사용자 지정 세션 바인딩 만들기

이 항목에서는 신뢰할 수 있는 세션에 SSL(Secure Sockets Layer) 전송 보안을 사용하는 방법을 보여 줍니다. HTTPS를 통해 신뢰할 수 있는 세션을 사용하려면 신뢰할 수 있는 세션 및 HTTPS 전송을 사용하는 사용자 지정 바인딩을 만들어야 합니다. 구성 파일에서 코드를 사용 하 여 명령적으로 또는 선언적으로 신뢰할 수 있는 세션을 사용 합니다. 이 절차에서는 신뢰할 수 있는 세션을 사용 하도록 설정 하려면 클라이언트와 서비스 구성 파일을 사용 하며 [  **\<httpsTransport >** ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) 요소입니다.

이 절차의 핵심 부분을  **\<끝점 >** 구성 요소 포함을 `bindingConfiguration` 라는 사용자 지정 바인딩 구성을 참조 하는 특성 `reliableSessionOverHttps`. 합니다 [  **\<바인딩 >** ](../../../../docs/framework/misc/binding.md) 신뢰할 수 있는 세션 및 HTTPS 전송을 포함 하 여 사용 되도록 지정 하려면이 이름을 참조 하는 구성 요소  **\< reliableSession >** 하 고  **\<httpsTransport >** 요소입니다.

이 예제의 소스 복사에 대해서 [사용자 지정 바인딩 신뢰할 수 있는 세션 HTTPS 통한](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md)합니다.

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a>HTTPS를 사용 하 여 신뢰할 수 있는 세션을 사용 하려면 CustomBinding으로 서비스를 구성 합니다.

1. 서비스 유형에 대한 서비스 계약을 정의합니다.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. 서비스 클래스에 서비스 계약을 구현합니다. 서비스 구현 내 주소 또는 바인딩 정보는 지정 되지 note 합니다. 구성 파일에서 주소 또는 바인딩 정보를 검색 하는 코드를 작성 하는 데 필요한 아닙니다.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. 만들기는 *Web.config* 파일에 대 한 끝점을 구성 하는 `CalculatorService` 라는 사용자 지정 바인딩을 사용 하 여 `reliableSessionOverHttps` 신뢰할 수 있는 세션 및 HTTPS 전송을 사용 하는 합니다.

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. 만들기는 *Service.svc* 줄이 포함 된 파일:

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. 위치는 *Service.svc* 인터넷 정보 서비스 (IIS) 가상 디렉터리의 파일에에서 있습니다.

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a>HTTPS를 사용 하 여 신뢰할 수 있는 세션을 사용 하려면 CustomBinding으로 클라이언트를 구성 합니다.

1. 사용 된 [ServiceModel Metadata 유틸리티 도구 (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 서비스 메타 데이터에서 코드를 생성 하려면 명령줄에서.

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. 생성 되는 클라이언트 포함 된 `ICalculator` 클라이언트 구현에서 충족 해야 하는 서비스 계약을 정의 하는 인터페이스입니다.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. 또한 생성된 클라이언트 응용 프로그램에는 `ClientCalculator`의 구현이 포함되어 있습니다. 서비스 구현 내 주소 및 바인딩 정보는 지정 되지 참고 합니다. 구성 파일에서 주소 및 바인딩 정보를 검색 하는 코드를 작성 하는 데 필요한 아닙니다.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. 명명 된 사용자 지정 바인딩을 구성 `reliableSessionOverHttps` 신뢰할 수 있는 세션 및 HTTPS 전송을 사용 하도록 합니다.

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. 응용 프로그램에서 `ClientCalculator`의 인스턴스를 만든 다음 서비스 작업을 호출합니다.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. 클라이언트를 컴파일하고 실행합니다.  

## <a name="net-framework-security"></a>.NET Framework 보안

이 샘플에 사용 된 인증서 사용 하 여 만든 테스트 인증서 이므로 *Makecert.exe*와 같은 HTTPS 주소에 액세스 하려고 할 때 보안 경고가 나타납니다 `https://localhost/servicemodelsamples/service.svc`, 브라우저에서 합니다.

## <a name="see-also"></a>참고자료

- [신뢰할 수 있는 세션](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
