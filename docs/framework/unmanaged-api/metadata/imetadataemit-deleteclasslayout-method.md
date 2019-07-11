---
title: IMetaDataEmit::DeleteClassLayout 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteClassLayout
helpviewer_keywords:
- DeleteClassLayout method [.NET Framework metadata]
- IMetaDataEmit::DeleteClassLayout method [.NET Framework metadata]
ms.assetid: 65a4ad49-fa49-4b36-8ed1-76dd6a185ab4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84de8e3c688a23198762fca5219d317fabb69c1b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777460"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="e806e-102">IMetaDataEmit::DeleteClassLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="e806e-102">IMetaDataEmit::DeleteClassLayout Method</span></span>
<span data-ttu-id="e806e-103">지정한 토큰이 나타내는 형식의 클래스 레이아웃 메타 데이터 서명을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e806e-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e806e-104">구문</span><span class="sxs-lookup"><span data-stu-id="e806e-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e806e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e806e-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="e806e-106">[in] `mdTypeDef` 클래스 레이아웃은 삭제할 형식을 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="e806e-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e806e-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e806e-107">Requirements</span></span>  
 <span data-ttu-id="e806e-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e806e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e806e-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e806e-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e806e-110">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="e806e-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e806e-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e806e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e806e-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="e806e-112">See also</span></span>

- [<span data-ttu-id="e806e-113">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e806e-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e806e-114">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e806e-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
