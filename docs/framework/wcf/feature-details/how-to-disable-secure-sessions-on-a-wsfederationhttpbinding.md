---
title: '방법: WSFederationHttpBinding에서 보안 세션을 사용하지 않도록 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 675fa143-6a4e-4be3-8afc-673334ab55ec
author: BrucePerlerMS
ms.openlocfilehash: e81469f5ac55b1c698dc99af0782dbdedab33339
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48793151"
---
# <a name="how-to-disable-secure-sessions-on-a-wsfederationhttpbinding"></a><span data-ttu-id="ceb28-102">방법: WSFederationHttpBinding에서 보안 세션을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="ceb28-102">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>
<span data-ttu-id="ceb28-103">일부 서비스에서 페더레이션 자격 증명을 필요로 하지만 보안 세션을 지원하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ceb28-103">Some services may require federated credentials but not support secure sessions.</span></span> <span data-ttu-id="ceb28-104">이 경우 보안 세션 기능을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb28-104">In that case, you must disable the secure session feature.</span></span> <span data-ttu-id="ceb28-105">달리는 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>, <xref:System.ServiceModel.WSFederationHttpBinding> 클래스 보안 세션을 사용 하지 않도록 설정 하는 방법을 제공 하지 않습니다 서비스와 통신 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="ceb28-105">Unlike the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>, the <xref:System.ServiceModel.WSFederationHttpBinding> class does not provide a way to disable secure sessions when communicating with a service.</span></span> <span data-ttu-id="ceb28-106">대신 보안 세션 설정을 부트스트랩으로 대체하는 사용자 지정 바인딩을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb28-106">Instead, you must create a custom binding that replaces the secure session settings with a bootstrap.</span></span>  
  
 <span data-ttu-id="ceb28-107">이 항목에서는 <xref:System.ServiceModel.WSFederationHttpBinding>에 포함된 바인딩 요소를 수정하여 사용자 지정 바인딩을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ceb28-107">This topic demonstrates how to modify the binding elements contained within a <xref:System.ServiceModel.WSFederationHttpBinding> to create a custom binding.</span></span> <span data-ttu-id="ceb28-108">보안 세션을 사용하지 않는 점만 제외하고 결과는 <xref:System.ServiceModel.WSFederationHttpBinding>과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb28-108">The result is identical to the <xref:System.ServiceModel.WSFederationHttpBinding> except that it does not use secure sessions.</span></span>  
  
### <a name="to-create-a-custom-federated-binding-without-secure-session"></a><span data-ttu-id="ceb28-109">보안 세션을 사용하지 않고 사용자 지정 페더레이션 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="ceb28-109">To create a custom federated binding without secure session</span></span>  
  
1.  <span data-ttu-id="ceb28-110">구성 파일에서 로드하거나 코드에서 명령적으로 <xref:System.ServiceModel.WSFederationHttpBinding> 클래스 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ceb28-110">Create an instance of the <xref:System.ServiceModel.WSFederationHttpBinding> class either imperatively in code or by loading one from the configuration file.</span></span>  
  
2.  <span data-ttu-id="ceb28-111"><xref:System.ServiceModel.WSFederationHttpBinding>을 <xref:System.ServiceModel.Channels.CustomBinding>으로 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb28-111">Clone the <xref:System.ServiceModel.WSFederationHttpBinding> into a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
3.  <span data-ttu-id="ceb28-112"><xref:System.ServiceModel.Channels.SecurityBindingElement>에서 <xref:System.ServiceModel.Channels.CustomBinding>를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ceb28-112">Find the <xref:System.ServiceModel.Channels.SecurityBindingElement> in the <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
4.  <span data-ttu-id="ceb28-113"><xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>에서 <xref:System.ServiceModel.Channels.SecurityBindingElement>를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ceb28-113">Find the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters> in the <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span></span>  
  
5.  <span data-ttu-id="ceb28-114">원래 <xref:System.ServiceModel.Channels.SecurityBindingElement>를 <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>의 부트스트랩 보안 바인딩 요소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ceb28-114">Replace the original <xref:System.ServiceModel.Channels.SecurityBindingElement> with the bootstrap security binding element from the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ceb28-115">예제</span><span class="sxs-lookup"><span data-stu-id="ceb28-115">Example</span></span>  
 <span data-ttu-id="ceb28-116">다음 예제에서는 보안 세션을 사용하지 않고 사용자 지정 페더레이션 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ceb28-116">This following example creates a custom federated binding without secure session.</span></span>  
  
 [!code-csharp[c_CustomFederationBinding#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customfederationbinding/cs/c_customfederationbinding.cs#0)]
 [!code-vb[c_CustomFederationBinding#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customfederationbinding/vb/c_customfederationbinding.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ceb28-117">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ceb28-117">Compiling the Code</span></span>  
  
-   <span data-ttu-id="ceb28-118">코드 예제를 컴파일하려면 System.ServiceModel.dll 어셈블리를 참조하는 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ceb28-118">To compile the code example, create a project that references the System.ServiceModel.dll assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceb28-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ceb28-119">See Also</span></span>  
 [<span data-ttu-id="ceb28-120">바인딩 및 보안</span><span class="sxs-lookup"><span data-stu-id="ceb28-120">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
