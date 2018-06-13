---
title: IMetaDataEmit::DefineTypeDef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 54691785e3b2619b5f4a2eecc510800b4b5cee07
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446599"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="c58f3-102">IMetaDataEmit::DefineTypeDef 메서드</span><span class="sxs-lookup"><span data-stu-id="c58f3-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="c58f3-103">공용 언어 런타임 형식에 대 한 형식 정의 만들고 해당 형식 정의 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c58f3-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c58f3-104">구문</span><span class="sxs-lookup"><span data-stu-id="c58f3-104">Syntax</span></span>  
  
```  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c58f3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c58f3-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="c58f3-106">[in] 유니코드에 대 한 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c58f3-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="c58f3-107">[in] `TypeDef` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c58f3-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="c58f3-108">이 비트 마스크의 `CoreTypeAttr` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c58f3-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="c58f3-109">[in] 기본 클래스의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c58f3-109">[in] The token of the base class.</span></span> <span data-ttu-id="c58f3-110">중 하나 이어야 합니다는 `mdTypeDef` 또는 `mdTypeRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c58f3-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="c58f3-111">[in] 이 클래스 또는 인터페이스를 구현 하는 인터페이스를 지정 하는 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c58f3-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="c58f3-112">[out] `mdTypeDef` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c58f3-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c58f3-113">설명</span><span class="sxs-lookup"><span data-stu-id="c58f3-113">Remarks</span></span>  
 <span data-ttu-id="c58f3-114">플래그 `dwTypeDefFlags` 생성 될 형식이 공용 형식 시스템 참조 형식 (클래스 또는 인터페이스) 또는 공용 형식 시스템 값 형식 인지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58f3-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="c58f3-115">제공 된 매개 변수에 따라이 메서드를 파생 작업으로 만들 수도 있습니다는 `mdInterfaceImpl` 이 형식에 의해 구현 되거나 상속 되는 각 인터페이스에 대 한 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c58f3-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="c58f3-116">그러나이 메서드는 반환 하지는 이러한 `mdInterfaceImpl` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c58f3-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="c58f3-117">클라이언트가 나중에 추가 하거나 수정 하려는 경우는 `mdInterfaceImpl` 토큰을 사용 하 여 해야는 `IMetaDataImport` 인터페이스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58f3-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="c58f3-118">COM 의미 체계를 사용 하려는 경우는 `[default]` 인터페이스에서 첫 번째 요소로 기본 인터페이스를 제공 해야 `rtkImplements`; 클래스에 설정 하는 사용자 지정 특성은 기본 인터페이스에 표시 됩니다 (되도록 항상 가정 된는 먼저 `mdInterfaceImpl` 클래스에 대해 선언 된 토큰)입니다.</span><span class="sxs-lookup"><span data-stu-id="c58f3-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="c58f3-119">각 요소는 `rtkImplements` 보류 배열는 `mdTypeDef` 또는 `mdTypeRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c58f3-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="c58f3-120">배열의 마지막 요소 여야 합니다 `mdTokenNil`합니다.</span><span class="sxs-lookup"><span data-stu-id="c58f3-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c58f3-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c58f3-121">Requirements</span></span>  
 <span data-ttu-id="c58f3-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c58f3-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c58f3-123">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c58f3-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c58f3-124">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="c58f3-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c58f3-125">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c58f3-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c58f3-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c58f3-126">See Also</span></span>  
 [<span data-ttu-id="c58f3-127">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c58f3-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="c58f3-128">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c58f3-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
