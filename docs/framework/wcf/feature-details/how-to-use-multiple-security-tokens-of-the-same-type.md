---
title: '방법: 동일한 형식의 여러 보안 토큰 사용'
ms.date: 03/30/2017
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 25afbb268a0ef7772585a0f3829b56f135758b61
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45507419"
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="0cae4-102">방법: 동일한 형식의 여러 보안 토큰 사용</span><span class="sxs-lookup"><span data-stu-id="0cae4-102">How to: Use Multiple Security Tokens of the Same Type</span></span>
-   <span data-ttu-id="0cae4-103">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0의 경우 클라이언트 메시지에 지정된 형식의 토큰을 하나만 포함할 수 있었지만,</span><span class="sxs-lookup"><span data-stu-id="0cae4-103">In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0, a client message only contained one token of any given type.</span></span> <span data-ttu-id="0cae4-104">이제 클라이언트 메시지에 특정 형식의 여러 토큰을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cae4-104">Now client messages can contain multiple tokens of a type.</span></span> <span data-ttu-id="0cae4-105">이 항목에서는 동일한 형식의 토큰을 클라이언트 메시지에 여러 개 포함하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0cae4-105">This topic shows how to include multiple tokens of the same type in a client message.</span></span>  
  
-   <span data-ttu-id="0cae4-106">서비스는 이러한 방식으로 구성할 수 없습니다. 서비스는 지원하는 토큰을 하나만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cae4-106">Note that you cannot configure a service in this way: a service can contain only one supporting token.</span></span>  
  
### <a name="to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="0cae4-107">동일한 형식의 보안 토큰을 여러 개 사용하려면</span><span class="sxs-lookup"><span data-stu-id="0cae4-107">To use multiple security tokens of the same type</span></span>  
  
1.  <span data-ttu-id="0cae4-108">바인딩 요소로 채울 빈 바인딩 요소 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0cae4-108">Create an empty binding element collection to be populated.</span></span>  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2.  <span data-ttu-id="0cae4-109"><xref:System.ServiceModel.Channels.SecurityBindingElement>를 호출하여 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0cae4-109">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> by calling <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.</span></span>  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3.  <span data-ttu-id="0cae4-110"><xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters> 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0cae4-110">Create a <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters> collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4.  <span data-ttu-id="0cae4-111">컬렉션에 SAML 토큰을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0cae4-111">Add SAML tokens to the collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5.  <span data-ttu-id="0cae4-112"><xref:System.ServiceModel.Channels.SecurityBindingElement>에 컬렉션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0cae4-112">Add the collection to the <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span></span>  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6.  <span data-ttu-id="0cae4-113">바인딩 요소 컬렉션에 바인딩 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0cae4-113">Add binding elements to the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7.  <span data-ttu-id="0cae4-114">바인딩 요소 컬렉션에서 만들어진 새로운 사용자 지정 바인딩을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0cae4-114">Return a new custom binding created from the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## <a name="example"></a><span data-ttu-id="0cae4-115">예제</span><span class="sxs-lookup"><span data-stu-id="0cae4-115">Example</span></span>  
 <span data-ttu-id="0cae4-116">다음은 앞의 절차에서 설명한 전체 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="0cae4-116">The following is the entire method described by the preceding procedure.</span></span>  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
  
## <a name="see-also"></a><span data-ttu-id="0cae4-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0cae4-117">See Also</span></span>  
 [<span data-ttu-id="0cae4-118">보안 아키텍처</span><span class="sxs-lookup"><span data-stu-id="0cae4-118">Security Architecture</span></span>](https://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
