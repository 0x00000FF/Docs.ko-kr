---
title: ICLRStrongName::GetHashFromAssemblyFile 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8d9e7d593c2a8a9cce798724b2705dee21a740e
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45527034"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="478d0-102">ICLRStrongName::GetHashFromAssemblyFile 메서드</span><span class="sxs-lookup"><span data-stu-id="478d0-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="478d0-103">지정된 해시 알고리즘을 사용하여 지정된 어셈블리 파일의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="478d0-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="478d0-104">구문</span><span class="sxs-lookup"><span data-stu-id="478d0-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="478d0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="478d0-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="478d0-106">[in] 해시할 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="478d0-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="478d0-107">[out에서] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="478d0-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="478d0-108">기본 해시 알고리즘에 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="478d0-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="478d0-109">[out] 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="478d0-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="478d0-110">[in] 요청 된 최대 크기인 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="478d0-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="478d0-111">[out] 크기 (바이트)를 반환 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="478d0-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="478d0-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="478d0-112">Return Value</span></span>  
 <span data-ttu-id="478d0-113">`S_OK` 메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값을 (참조 [일반적인 HRESULT 값](https://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="478d0-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="478d0-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="478d0-114">Requirements</span></span>  
 <span data-ttu-id="478d0-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="478d0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="478d0-116">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="478d0-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="478d0-117">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="478d0-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="478d0-118">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="478d0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="478d0-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="478d0-119">See Also</span></span>  
 [<span data-ttu-id="478d0-120">GetHashFromAssemblyFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="478d0-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="478d0-121">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="478d0-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
