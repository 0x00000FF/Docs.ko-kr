---
title: 암호화 체계 만들기
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b1635276465dd58028c8a5e4b7e69a307664a4c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33580759"
---
# <a name="creating-a-cryptographic-scheme"></a><span data-ttu-id="4e9ab-102">암호화 체계 만들기</span><span class="sxs-lookup"><span data-stu-id="4e9ab-102">Creating a Cryptographic Scheme</span></span>
<span data-ttu-id="4e9ab-103">.NET Framework의 암호화 구성 요소를 결합하여 다양한 체계를 만들고 데이터를 암호화 및 암호 해독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e9ab-103">The cryptographic components of the .NET Framework can be combined to create different schemes to encrypt and decrypt data.</span></span>  
  
 <span data-ttu-id="4e9ab-104">데이터 암호화 및 암호 해독을 위한 간단한 암호화 체계에서는 다음 단계를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e9ab-104">A simple cryptographic scheme for encrypting and decrypting data might specify the following steps:</span></span>  
  
1.  <span data-ttu-id="4e9ab-105">각 당사자가 공개/개인 키 쌍을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9ab-105">Each party generates a public/private key pair.</span></span>  
  
2.  <span data-ttu-id="4e9ab-106">양쪽 당사자가 공개 키를 교환합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9ab-106">The parties exchange their public keys.</span></span>  
  
3.  <span data-ttu-id="4e9ab-107">예를 들어 각 당사자가 TripleDES 암호화를 위한 비밀 키를 생성하고 상대방의 공개 키를 사용하여 새로 만든 키를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9ab-107">Each party generates a secret key for TripleDES encryption, for example, and encrypts the newly created key using the other's public key.</span></span>  
  
4.  <span data-ttu-id="4e9ab-108">각 당사자가 상대방에게 데이터를 보내고 상대방의 비밀 키와 자신의 비밀 키를 특정 순서로 결합하여 새 비밀 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e9ab-108">Each party sends the data to the other and combines the other's secret key with its own, in a particular order, to create a new secret key.</span></span>  
  
5.  <span data-ttu-id="4e9ab-109">양쪽 당사자가 대칭 암호화를 사용하여 대화를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9ab-109">The parties then initiate a conversation using symmetric encryption.</span></span>  
  
 <span data-ttu-id="4e9ab-110">암호화 체계를 만드는 과정은 간단한 작업이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4e9ab-110">Creating a cryptographic scheme is not a trivial task.</span></span> <span data-ttu-id="4e9ab-111">암호화 사용에 대 한 자세한 내용은 플랫폼 SDK 설명서에서의 암호화 항목을 참조 하십시오. http://msdn.microsoft.com/library합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9ab-111">For more information on using cryptography, see the Cryptography topic in the Platform SDK documentation at http://msdn.microsoft.com/library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e9ab-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e9ab-112">See Also</span></span>  
 [<span data-ttu-id="4e9ab-113">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="4e9ab-113">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
