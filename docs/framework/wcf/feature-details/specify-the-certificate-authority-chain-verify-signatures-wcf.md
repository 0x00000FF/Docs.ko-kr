---
title: '방법: (WCF) 서명을 확인 하는 데 인증서 기관 인증서 체인 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], specifying the certificate authority certificate chain
- certificates [WCF], verifying signatures
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
ms.openlocfilehash: 43296fad9519a08db5facdd220492ac70dffeca2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224484"
---
# <a name="how-to-specify-the-certificate-authority-certificate-chain-used-to-verify-signatures-wcf"></a><span data-ttu-id="59ba9-102">방법: (WCF) 서명을 확인 하는 데 인증서 기관 인증서 체인 지정</span><span class="sxs-lookup"><span data-stu-id="59ba9-102">How to: Specify the Certificate Authority Certificate Chain Used to Verify Signatures (WCF)</span></span>
<span data-ttu-id="59ba9-103">Windows Communication Foundation (WCF)는 X.509 인증서를 사용 하 여 서명 된 SOAP 메시지를 받으면 기본적으로 확인 신뢰할 수 있는 인증 기관에서 X.509 인증서를 발행 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="59ba9-103">When Windows Communication Foundation (WCF) receives a SOAP message signed using an X.509 certificate, by default it verifies that the X.509 certificate was issued by a trusted certification authority.</span></span> <span data-ttu-id="59ba9-104">이렇게 하려면 인증서 저장소를 찾고 해당 인증 기관의 인증서가 신뢰할 수 있는 것으로 지정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="59ba9-104">This is done by looking in a certificate store and determining if the certificate for that certification authority has been designated as trusted.</span></span> <span data-ttu-id="59ba9-105">이 확인 하기 위해 WCF에 대 한 순서로 인증 기관 인증서 체인을 올바른 인증서 저장소에 설치 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59ba9-105">In order for WCF to make this determination, the certification authority certificate chain must be installed in the correct certificate store.</span></span>  
  
### <a name="to-install-a-certification-authority-certificate-chain"></a><span data-ttu-id="59ba9-106">인증 기관 인증서 체인을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="59ba9-106">To install a certification authority certificate chain</span></span>  
  
-   <span data-ttu-id="59ba9-107">SOAP 메시지 받는 사람이 신뢰 하는 각 인증 기관에서 발급 된 X.509 인증서 WCF에서 X.509 인증서를 검색 하도록 구성 되어 있는지를 인증서 저장소로 인증 기관 인증서 체인을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="59ba9-107">For each certification authority that a SOAP message recipient intends to trust X.509 certificates issued from, install the certification authority certificate chain into the certificate store that WCF is configured to retrieve X.509 certificates from.</span></span>  
  
     <span data-ttu-id="59ba9-108">예를 들어, SOAP 메시지 받는 사람이 Microsoft에서 발급 한 X.509 인증서를 신뢰 하는, microsoft 인증 기관 인증서 체인을 WCF에서 X.509 인증서를 검색할 수 있도록 설정 되어 있는 인증서 저장소에 설치 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59ba9-108">For instance, if a SOAP message recipient intends to trust X.509 certificates issued by Microsoft, the certification authority certificate chain for Microsoft must be installed in the certificate store that WCF is set up to look for X.509 certificates from.</span></span> <span data-ttu-id="59ba9-109">코드 또는 구성에는 WCF는 X.509 인증서를 찾습니다 인증서 저장소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59ba9-109">The certificate store in which WCF looks for X.509 certificates can be specified in code or configuration.</span></span> <span data-ttu-id="59ba9-110">예를 들어, 다음을 사용 하 여 코드에서 지정할 수 있습니다 합니다 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> 메서드 또는 구성 등의 몇 가지 방법으로 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="59ba9-110">For example, this can be specified in code using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method or in configuration a few ways, including the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .</span></span>  
  
     <span data-ttu-id="59ba9-111">Windows는 신뢰할 수 있는 인증 기관에 대한 기본 인증서 체인 집합이 함께 제공되므로 모든 인증 기관에 대한 인증서 체인을 반드시 설치할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59ba9-111">Because Windows ships with a set of default certificate chains for trusted certificate authorities, it may not be necessary to install the certificate chain for all certificate authorities.</span></span>  
  
    1.  <span data-ttu-id="59ba9-112">인증 기관 인증서 체인을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="59ba9-112">Export the certification authority certificate chain.</span></span>  
  
         <span data-ttu-id="59ba9-113">이 작업을 수행하는 방법은 인증 기관에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="59ba9-113">Exactly how this is done depends on the certification authority.</span></span> <span data-ttu-id="59ba9-114">인증 기관 Microsoft 인증서 서비스를 실행 하는 경우 **CA 인증서, 인증서 체인 또는 CRL 다운로드**를 선택한 후 **CA 인증서 다운로드**합니다.</span><span class="sxs-lookup"><span data-stu-id="59ba9-114">If the certification authority is running Microsoft Certificate Services, select **Download a CA certificate, certificate chain, or CRL**, and then choose **Download CA certificate**.</span></span>  
  
    2.  <span data-ttu-id="59ba9-115">인증 기관 인증서 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="59ba9-115">Import the certification authority certificate chain.</span></span>  
  
         <span data-ttu-id="59ba9-116">MMC(Microsoft Management Console)에서 인증서 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="59ba9-116">In the Microsoft Management Console (MMC), open the Certificates snap-in.</span></span> <span data-ttu-id="59ba9-117">선택에서 X.509 인증서를 검색 하도록 구성 된 해당 WCF의 인증서 저장소를 **신뢰할 수 있는 루트** **인증 기관** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="59ba9-117">For the certificate store that WCF is configured to retrieve X.509 certificates from, select the **Trusted Root** **Certification Authorities** folder.</span></span> <span data-ttu-id="59ba9-118">아래는 **신뢰할 수 있는 루트 인증 기관** 폴더를 마우스 오른쪽 단추로 클릭 합니다 **인증서** 폴더를 가리킵니다 **모든 작업**를 클릭 하 고 **가져오기** .</span><span class="sxs-lookup"><span data-stu-id="59ba9-118">Under the **Trusted Root Certification Authorities** folder, right-click the **Certificates** folder, point to **All Tasks**, and then click **Import**.</span></span> <span data-ttu-id="59ba9-119">a 단계에서 내보낸 파일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="59ba9-119">Provide the file exported in step a.</span></span>  
  
         <span data-ttu-id="59ba9-120">MMC 인증서 스냅인을 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: MMC 스냅인을 사용 하 여 인증서 보기](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="59ba9-120">For more information about using the Certificates snap-in with MMC, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59ba9-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="59ba9-121">See also</span></span>

- [<span data-ttu-id="59ba9-122">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="59ba9-122">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
