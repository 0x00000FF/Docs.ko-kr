---
title: IMetaDataEmit::GetTokenFromTypeSpec 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ff240a80d2910dcb050cc022257c6eba166bbdc5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465935"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="7694a-102">IMetaDataEmit::GetTokenFromTypeSpec 메서드</span><span class="sxs-lookup"><span data-stu-id="7694a-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="7694a-103">지정 된 메타 데이터 서명 사용 하 여 형식에 대 한 메타 데이터를 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7694a-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7694a-104">구문</span><span class="sxs-lookup"><span data-stu-id="7694a-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7694a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7694a-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="7694a-106">[in] 정의 되는 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="7694a-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="7694a-107">[in] 바이트 수가 `pvSig`합니다.</span><span class="sxs-lookup"><span data-stu-id="7694a-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="7694a-108">[out] `mdTypeSpec` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7694a-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7694a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7694a-109">Requirements</span></span>  
 <span data-ttu-id="7694a-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7694a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7694a-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7694a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7694a-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="7694a-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7694a-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7694a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7694a-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="7694a-114">See also</span></span>
- [<span data-ttu-id="7694a-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7694a-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7694a-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7694a-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
