---
title: '방법: 데이터 보호 사용'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET Framework], data protection API
- data [.NET Framework], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET Framework], data protection API
- data protection API [.NET Framework]
- decryption
- data [.NET Framework], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b043c5a2173cff9eb82497f6d4ee8b7c0aa3f14c
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44140344"
---
# <a name="how-to-use-data-protection"></a><span data-ttu-id="4655f-102">방법: 데이터 보호 사용</span><span class="sxs-lookup"><span data-stu-id="4655f-102">How to: Use Data Protection</span></span>
<span data-ttu-id="4655f-103">.NET Framework는 현재 사용자 계정 또는 컴퓨터의 정보를 사용하여 데이터를 암호화할 수 있게 해주는 DPAPI(데이터 보호 API)에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-103">The .NET Framework provides access to the data protection API (DPAPI), which allows you to encrypt data using information from the current user account or computer.</span></span>  <span data-ttu-id="4655f-104">DPAPI를 사용하는 경우 명시적으로 암호화 키를 생성 및 저장하는 어려운 문제가 완화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-104">When you use the DPAPI, you alleviate the difficult problem of explicitly generating and storing a cryptographic key.</span></span>  
  
 <span data-ttu-id="4655f-105"><xref:System.Security.Cryptography.ProtectedMemory> 클래스를 사용하여 메모리 내 바이트 배열을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-105">Use the <xref:System.Security.Cryptography.ProtectedMemory> class to encrypt an array of in-memory bytes.</span></span>  <span data-ttu-id="4655f-106">이 기능은 Microsoft Windows XP 이상의 운영 체제에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-106">This functionality is available in Microsoft Windows XP and later operating systems.</span></span>  <span data-ttu-id="4655f-107">현재 프로세스에서 암호화된 메모리가 현재 프로세스에서만, 모든 프로세스에서 또는 동일한 사용자 컨텍스트에서 암호 해독할 수 있도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-107">You can specify that memory encrypted by the current process can be decrypted by the current process only, by all processes, or from the same user context.</span></span>  <span data-ttu-id="4655f-108"><xref:System.Security.Cryptography.ProtectedMemory> 옵션에 대한 자세한 내용은 <xref:System.Security.Cryptography.MemoryProtectionScope> 열거형을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4655f-108">See the <xref:System.Security.Cryptography.MemoryProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedMemory> options.</span></span>  
  
 <span data-ttu-id="4655f-109"><xref:System.Security.Cryptography.ProtectedData> 클래스를 사용하여 바이트 배열 복사본을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-109">Use the <xref:System.Security.Cryptography.ProtectedData> class to encrypt a copy of an array of bytes.</span></span> <span data-ttu-id="4655f-110">이 기능은 Microsoft Windows 2000 이상의 운영 체제에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-110">This functionality is available in Microsoft Windows 2000 and later operating systems.</span></span>  <span data-ttu-id="4655f-111">현재 사용자 계정에서 암호화된 데이터가 동일한 사용자 계정에 의해서만 암호 해독될 수 있도록 지정하거나, 현재 사용자 계정에서 암호화된 데이터가 컴퓨터의 모든 계정에 의해 암호 해독될 수 있도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-111">You can specify that data encrypted by the current user account can be decrypted only by the same user account, or you can specify that data encrypted by the current user account can be decrypted by any account on the computer.</span></span>  <span data-ttu-id="4655f-112"><xref:System.Security.Cryptography.ProtectedData> 옵션에 대한 자세한 내용은 <xref:System.Security.Cryptography.DataProtectionScope> 열거형을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4655f-112">See the <xref:System.Security.Cryptography.DataProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedData> options.</span></span>  
  
### <a name="to-encrypt-in-memory-data-using-data-protection"></a><span data-ttu-id="4655f-113">데이터 보호를 사용하여 메모리 내 데이터를 암호화하려면</span><span class="sxs-lookup"><span data-stu-id="4655f-113">To encrypt in-memory data using data protection</span></span>  
  
1.  <span data-ttu-id="4655f-114">암호화할 바이트 배열, 엔트로피 및 메모리 보호 범위를 전달하는 동안 정적 <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-114">Call the static <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the memory protection scope.</span></span>  
  
### <a name="to-decrypt-in-memory-data-using-data-protection"></a><span data-ttu-id="4655f-115">데이터 보호를 사용하여 메모리 내 데이터를 암호 해독하려면</span><span class="sxs-lookup"><span data-stu-id="4655f-115">To decrypt in-memory data using data protection</span></span>  
  
1.  <span data-ttu-id="4655f-116">암호 해독할 바이트 배열 및 메모리 보호 범위를 전달하는 동안 정적 <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-116">Call the static <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> method while passing an array of bytes to decrypt and the memory protection scope.</span></span>  
  
### <a name="to-encrypt-data-to-a-file-or-stream-using-data-protection"></a><span data-ttu-id="4655f-117">데이터 보호를 사용하여 파일 또는 스트림에 데이터를 암호화하려면</span><span class="sxs-lookup"><span data-stu-id="4655f-117">To encrypt data to a file or stream using data protection</span></span>  
  
1.  <span data-ttu-id="4655f-118">임의 엔트로피를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-118">Create random entropy.</span></span>  
  
2.  <span data-ttu-id="4655f-119">암호화할 바이트 배열, 엔트로피 및 데이터 보호 범위를 전달하는 동안 정적 <xref:System.Security.Cryptography.ProtectedData.Protect%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-119">Call the static <xref:System.Security.Cryptography.ProtectedData.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the data protection scope.</span></span>  
  
3.  <span data-ttu-id="4655f-120">파일 또는 스트림에 암호화된 데이터를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-120">Write the encrypted data to a file or stream.</span></span>  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a><span data-ttu-id="4655f-121">데이터 보호를 사용하여 파일 또는 스트림에서 데이터를 암호 해독하려면</span><span class="sxs-lookup"><span data-stu-id="4655f-121">To decrypt data from a file or stream using data protection</span></span>  
  
1.  <span data-ttu-id="4655f-122">파일 또는 스트림에서 암호화된 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-122">Read the encrypted data from a file or stream.</span></span>  
  
2.  <span data-ttu-id="4655f-123">암호 해독할 바이트 배열 및 데이터 보호 범위를 전달하는 동안 정적 <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-123">Call the static <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> method while passing an array of bytes to decrypt and the data protection scope.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4655f-124">예제</span><span class="sxs-lookup"><span data-stu-id="4655f-124">Example</span></span>  
 <span data-ttu-id="4655f-125">다음 코드 예제에서는 두 가지 형태의 암호화 및 암호 해독을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-125">The following code example demonstrates two forms of encryption and decryption.</span></span>  <span data-ttu-id="4655f-126">먼저 코드 예제에서 메모리 내 바이트 배열을 암호화한 다음 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-126">First, the code example encrypts and then decrypts an in-memory array of bytes.</span></span>  <span data-ttu-id="4655f-127">그런 다음 코드 예제에서 바이트 배열의 복사본을 암호화하고 파일에 저장한 다음 파일에서 다시 데이터를 로드하고 데이터를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-127">Next, the code example encrypts a copy of a byte array, saves it to a file, loads the data back from the file, and then decrypts the data.</span></span>  <span data-ttu-id="4655f-128">이 예제에서는 원본 데이터, 암호화된 데이터 및 암호 해독된 데이터를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-128">The example displays the original data, the encrypted data, and the decrypted data.</span></span>  
  
 [!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
 [!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4655f-129">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="4655f-129">Compiling the Code</span></span>  
  
-   <span data-ttu-id="4655f-130">`System.Security.dll`에 대한 참조를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-130">Include a reference to `System.Security.dll`.</span></span>  
  
-   <span data-ttu-id="4655f-131"><xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> 및 <xref:System.Text> 네임스페이스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4655f-131">Include the <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography>, and <xref:System.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4655f-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="4655f-132">See also</span></span>

- <xref:System.Security.Cryptography.ProtectedMemory>  
- <xref:System.Security.Cryptography.ProtectedData>
