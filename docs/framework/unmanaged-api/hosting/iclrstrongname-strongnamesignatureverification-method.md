---
title: ICLRStrongName::StrongNameSignatureVerification 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerification
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerification method [.NET Framework hosting]
- StrongNameSignatureVerification method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 734dc4d1-0a76-4736-b5ac-cb4253b3dd49
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49041031742332fbc275a9dbde91e640eb428c28
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43561339"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a><span data-ttu-id="0db72-102">ICLRStrongName::StrongNameSignatureVerification 메서드</span><span class="sxs-lookup"><span data-stu-id="0db72-102">ICLRStrongName::StrongNameSignatureVerification Method</span></span>
<span data-ttu-id="0db72-103">어셈블리 매니페스트에 제공 된 경로의 지정된 된 플래그에 따라 확인할 수 있는 강력한 이름 서명을 포함 되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0db72-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0db72-104">구문</span><span class="sxs-lookup"><span data-stu-id="0db72-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0db72-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0db72-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="0db72-106">[in] 이식 가능한 실행 파일 (.dll 또는.exe) 파일에 어셈블리 확인에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="0db72-106">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="0db72-107">[in] 확인 동작을 수정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="0db72-107">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="0db72-108">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0db72-108">The following values are supported:</span></span>  
  
-   <span data-ttu-id="0db72-109">`SN_INFLAG_FORCE_VER` (0x00000001)-레지스트리 설정을 재정의 해야 하는 경우에 확인이 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0db72-109">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="0db72-110">`SN_INFLAG_INSTALL` (0x00000002)-매니페스트를 확인 하는 첫 번째 시간 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0db72-110">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   <span data-ttu-id="0db72-111">`SN_INFLAG_ADMIN_ACCESS` (0x00000004)-캐시는 관리 권한이 있는 사용자만 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0db72-111">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="0db72-112">`SN_INFLAG_USER_ACCESS` (0x00000008)-어셈블리는 현재 사용자만 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0db72-112">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="0db72-113">`SN_INFLAG_ALL_ACCESS` (0x00000010)-캐시의 액세스 제한이 않음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0db72-113">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="0db72-114">`SN_INFLAG_RUNTIME` (0x80000000)-내부 디버깅을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0db72-114">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="0db72-115">[out] 강력한 이름 서명을 확인 하는지 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="0db72-115">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="0db72-116">다음 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0db72-116">The following value is supported:</span></span>  
  
-   <span data-ttu-id="0db72-117">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001)-이 값 설정할지 `false` 레지스트리 설정으로 인해 확인이 성공 했는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0db72-117">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0db72-118">반환 값</span><span class="sxs-lookup"><span data-stu-id="0db72-118">Return Value</span></span>  
 <span data-ttu-id="0db72-119">`S_OK` 메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값을 (참조 [일반적인 HRESULT 값](https://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="0db72-119">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0db72-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0db72-120">Requirements</span></span>  
 <span data-ttu-id="0db72-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0db72-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0db72-122">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="0db72-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0db72-123">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0db72-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0db72-124">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0db72-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0db72-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0db72-125">See Also</span></span>  
 [<span data-ttu-id="0db72-126">StrongNameSignatureVerificationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="0db72-126">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="0db72-127">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0db72-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
