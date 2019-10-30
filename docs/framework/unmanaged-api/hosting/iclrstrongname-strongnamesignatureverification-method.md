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
ms.openlocfilehash: 6b473466aefc06dc83526e65f8ee9e37703ba9e4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134957"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a><span data-ttu-id="87451-102">ICLRStrongName::StrongNameSignatureVerification 메서드</span><span class="sxs-lookup"><span data-stu-id="87451-102">ICLRStrongName::StrongNameSignatureVerification Method</span></span>
<span data-ttu-id="87451-103">제공 된 경로의 어셈블리 매니페스트에 지정 된 플래그에 따라 확인 되는 강력한 이름 서명이 들어 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="87451-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87451-104">구문</span><span class="sxs-lookup"><span data-stu-id="87451-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87451-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="87451-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="87451-106">진행 어셈블리에서 확인할 이식 가능한 실행 파일 (.dll 또는 .exe)의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="87451-106">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="87451-107">진행 확인 동작을 수정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="87451-107">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="87451-108">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87451-108">The following values are supported:</span></span>  
  
- <span data-ttu-id="87451-109">`SN_INFLAG_FORCE_VER` (0x00000001)-레지스트리 설정을 재정의 해야 하는 경우에도 확인을 강제로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="87451-109">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="87451-110">`SN_INFLAG_INSTALL` (0x00000002)-매니페스트를 처음 확인 하는 것을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87451-110">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
- <span data-ttu-id="87451-111">`SN_INFLAG_ADMIN_ACCESS` (0x00000004)-캐시가 관리 권한이 있는 사용자 에게만 액세스를 허용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87451-111">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="87451-112">`SN_INFLAG_USER_ACCESS` (0x00000008)-현재 사용자만 어셈블리에 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87451-112">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="87451-113">`SN_INFLAG_ALL_ACCESS` (0x00000010)-캐시가 액세스 제한에 대 한 보장을 제공 하지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87451-113">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="87451-114">`SN_INFLAG_RUNTIME` (0x80000000)-내부 디버깅용으로 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87451-114">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="87451-115">제한이 강력한 이름 서명을 확인 했는지 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="87451-115">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="87451-116">지원 되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87451-116">The following value is supported:</span></span>  
  
- <span data-ttu-id="87451-117">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001)-이 값은 `false` 설정 되어 레지스트리 설정으로 인해 확인이 성공 했음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87451-117">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87451-118">반환 값</span><span class="sxs-lookup"><span data-stu-id="87451-118">Return Value</span></span>  
 <span data-ttu-id="87451-119">메서드가 성공적으로 완료 되 면 `S_OK` 하 고, 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](https://go.microsoft.com/fwlink/?LinkId=213878) 참조).</span><span class="sxs-lookup"><span data-stu-id="87451-119">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87451-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="87451-120">Requirements</span></span>  
 <span data-ttu-id="87451-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87451-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87451-122">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="87451-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="87451-123">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87451-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87451-124">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87451-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87451-125">참조</span><span class="sxs-lookup"><span data-stu-id="87451-125">See also</span></span>

- [<span data-ttu-id="87451-126">StrongNameSignatureVerificationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="87451-126">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="87451-127">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87451-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
