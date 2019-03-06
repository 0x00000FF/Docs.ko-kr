---
title: IMetaDataEmit::DeletePinvokeMap 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeletePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5775c249236fdbe488ce11be0c664d2073ccfb67
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477077"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="540c8-102">IMetaDataEmit::DeletePinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="540c8-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="540c8-103">지정한 토큰이 참조 하는 개체에 대 한 PInvoke 매핑 메타 데이터를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="540c8-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="540c8-104">구문</span><span class="sxs-lookup"><span data-stu-id="540c8-104">Syntax</span></span>  
  
```  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="540c8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="540c8-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="540c8-106">[in] `mdFieldDef` 또는 `mdMethodDef` PInvoke 매핑 메타 데이터를 삭제 하는 개체를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="540c8-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="540c8-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="540c8-107">Requirements</span></span>  
 <span data-ttu-id="540c8-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="540c8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="540c8-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="540c8-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="540c8-110">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="540c8-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="540c8-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="540c8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="540c8-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="540c8-112">See also</span></span>
- [<span data-ttu-id="540c8-113">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="540c8-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="540c8-114">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="540c8-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
