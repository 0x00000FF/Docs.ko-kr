---
title: IMetaDataEmit::SetTypeDefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7500d7b95426aefc49fea2613ea1572f466defc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496077"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="9b7c5-102">IMetaDataEmit::SetTypeDefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="9b7c5-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="9b7c5-103">설정에 대 한 이전 호출에서 정의 된 형식 기능의 [imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7c5-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b7c5-104">구문</span><span class="sxs-lookup"><span data-stu-id="9b7c5-104">Syntax</span></span>  
  
```  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b7c5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9b7c5-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="9b7c5-106">[in] `mdTypeDef` 토큰에 대 한 원래 호출에서 얻은 [imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7c5-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="9b7c5-107">[in] `TypeDef` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7c5-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="9b7c5-108">이 비트 마스크의 `CorTypeAttr` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7c5-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="9b7c5-109">[in] `mdToken` 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7c5-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="9b7c5-110">에 대 한 이전 호출에서 가져온 [imetadataemit:: Defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), 또는 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7c5-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="9b7c5-111">[in] 이 형식이 구현 하는 인터페이스에 대 한 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7c5-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="9b7c5-112">이러한 `mdTypeRef` 를 사용 하 여 토큰을 가져오는 [imetadataemit:: Defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7c5-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="9b7c5-113">배열의 마지막 요소 여야 합니다 `mdTokenNil`합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7c5-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b7c5-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b7c5-114">Requirements</span></span>  
 <span data-ttu-id="9b7c5-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9b7c5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b7c5-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9b7c5-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b7c5-117">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="9b7c5-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b7c5-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b7c5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b7c5-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="9b7c5-119">See also</span></span>
- [<span data-ttu-id="9b7c5-120">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b7c5-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9b7c5-121">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b7c5-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
