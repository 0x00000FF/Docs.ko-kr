---
title: StrongNameTokenFromPublicKey 함수
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 197504cbb0dd66c0cf43dee718026fc63e918d60
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798859"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="f183d-102">StrongNameTokenFromPublicKey 함수</span><span class="sxs-lookup"><span data-stu-id="f183d-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="f183d-103">공개 키를 나타내는 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f183d-103">Gets a token representing a public key.</span></span> <span data-ttu-id="f183d-104">강력한 이름 토큰은 공개 키의 축약 된 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="f183d-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="f183d-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f183d-105">This function has been deprecated.</span></span> <span data-ttu-id="f183d-106">대신 [ICLRStrongName:: StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f183d-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f183d-107">구문</span><span class="sxs-lookup"><span data-stu-id="f183d-107">Syntax</span></span>  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f183d-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f183d-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="f183d-109">진행 강력한 이름 서명을 생성 하는 데 사용 되는 키 쌍의 공개 부분을 포함 하는 [PublicKeyBlob](publickeyblob-structure.md) 형식의 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="f183d-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="f183d-110">진행 의 `pbPublicKeyBlob`크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="f183d-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="f183d-111">제한이 전달 된 키에 해당 하는 강력한 이름 토큰 `pbPublicKeyBlob`입니다.</span><span class="sxs-lookup"><span data-stu-id="f183d-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="f183d-112">공용 언어 런타임은 토큰을 반환할 메모리를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f183d-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="f183d-113">호출자는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 사용 하 여이 메모리를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f183d-113">The caller must free this memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="f183d-114">제한이 반환 된 강력한 이름 토큰의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="f183d-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f183d-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="f183d-115">Return Value</span></span>  
 <span data-ttu-id="f183d-116">`true`성공적으로 완료 되 면 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="f183d-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f183d-117">설명</span><span class="sxs-lookup"><span data-stu-id="f183d-117">Remarks</span></span>  
 <span data-ttu-id="f183d-118">강력한 이름 토큰은 키 정보를 메타 데이터에 저장할 때 공간을 절약 하는 데 사용 되는 공개 키의 축약 된 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="f183d-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="f183d-119">특히 강력한 이름 토큰은 어셈블리 참조에서 종속 어셈블리를 참조 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f183d-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="f183d-120">`StrongNameTokenFromPublicKey` 함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f183d-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f183d-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f183d-121">Requirements</span></span>  
 <span data-ttu-id="f183d-122">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f183d-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f183d-123">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="f183d-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f183d-124">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f183d-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="f183d-125">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f183d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f183d-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="f183d-126">See also</span></span>

- [<span data-ttu-id="f183d-127">StrongNameTokenFromPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="f183d-127">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="f183d-128">StrongNameGetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="f183d-128">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="f183d-129">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="f183d-129">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
