---
title: IMetaDataImport::EnumMembers 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 88b8f874400d68110fa5e8fb66ca910b8e7231e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645966"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="c5c56-102">IMetaDataImport::EnumMembers 메서드</span><span class="sxs-lookup"><span data-stu-id="c5c56-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="c5c56-103">지정한 형식의 멤버를 나타내는 MemberDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c56-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5c56-104">구문</span><span class="sxs-lookup"><span data-stu-id="c5c56-104">Syntax</span></span>  
  
```  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5c56-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c5c56-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c5c56-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c5c56-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="c5c56-107">[in] 해당 멤버를 열거할 수는 형식을 나타내는 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c5c56-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="c5c56-108">[out] MemberDef 토큰을 보유 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c5c56-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c5c56-109">[in] `rMembers` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c5c56-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="c5c56-110">[out] 실제 MemberDef 토큰에서 반환 된 수가 `rMembers`합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c56-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5c56-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="c5c56-111">Return Value</span></span>  
  
|<span data-ttu-id="c5c56-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5c56-112">HRESULT</span></span>|<span data-ttu-id="c5c56-113">설명</span><span class="sxs-lookup"><span data-stu-id="c5c56-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c5c56-114">`EnumMembers` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c56-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c5c56-115">열거할 MemberDef 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5c56-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="c5c56-116">이런 경우 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="c5c56-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5c56-117">설명</span><span class="sxs-lookup"><span data-stu-id="c5c56-117">Remarks</span></span>  
 <span data-ttu-id="c5c56-118">클래스에 대 한 멤버의 컬렉션을 열거할 때 `EnumMembers` 클래스에서 직접 정의 된 멤버만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c56-118">When enumerating collections of members for a class, `EnumMembers` returns only members defined directly on the class.</span></span> <span data-ttu-id="c5c56-119">클래스 상속 된 해당 멤버에 대 한 구현을 제공 하는 경우에 클래스를 상속 하는 모든 멤버 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5c56-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="c5c56-120">상속 된 멤버를 열거 하려면 호출자에 게 상속 체인을 명시적으로 탐색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c56-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="c5c56-121">규칙의 상속 체인을 언어 또는 원래 메타 데이터를 내보낸 컴파일러에 따라 달라질 수 있는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c56-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5c56-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c5c56-122">Requirements</span></span>  
 <span data-ttu-id="c5c56-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c5c56-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5c56-124">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c5c56-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c5c56-125">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c5c56-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c5c56-126">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5c56-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5c56-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="c5c56-127">See also</span></span>
- [<span data-ttu-id="c5c56-128">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5c56-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c5c56-129">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5c56-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
