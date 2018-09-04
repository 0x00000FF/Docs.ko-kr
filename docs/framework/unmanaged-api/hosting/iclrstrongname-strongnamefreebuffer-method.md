---
title: ICLRStrongName::StrongNameFreeBuffer 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameFreeBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameFreeBuffer method [.NET Framework hosting]
ms.assetid: 6148c508-bd1d-4a37-85c3-06ecb09cc857
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef8c1e96c12b554a89d012633d1e5c347dab6de4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501235"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a><span data-ttu-id="0acf3-102">ICLRStrongName::StrongNameFreeBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="0acf3-102">ICLRStrongName::StrongNameFreeBuffer Method</span></span>
<span data-ttu-id="0acf3-103">와 같은 강력한 이름의 메서드에 대 한 이전 호출을 사용 하 여 할당 된 메모리를 해제 [iclrstrongname:: Strongnamegetpublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)하십시오 [iclrstrongname:: Strongnametokenfrompublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), 또는 [ Iclrstrongname:: Strongnamesignaturegeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0acf3-103">Frees memory that was allocated with a previous call to a strong name method such as [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), or [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0acf3-104">구문</span><span class="sxs-lookup"><span data-stu-id="0acf3-104">Syntax</span></span>  
  
```  
HRESULT StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0acf3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0acf3-105">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="0acf3-106">[in] 사용 가능한 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0acf3-106">[in] A pointer to the memory to free.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0acf3-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="0acf3-107">Return Value</span></span>  
 <span data-ttu-id="0acf3-108">`S_OK` 메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값을 (참조 [일반적인 HRESULT 값](https://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="0acf3-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0acf3-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0acf3-109">Requirements</span></span>  
 <span data-ttu-id="0acf3-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0acf3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0acf3-111">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="0acf3-111">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0acf3-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0acf3-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0acf3-113">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0acf3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0acf3-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0acf3-114">See Also</span></span>  
 [<span data-ttu-id="0acf3-115">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0acf3-115">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
