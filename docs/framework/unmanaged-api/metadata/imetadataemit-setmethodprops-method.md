---
title: "IMetaDataEmit::SetMethodProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetMethodProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d03423aa20ed9582f0e2cb38b24169a25d47e352
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="44e5b-102">IMetaDataEmit::SetMethodProps 메서드</span><span class="sxs-lookup"><span data-stu-id="44e5b-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="44e5b-103">설정 하거나 지정된 된 상대 가상 주소, 이전 호출에서 정의 된 메서드의 저장 하는 기능을 업데이트 [imetadataemit:: Definemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44e5b-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44e5b-104">구문</span><span class="sxs-lookup"><span data-stu-id="44e5b-104">Syntax</span></span>  
  
```  
HRESULT SetMethodProps (   
    [in]  mdMethodDef md,   
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,   
    [in]  DWORD       dwImplFlags   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44e5b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="44e5b-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="44e5b-106">[in] 변경 하려는 방법에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="44e5b-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="44e5b-107">[in] 멤버 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="44e5b-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="44e5b-108">[in] 코드의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="44e5b-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="44e5b-109">[in] 메서드에 대 한 구현 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="44e5b-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44e5b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="44e5b-110">Requirements</span></span>  
 <span data-ttu-id="44e5b-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44e5b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44e5b-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="44e5b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="44e5b-113">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="44e5b-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44e5b-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44e5b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e5b-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44e5b-115">See Also</span></span>  
 [<span data-ttu-id="44e5b-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44e5b-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="44e5b-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44e5b-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
