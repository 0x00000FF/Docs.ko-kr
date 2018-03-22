---
title: '방법: 인증서의 지문 검색'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates [WCF], retrieving thumbprint
ms.assetid: da3101aa-78cd-4c34-9652-d1f24777eeab
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8f6d00d31023aa8d6dbfec4a8306f1cb9da17c74
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-retrieve-the-thumbprint-of-a-certificate"></a><span data-ttu-id="65918-102">방법: 인증서의 지문 검색</span><span class="sxs-lookup"><span data-stu-id="65918-102">How to: Retrieve the Thumbprint of a Certificate</span></span>
<span data-ttu-id="65918-103">인증에 X.509 인증서를 사용하는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 응용 프로그램을 작성하는 경우 인증서에 있는 클레임을 지정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65918-103">When writing a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application that uses an X.509 certificate for authentication, it is often necessary to specify claims found in the certificate.</span></span> <span data-ttu-id="65918-104">예를 들어 <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> 메서드에 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> 열거를 사용하는 경우 지문 클레임을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65918-104">For example, you must supply a thumbprint claim when using the <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> enumeration in the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method.</span></span> <span data-ttu-id="65918-105">클레임 값을 찾는 과정은 두 단계로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="65918-105">Finding the claim value requires two steps.</span></span> <span data-ttu-id="65918-106">첫째, 인증서에 대한 MMC(Microsoft Management Console) 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="65918-106">First, open the Microsoft Management Console (MMC) snap-in for certificates.</span></span> <span data-ttu-id="65918-107">[방법: MMC 스냅인을 사용하여 인증서 보기](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)를 참조하세요. 둘째, 여기서 설명하는 대로 적절한 인증서를 찾아 해당 지문(또는 다른 클레임 값)을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="65918-107">(See [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).) Second, as described here, find an appropriate certificate and copy its thumbprint (or other claim values).</span></span>  
  
 <span data-ttu-id="65918-108">서비스 인증에 인증서를 사용하는 경우 **발급 대상** 열(콘솔의 첫 번째 열)의 값을 확인하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="65918-108">If you are using a certificate for service authentication, it is important to note the value of the **Issued To** column (the first column in the console).</span></span> <span data-ttu-id="65918-109">SSL(Secure Sockets Layer)을 전송 보안으로 사용하는 경우 수행되는 첫 번째 확인 작업 중 하나는 서비스의 기본 주소 URI(Uniform Resource Identifier)를 **발급 대상** 값과 비교하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="65918-109">When using Secure Sockets Layer (SSL) as a transport security, one of the first checks done is to compare the base address Uniform Resource Identifier (URI) of a service to the **Issued To** value.</span></span> <span data-ttu-id="65918-110">값이 일치해야 하며, 그렇지 않으면 인증 프로세스가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="65918-110">The values must match or the authentication process is halted.</span></span>  
  
 <span data-ttu-id="65918-111">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] SDK의 Makecert.exe 도구를 사용하여 개발 중에만 사용할 임시 인증서를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65918-111">You can also use the Makecert.exe tool from the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] SDK to create temporary certificates for use only during development.</span></span> <span data-ttu-id="65918-112">그러나 이러한 인증서는 기본적으로 인증 기관에서 발급되지 않으며 프로덕션 목적으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65918-112">By default, however, such a certificate is not issued by a certification authority, and is unusable for production purposes.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="65918-113">[하는 방법: 개발 중 사용할 임시 인증서 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="65918-113"> [How to: Create Temporary Certificates for Use During Development](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md).</span></span>  
  
### <a name="to-retrieve-a-certificates-thumbprint"></a><span data-ttu-id="65918-114">인증서의 지문을 검색하려면</span><span class="sxs-lookup"><span data-stu-id="65918-114">To retrieve a certificate's thumbprint</span></span>  
  
1.  <span data-ttu-id="65918-115">인증서에 대한 MMC(Microsoft Management Console) 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="65918-115">Open the Microsoft Management Console (MMC) snap-in for certificates.</span></span> <span data-ttu-id="65918-116">[방법: MMC 스냅인을 사용하여 인증서 보기](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65918-116">(See [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).)</span></span>  
  
2.  <span data-ttu-id="65918-117">**콘솔 루트** 창의 왼쪽 창에서 **인증서(로컬 컴퓨터)**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65918-117">In the **Console Root** window's left pane, click **Certificates (Local Computer)**.</span></span>  
  
3.  <span data-ttu-id="65918-118">**개인** 폴더를 클릭하여 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="65918-118">Click the **Personal** folder to expand it.</span></span>  
  
4.  <span data-ttu-id="65918-119">**인증서** 폴더를 클릭하여 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="65918-119">Click the **Certificates** folder to expand it.</span></span>  
  
5.  <span data-ttu-id="65918-120">인증서 목록에서 **용도** 제목을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="65918-120">In the list of certificates, note the **Intended Purposes** heading.</span></span> <span data-ttu-id="65918-121">**클라이언트 인증** 을 용도로 표시하는 인증서를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="65918-121">Find a certificate that lists **Client Authentication** as an intended purpose.</span></span>  
  
6.  <span data-ttu-id="65918-122">인증서를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65918-122">Double-click the certificate.</span></span>  
  
7.  <span data-ttu-id="65918-123">**인증서** 대화 상자에서 **자세히** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65918-123">In the **Certificate** dialog box, click the **Details** tab.</span></span>  
  
8.  <span data-ttu-id="65918-124">필드 목록을 스크롤하여 **지문**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65918-124">Scroll through the list of fields and click **Thumbprint**.</span></span>  
  
9. <span data-ttu-id="65918-125">상자에서 16진수 문자를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="65918-125">Copy the hexadecimal characters from the box.</span></span> <span data-ttu-id="65918-126">`X509FindType`에 대한 코드에서 이 지문을 사용하는 경우 16진수 사이의 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="65918-126">If this thumbprint is used in code for the `X509FindType`, remove the spaces between the hexadecimal numbers.</span></span> <span data-ttu-id="65918-127">예를 들어 지문 "a9 09 50 2d d8 2a e4 14 33 e6 f8 38 86 b0 0d 42 77 a3 2a 7b"는 코드에서 "a909502dd82ae41433e6f83886b00d4277a32a7b"로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65918-127">For example, the thumbprint "a9 09 50 2d d8 2a e4 14 33 e6 f8 38 86 b0 0d 42 77 a3 2a 7b" should be specified as "a909502dd82ae41433e6f83886b00d4277a32a7b" in code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65918-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65918-128">See Also</span></span>  
 <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>  
 [<span data-ttu-id="65918-129">방법: SSL 인증서로 포트 구성</span><span class="sxs-lookup"><span data-stu-id="65918-129">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 [<span data-ttu-id="65918-130">방법: MMC 스냅인을 사용하여 인증서 보기</span><span class="sxs-lookup"><span data-stu-id="65918-130">How to: View Certificates with the MMC Snap-in</span></span>](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)  
 [<span data-ttu-id="65918-131">방법: 개발 중 사용할 임시 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="65918-131">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
