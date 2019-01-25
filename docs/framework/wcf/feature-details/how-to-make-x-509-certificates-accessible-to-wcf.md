---
title: '방법: X.509 인증서를 WCF에 액세스할 수 있도록 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- X.509 certificates [WCF]
- certificates [WCF], making X.509 certificates accessible to WCF
- X.509 certificates [WCF], making accessible to WCF
ms.assetid: a54e407c-c2b5-4319-a648-60e43413664b
ms.openlocfilehash: 7c90d5b0541edfc11145d9373c2554ee4595a7b1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741885"
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="bc9cb-102">방법: X.509 인증서를 WCF에 액세스할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="bc9cb-102">How to: Make X.509 Certificates Accessible to WCF</span></span>
<span data-ttu-id="bc9cb-103">X.509 인증서에 Windows Communication Foundation (WCF)에 액세스할 수 있도록 하려면 응용 프로그램 코드에는 인증서 저장소 이름 및 위치를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-103">To make an X.509 certificate accessible to Windows Communication Foundation (WCF), application code must specify the certificate store name and location.</span></span> <span data-ttu-id="bc9cb-104">상황에 따라, X.509 인증서와 연결된 개인 키를 포함하는 파일에 대한 액세스가 프로세스 ID에 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-104">In certain circumstances, the process identity must have access to the file that contains the private key associated with the X.509 certificate.</span></span> <span data-ttu-id="bc9cb-105">인증서 저장소에서 X.509 인증서와 연결 된 개인 키를 가져오려면 WCF 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-105">To obtain the private key associated with an X.509 certificate in a certificate store, WCF must have permission to do so.</span></span> <span data-ttu-id="bc9cb-106">기본적으로 소유자와 시스템 계정에서만 인증서의 개인 키에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-106">By default, only the owner and the System account can access the private key of a certificate.</span></span>  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="bc9cb-107">WCF에서 X.509 인증서에 액세스할 수 있도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="bc9cb-107">To make X.509 certificates accessible to WCF</span></span>  
  
1.  <span data-ttu-id="bc9cb-108">실행 계정에는 WCF는 읽기 액세스 X.509 인증서와 연결 된 개인 키가 포함 된 파일을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-108">Give the account under which WCF is running read access to the file that contains the private key associated with the X.509 certificate.</span></span>  
  
    1.  <span data-ttu-id="bc9cb-109">WCF X.509 인증서의 개인 키에 대 한 읽기 액세스를 해야 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-109">Determine whether WCF requires read access to the private key for the X.509 certificate.</span></span>  
  
         <span data-ttu-id="bc9cb-110">다음 표에는 X.509 인증서를 사용하는 경우 개인 키를 사용할 수 있어야 하는지 여부가 자세히 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-110">The following table details whether a private key must be available when using an X.509 certificate.</span></span>  
  
        |<span data-ttu-id="bc9cb-111">X.509 인증서 사용</span><span class="sxs-lookup"><span data-stu-id="bc9cb-111">X.509 certificate use</span></span>|<span data-ttu-id="bc9cb-112">개인 키</span><span class="sxs-lookup"><span data-stu-id="bc9cb-112">Private key</span></span>|  
        |---------------------------|-----------------|  
        |<span data-ttu-id="bc9cb-113">아웃바운드 SOAP 메시지 디지털 서명.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-113">Digitally signing an outbound SOAP message.</span></span>|<span data-ttu-id="bc9cb-114">예</span><span class="sxs-lookup"><span data-stu-id="bc9cb-114">Yes</span></span>|  
        |<span data-ttu-id="bc9cb-115">인바운드 SOAP 메시지 서명 확인.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-115">Verifying the signature of an inbound SOAP message.</span></span>|<span data-ttu-id="bc9cb-116">아니요</span><span class="sxs-lookup"><span data-stu-id="bc9cb-116">No</span></span>|  
        |<span data-ttu-id="bc9cb-117">아웃바운드 SOAP 메시지 암호화.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-117">Encrypting an outbound SOAP message.</span></span>|<span data-ttu-id="bc9cb-118">아니요</span><span class="sxs-lookup"><span data-stu-id="bc9cb-118">No</span></span>|  
        |<span data-ttu-id="bc9cb-119">인바운드 SOAP 메시지 암호 해독.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-119">Decrypting an inbound SOAP message.</span></span>|<span data-ttu-id="bc9cb-120">예</span><span class="sxs-lookup"><span data-stu-id="bc9cb-120">Yes</span></span>|  
  
    2.  <span data-ttu-id="bc9cb-121">인증서가 저장되는 인증서 저장소 위치와 이름을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-121">Determine the certificate store location and name in which the certificate is stored.</span></span>  
  
         <span data-ttu-id="bc9cb-122">인증서가 저장되는 인증서 저장소는 응용 프로그램 코드 또는 구성에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-122">The certificate store in which the certificate is stored is specified either in application code or in configuration.</span></span> <span data-ttu-id="bc9cb-123">예를 들어, 다음 예에서는 인증서 위치를 이름이 `CurrentUser`인 `My` 인증서 저장소로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-123">For example, the following example specifies that the certificate is located in the `CurrentUser` certificate store named `My`.</span></span>  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3.  <span data-ttu-id="bc9cb-124">사용 하 여 인증서의 개인 키를 컴퓨터에 있는 위치를 확인 합니다 [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-124">Determine where the private key for the certificate is located on the computer by using the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool.</span></span>  
  
         <span data-ttu-id="bc9cb-125">합니다 [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) 도구에 필요한 인증서 저장소 이름, 인증서 저장소 위치 및 인증서를 고유 하 게 식별 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-125">The [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool requires the certificate store name, certificate store location, and something that uniquely identifies the certificate.</span></span> <span data-ttu-id="bc9cb-126">도구에서는 인증서의 제목 이름이나 지문을 고유 식별자로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-126">The tool accepts either the certificate's subject name or its thumbprint as a unique identifier.</span></span> <span data-ttu-id="bc9cb-127">인증서의 지문을 확인 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 인증서의 지문 검색](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-127">For more information about how to determine the thumbprint for a certificate, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
         <span data-ttu-id="bc9cb-128">다음 코드 예제에서는 합니다 [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) 인증서의 개인 키의 위치를 결정 하는 도구를 `My` 에 저장 `CurrentUser` 지문이 있는 `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-128">The following code example uses the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool to determine the location of the private key for a certificate in the `My` store in `CurrentUser` with a thumbprint of `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span></span>  
  
        ```  
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4.  <span data-ttu-id="bc9cb-129">WCF에서 실행 되는 계정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-129">Determine the account that WCF is running under.</span></span>  
  
         <span data-ttu-id="bc9cb-130">다음 표에서 실행 계정에는 WCF는 지정된 된 시나리오에 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-130">The following table details the account under which WCF is running for a given scenario.</span></span>  
  
        |<span data-ttu-id="bc9cb-131">시나리오</span><span class="sxs-lookup"><span data-stu-id="bc9cb-131">Scenario</span></span>|<span data-ttu-id="bc9cb-132">프로세스 ID</span><span class="sxs-lookup"><span data-stu-id="bc9cb-132">Process identity</span></span>|  
        |--------------|----------------------|  
        |<span data-ttu-id="bc9cb-133">클라이언트(콘솔 또는 WinForms 응용 프로그램).</span><span class="sxs-lookup"><span data-stu-id="bc9cb-133">Client (console or WinForms application).</span></span>|<span data-ttu-id="bc9cb-134">현재 로그인한 사용자.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-134">Currently logged in user.</span></span>|  
        |<span data-ttu-id="bc9cb-135">자체 호스팅된 서비스.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-135">Service that is self-hosted.</span></span>|<span data-ttu-id="bc9cb-136">현재 로그인한 사용자.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-136">Currently logged in user.</span></span>|  
        |<span data-ttu-id="bc9cb-137">IIS 6.0([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) 또는 IIS 7.0([!INCLUDE[wv](../../../../includes/wv-md.md)])에서 호스팅되는 서비스.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-137">Service that is hosted in IIS 6.0 ([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) or IIS 7.0 ([!INCLUDE[wv](../../../../includes/wv-md.md)]).</span></span>|<span data-ttu-id="bc9cb-138">NETWORK SERVICE</span><span class="sxs-lookup"><span data-stu-id="bc9cb-138">NETWORK SERVICE</span></span>|  
        |<span data-ttu-id="bc9cb-139">IIS 5.X([!INCLUDE[wxp](../../../../includes/wxp-md.md)])에서 호스팅되는 서비스.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-139">Service that is hosted in IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]).</span></span>|<span data-ttu-id="bc9cb-140">Machine.config 파일의 `<processModel>` 요소로 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-140">Controlled by the `<processModel>` element in the Machine.config file.</span></span> <span data-ttu-id="bc9cb-141">기본 계정은 ASPNET입니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-141">The default account is ASPNET.</span></span>|  
  
    5.  <span data-ttu-id="bc9cb-142">Icacls.exe와 같은 도구를 사용 하 여 WCF에서를 실행 중인 계정에 개인 키를 포함 하는 파일에 대 한 읽기 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-142">Grant read access to the file that contains the private key to the account that WCF is running under, using a tool such as icacls.exe.</span></span>  
  
         <span data-ttu-id="bc9cb-143">다음 코드 예제에서는 네트워크 서비스 계정 읽기 권한을 부여 하려면 지정된 된 파일에 대 한 임의 액세스 제어 목록 (DACL) 편집 (: R) 파일에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9cb-143">The following code example edits the discretionary access control list (DACL) for the specified file to grant the NETWORK SERVICE account read (:R) access to the file.</span></span>  
  
        ```  
        icacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /grant "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="bc9cb-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="bc9cb-144">See also</span></span>
- [<span data-ttu-id="bc9cb-145">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="bc9cb-145">FindPrivateKey</span></span>](../../../../docs/framework/wcf/samples/findprivatekey.md)
- [<span data-ttu-id="bc9cb-146">방법: 인증서의 지문 검색</span><span class="sxs-lookup"><span data-stu-id="bc9cb-146">How to: Retrieve the Thumbprint of a Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
- [<span data-ttu-id="bc9cb-147">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="bc9cb-147">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
