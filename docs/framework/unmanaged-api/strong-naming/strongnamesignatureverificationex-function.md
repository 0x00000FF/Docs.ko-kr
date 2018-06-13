---
title: StrongNameSignatureVerificationEx 함수
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ce139669c0a31301f3eecdef4b4d61f83d5e4e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458941"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="44664-102">StrongNameSignatureVerificationEx 함수</span><span class="sxs-lookup"><span data-stu-id="44664-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="44664-103">제공 된 경로의 어셈블리 매니페스트는 강력한 이름 서명을 포함 되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="44664-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="44664-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44664-104">This function has been deprecated.</span></span> <span data-ttu-id="44664-105">사용 하 여 [iclrstrongname:: Strongnamesignatureverificationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="44664-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44664-106">구문</span><span class="sxs-lookup"><span data-stu-id="44664-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44664-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="44664-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="44664-108">[in] 이식 가능한 실행 (.exe 또는.dll) 파일에 어셈블리를 확인할 수에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="44664-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="44664-109">[in] `true` 고, 그렇지 않으면 레지스트리 설정을 재정의 하는 데 필요한 경우에 유효성 검사를 수행 하려면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="44664-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="44664-110">[out] `true` 강력한 이름 서명을 했으면 확인 된, `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="44664-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="44664-111">`pfWasVerified` 도로 설정 `false` 레지스트리 설정으로 인해 확인 되 면 합니다.</span><span class="sxs-lookup"><span data-stu-id="44664-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44664-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="44664-112">Return Value</span></span>  
 <span data-ttu-id="44664-113">`true` 확인에 성공 하면 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="44664-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44664-114">설명</span><span class="sxs-lookup"><span data-stu-id="44664-114">Remarks</span></span>  
 <span data-ttu-id="44664-115">`StrongNameSignatureVerificationEx` 유사한 기능을 제공 된 [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="44664-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="44664-116">그러나 두 번째 입력 매개 변수와 출력 매개 변수를 `StrongNameSignatureVerificationEx` 형식의 `BOOLEAN` 대신 `DWORD`합니다.</span><span class="sxs-lookup"><span data-stu-id="44664-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44664-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="44664-117">Requirements</span></span>  
 <span data-ttu-id="44664-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44664-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44664-119">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="44664-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="44664-120">**라이브러리:** mscoree.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="44664-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="44664-121">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44664-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44664-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44664-122">See Also</span></span>  
 [<span data-ttu-id="44664-123">StrongNameSignatureVerificationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="44664-123">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="44664-124">StrongNameSignatureVerification 메서드</span><span class="sxs-lookup"><span data-stu-id="44664-124">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="44664-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44664-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
