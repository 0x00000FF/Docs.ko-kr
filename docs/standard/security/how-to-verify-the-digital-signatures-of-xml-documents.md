---
title: "방법: XML 문서의 디지털 서명 확인"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.SignedXml class
- signatures, cryptographic
- System.Security.Cryptography.RSACryptoServiceProvider class
- verifying signatures
- checking signatures
- XML digital signatures
- digital signatures, verifying
ms.assetid: a4d5ceb1-b9f5-47e8-9e4a-a2b39110002f
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a2c8cf23e1f00d6deac52f3c4bee8932b7c487a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-verify-the-digital-signatures-of-xml-documents"></a><span data-ttu-id="57453-102">방법: XML 문서의 디지털 서명 확인</span><span class="sxs-lookup"><span data-stu-id="57453-102">How to: Verify the Digital Signatures of XML Documents</span></span>
<span data-ttu-id="57453-103"><xref:System.Security.Cryptography.Xml> 네임스페이스의 클래스를 사용하여 디지털 서명으로 서명된 XML 데이터를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57453-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to verify XML data signed with a digital signature.</span></span>  <span data-ttu-id="57453-104">XML 디지털 서명(XMLDSIG)을 사용하면 서명된 후 데이터가 변경되지 않았음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57453-104">XML digital signatures (XMLDSIG) allow you to verify that data was not altered after it was signed.</span></span>  <span data-ttu-id="57453-105">XMLDSIG 표준에 대한 자세한 내용은 http://www.w3.org/TR/xmldsig-core/의 W3C(World Wide Web 컨소시엄) 사양을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57453-105">For more information about the XMLDSIG standard, see the World Wide Web Consortium (W3C) specification at http://www.w3.org/TR/xmldsig-core/.</span></span>  
  
 <span data-ttu-id="57453-106">이 절차의 코드 예제에서는 <`Signature`> 요소에 포함된 XML 디지털 서명을 확인하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="57453-106">The code example in this procedure demonstrates how to verify an XML digital signature contained in a <`Signature`> element.</span></span>  <span data-ttu-id="57453-107">이 예제에서는 키 컨테이너에서 RSA 공개 키를 검색한 다음 키를 사용하여 서명을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="57453-107">The example retrieves an RSA public key from a key container and then uses the key to verify the signature.</span></span>  
  
 <span data-ttu-id="57453-108">이 기술을 사용 하 여 확인할 수 있는 디지털 서명을 만드는 하는 방법에 대 한 정보를 참조 [하는 방법: 서명 디지털 서명으로 XML 문서](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="57453-108">For information about how create a digital signature that can be verified using this technique, see [How to: Sign XML Documents with Digital Signatures](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span></span>  
  
### <a name="to-verify-the-digital-signature-of-an-xml-document"></a><span data-ttu-id="57453-109">XML 문서의 디지털 서명을 확인하려면</span><span class="sxs-lookup"><span data-stu-id="57453-109">To verify the digital signature of an XML document</span></span>  
  
1.  <span data-ttu-id="57453-110">문서를 확인하려면 서명에 사용된 것과 동일한 비대칭 키를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57453-110">To verify the document, you must use the same asymmetric key that was used for signing.</span></span>  <span data-ttu-id="57453-111"><xref:System.Security.Cryptography.CspParameters> 개체를 만들고 서명에 사용된 키 컨테이너의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="57453-111">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container that was used for signing.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#2)]  
  
2.  <span data-ttu-id="57453-112"><xref:System.Security.Cryptography.RSACryptoServiceProvider> 클래스를 사용하여 공개 키를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="57453-112">Retrieve the public key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="57453-113"><xref:System.Security.Cryptography.RSACryptoServiceProvider> 클래스의 생성자에 <xref:System.Security.Cryptography.CspParameters> 개체를 전달하면 키가 이름을 기준으로 자동으로 키 컨테이너에서 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="57453-113">The key is automatically loaded from the key container by name when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#3)]  
  
3.  <span data-ttu-id="57453-114">디스크에서 XML 파일을 로드하여 <xref:System.Xml.XmlDocument> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57453-114">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="57453-115"><xref:System.Xml.XmlDocument> 개체에는 확인할 서명된 XML 문서가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57453-115">The <xref:System.Xml.XmlDocument> object contains the signed XML document to verify.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#4)]  
  
4.  <span data-ttu-id="57453-116">새 <xref:System.Security.Cryptography.Xml.SignedXml> 개체를 만들고 <xref:System.Xml.XmlDocument> 개체를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="57453-116">Create a new <xref:System.Security.Cryptography.Xml.SignedXml> object and pass the <xref:System.Xml.XmlDocument> object to it.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#5)]  
  
5.  <span data-ttu-id="57453-117"><`signature`> 요소를 찾고 새 <xref:System.Xml.XmlNodeList> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57453-117">Find the <`signature`> element and create a new <xref:System.Xml.XmlNodeList> object.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#6)]  
  
6.  <span data-ttu-id="57453-118">첫 번째 <`signature`> 요소의 XML을 <xref:System.Security.Cryptography.Xml.SignedXml> 개체에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="57453-118">Load the XML of the first <`signature`> element into the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#7)]  
  
7.  <span data-ttu-id="57453-119"><xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> 메서드 및 RSA 공개 키를 사용하여 서명을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="57453-119">Check the signature using the <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> method and the RSA public key.</span></span>  <span data-ttu-id="57453-120">이 메서드는 성공 또는 실패를 나타내는 부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="57453-120">This method returns a Boolean value that indicates success or failure.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="57453-121">예제</span><span class="sxs-lookup"><span data-stu-id="57453-121">Example</span></span>  
 <span data-ttu-id="57453-122">이 예제에서는 `"test.xml"`이라는 파일이 컴파일된 프로그램과 동일한 디렉터리에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="57453-122">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="57453-123">`"test.xml"` 에 설명 된 기술을 사용 하 여 파일에 서명 해야 [하는 방법: 서명 디지털 서명으로 XML 문서](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="57453-123">The `"test.xml"` file must be signed using the techniques described in [How to: Sign XML Documents with Digital Signatures](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span></span>  
  
 [!code-csharp[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#1)]
 [!code-vb[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="57453-124">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="57453-124">Compiling the Code</span></span>  
  
-   <span data-ttu-id="57453-125">이 예제를 컴파일하려면 `System.Security.dll`에 대한 참조를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57453-125">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
-   <span data-ttu-id="57453-126"><xref:System.Xml>, <xref:System.Security.Cryptography> 및 <xref:System.Security.Cryptography.Xml> 네임스페이스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="57453-126">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="57453-127">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="57453-127">.NET Framework Security</span></span>  
 <span data-ttu-id="57453-128">비대칭 키 쌍의 개인 키를 일반 텍스트로 저장하거나 전송하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="57453-128">Never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="57453-129">대칭 및 비대칭 암호화 키에 대 한 자세한 내용은 참조 [암호화 및 암호 해독용 키 생성](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="57453-129">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="57453-130">소스 코드에 직접 개인 키를 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="57453-130">Never embed a private key directly into your source code.</span></span>  <span data-ttu-id="57453-131">포함 된 키를 사용 하 여 어셈블리에서 쉽게 읽을 수 있습니다는 [Ildasm.exe (IL 디스어셈블러)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) 또는 메모장과 같은 텍스트 편집기에서 어셈블리를 열어 합니다.</span><span class="sxs-lookup"><span data-stu-id="57453-131">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57453-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="57453-132">See Also</span></span>  
 <xref:System.Security.Cryptography.Xml>  
 [<span data-ttu-id="57453-133">방법: 디지털 서명으로 XML 문서 서명</span><span class="sxs-lookup"><span data-stu-id="57453-133">How to: Sign XML Documents with Digital Signatures</span></span>](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md)
