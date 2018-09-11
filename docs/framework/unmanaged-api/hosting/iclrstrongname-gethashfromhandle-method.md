---
title: ICLRStrongName::GetHashFromHandle 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromHandle
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromHandle method [.NET Framework hosting]
ms.assetid: 3bedbb7d-3cdd-4175-b370-10ae734062db
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20c5f6bbb58b85f42ec00e356eccc5fb41ce813c
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44339041"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="73944-102">ICLRStrongName::GetHashFromHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="73944-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="73944-103">지정 된 해시 알고리즘을 사용 하 여 지정 된 파일 핸들에 있는 파일의 내용에 대 한 해시를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="73944-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73944-104">구문</span><span class="sxs-lookup"><span data-stu-id="73944-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73944-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="73944-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="73944-106">[in] 해시 될 파일의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="73944-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="73944-107">[out에서] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="73944-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="73944-108">기본 알고리즘에 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="73944-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="73944-109">[out] 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="73944-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="73944-110">[in] 요청 된 최대 크기인 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="73944-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="73944-111">[out] 반환 된 바이트의 크기, `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="73944-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73944-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="73944-112">Return Value</span></span>  
 <span data-ttu-id="73944-113">`S_OK` 메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값을 (참조 [일반적인 HRESULT 값](https://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="73944-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73944-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="73944-114">Requirements</span></span>  
 <span data-ttu-id="73944-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73944-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73944-116">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="73944-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="73944-117">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="73944-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73944-118">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73944-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73944-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73944-119">See Also</span></span>  
 [<span data-ttu-id="73944-120">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73944-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
