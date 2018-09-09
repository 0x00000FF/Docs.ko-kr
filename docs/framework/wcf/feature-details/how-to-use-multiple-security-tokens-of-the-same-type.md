---
title: '방법: 동일한 형식의 여러 보안 토큰 사용'
ms.date: 03/30/2017
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 25afbb268a0ef7772585a0f3829b56f135758b61
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44225635"
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a>방법: 동일한 형식의 여러 보안 토큰 사용
-   [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0의 경우 클라이언트 메시지에 지정된 형식의 토큰을 하나만 포함할 수 있었지만, 이제 클라이언트 메시지에 특정 형식의 여러 토큰을 포함할 수 있습니다. 이 항목에서는 동일한 형식의 토큰을 클라이언트 메시지에 여러 개 포함하는 방법을 보여 줍니다.  
  
-   서비스는 이러한 방식으로 구성할 수 없습니다. 서비스는 지원하는 토큰을 하나만 포함할 수 있습니다.  
  
### <a name="to-use-multiple-security-tokens-of-the-same-type"></a>동일한 형식의 보안 토큰을 여러 개 사용하려면  
  
1.  바인딩 요소로 채울 빈 바인딩 요소 컬렉션을 만듭니다.  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2.  <xref:System.ServiceModel.Channels.SecurityBindingElement>를 호출하여 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>를 만듭니다.  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3.  <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters> 컬렉션을 만듭니다.  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4.  컬렉션에 SAML 토큰을 추가합니다.  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5.  <xref:System.ServiceModel.Channels.SecurityBindingElement>에 컬렉션을 추가합니다.  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6.  바인딩 요소 컬렉션에 바인딩 요소를 추가합니다.  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7.  바인딩 요소 컬렉션에서 만들어진 새로운 사용자 지정 바인딩을 반환합니다.  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## <a name="example"></a>예제  
 다음은 앞의 절차에서 설명한 전체 메서드입니다.  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
  
## <a name="see-also"></a>참고 항목  
 [보안 아키텍처](https://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
