---
title: Cert2spc.exe(SPC 테스트 도구)
ms.date: 03/30/2017
helpviewer_keywords:
- SPC
- Software Publisher Certificate Test tool
- Software Publisher Certificate
- Cert2spc.exe
- certificates, Software Publisher's Certificate
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 079c48a9975861646f1d28338d02dab8e4775031
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101239"
---
# <a name="cert2spcexe-software-publisher-certificate-test-tool"></a><span data-ttu-id="39842-102">Cert2spc.exe(SPC 테스트 도구)</span><span class="sxs-lookup"><span data-stu-id="39842-102">Cert2spc.exe (Software Publisher Certificate Test Tool)</span></span>
<span data-ttu-id="39842-103">SPC(소프트웨어 게시자 인증서) 테스트 도구를 사용하면 하나 이상의 X.509 인증서에서 SPC를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39842-103">The Software Publisher Certificate Test tool creates a Software Publisher's Certificate (SPC) from one or more X.509 certificates.</span></span> <span data-ttu-id="39842-104">Cert2spc.exe는 테스트 전용이며,</span><span class="sxs-lookup"><span data-stu-id="39842-104">Cert2spc.exe is for test purposes only.</span></span> <span data-ttu-id="39842-105">VeriSign 또는 Thawte 같은 인증 기관에서 유효한 SPC를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39842-105">You can obtain a valid SPC from a Certification Authority such as VeriSign or Thawte.</span></span> <span data-ttu-id="39842-106">X.509 인증서를 만드는 방법은 [Makecert.exe(인증서 작성 도구)](/windows/desktop/SecCrypto/makecert)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39842-106">For more information about creating X.509 certificates, see [Makecert.exe (Certificate Creation Tool)](/windows/desktop/SecCrypto/makecert).</span></span>  
  
 <span data-ttu-id="39842-107">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="39842-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="39842-108">이 도구를 실행하려면 Visual Studio용 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="39842-108">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="39842-109">자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39842-109">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="39842-110">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="39842-110">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39842-111">구문</span><span class="sxs-lookup"><span data-stu-id="39842-111">Syntax</span></span>  
  
```  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
## <a name="parameters"></a><span data-ttu-id="39842-112">매개 변수</span><span class="sxs-lookup"><span data-stu-id="39842-112">Parameters</span></span>  
  
|<span data-ttu-id="39842-113">인수</span><span class="sxs-lookup"><span data-stu-id="39842-113">Argument</span></span>|<span data-ttu-id="39842-114">설명</span><span class="sxs-lookup"><span data-stu-id="39842-114">Description</span></span>|  
|--------------|-----------------|  
|`certN.cer`|<span data-ttu-id="39842-115">SPC 파일에 포함할 X.509 인증서의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="39842-115">The name of an X.509 certificate to include in the SPC file.</span></span> <span data-ttu-id="39842-116">여러 개의 이름을 공백으로 구분하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39842-116">You can specify multiple names separated by spaces.</span></span>|  
|`crlN.crl`|<span data-ttu-id="39842-117">SPC 파일에 포함할 인증서 해지 목록의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="39842-117">The name of a certificate revocation list to include in the SPC file.</span></span> <span data-ttu-id="39842-118">여러 개의 이름을 공백으로 구분하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39842-118">You can specify multiple names separated by spaces.</span></span>|  
|`outputSPCfile.spc`|<span data-ttu-id="39842-119">X.509 인증서가 들어 있는 PKCS #7 개체의 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="39842-119">The name of the PKCS #7 object that will contain the X.509 certificates.</span></span>|  
  
|<span data-ttu-id="39842-120">옵션</span><span class="sxs-lookup"><span data-stu-id="39842-120">Option</span></span>|<span data-ttu-id="39842-121">설명</span><span class="sxs-lookup"><span data-stu-id="39842-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="39842-122">**/?**</span><span class="sxs-lookup"><span data-stu-id="39842-122">**/?**</span></span>|<span data-ttu-id="39842-123">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="39842-123">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="39842-124">예제</span><span class="sxs-lookup"><span data-stu-id="39842-124">Examples</span></span>  
 <span data-ttu-id="39842-125">다음 명령을 사용하여 `myCertificate.cer`에서 SPC를 만들고 이를 `mySPCFile.spc`에 포함시킵니다.</span><span class="sxs-lookup"><span data-stu-id="39842-125">The following command creates an SPC from `myCertificate.cer` and places it in `mySPCFile.spc`.</span></span>  
  
```  
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 <span data-ttu-id="39842-126">다음 명령을 사용하여 `oneCertificate.cer` 및 `twoCertificate.cer`에서 SPC를 만들고 이를 `mySPCFile.spc`에 포함시킵니다.</span><span class="sxs-lookup"><span data-stu-id="39842-126">The following command creates an SPC from `oneCertificate.cer` and `twoCertificate.cer`, and places it in `mySPCFile.spc`.</span></span>  
  
```  
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## <a name="see-also"></a><span data-ttu-id="39842-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39842-127">See also</span></span>

- [<span data-ttu-id="39842-128">도구</span><span class="sxs-lookup"><span data-stu-id="39842-128">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="39842-129">Makecert.exe(인증서 작성 도구)</span><span class="sxs-lookup"><span data-stu-id="39842-129">Makecert.exe (Certificate Creation Tool)</span></span>](/windows/desktop/SecCrypto/makecert)
- [<span data-ttu-id="39842-130">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="39842-130">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
