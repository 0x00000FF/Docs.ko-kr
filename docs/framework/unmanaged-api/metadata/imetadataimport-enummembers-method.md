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
ms.openlocfilehash: de4bf2cf647682062fbacb4484ffae905d1b7995
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835371"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="d9957-102">IMetaDataImport::EnumMembers 메서드</span><span class="sxs-lookup"><span data-stu-id="d9957-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="d9957-103">지정한 형식의 멤버를 나타내는 MemberDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="d9957-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9957-104">구문</span><span class="sxs-lookup"><span data-stu-id="d9957-104">Syntax</span></span>  
  
```  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9957-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d9957-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d9957-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d9957-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="d9957-107">[in] 해당 멤버를 열거할 수는 형식을 나타내는 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d9957-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="d9957-108">[out] MemberDef 토큰을 보유 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d9957-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d9957-109">[in] `rMembers` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="d9957-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d9957-110">[out] 실제 MemberDef 토큰에서 반환 된 수가 `rMembers`합니다.</span><span class="sxs-lookup"><span data-stu-id="d9957-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9957-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="d9957-111">Return Value</span></span>  
  
|<span data-ttu-id="d9957-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9957-112">HRESULT</span></span>|<span data-ttu-id="d9957-113">설명</span><span class="sxs-lookup"><span data-stu-id="d9957-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d9957-114">`EnumMembers` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9957-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d9957-115">열거할 MemberDef 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9957-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="d9957-116">이런 경우 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="d9957-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9957-117">설명</span><span class="sxs-lookup"><span data-stu-id="d9957-117">Remarks</span></span>  
 <span data-ttu-id="d9957-118">클래스에 대 한 멤버의 컬렉션을 열거 하는 동안 `EnumMembers` 멤버만 반환 합니다 (필드 및 메서드를 하지만 **하지** 속성 또는 이벤트) 클래스에 직접 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9957-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="d9957-119">클래스 상속 된 해당 멤버에 대 한 구현을 제공 하는 경우에 클래스를 상속 하는 모든 멤버 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9957-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="d9957-120">상속 된 멤버를 열거 하려면 호출자에 게 상속 체인을 명시적으로 탐색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9957-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="d9957-121">규칙의 상속 체인을 언어 또는 원래 메타 데이터를 내보낸 컴파일러에 따라 달라질 수 있는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9957-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>
 
 <span data-ttu-id="d9957-122">속성 및 이벤트에서 열거 되지 않습니다 `EnumMembers`합니다.</span><span class="sxs-lookup"><span data-stu-id="d9957-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="d9957-123">이러한 열거를 사용 하 여 [EnumProperties](imetadataimport-enumproperties-method.md) 하거나 [EnumEvents](imetadataimport-enumevents-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d9957-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="d9957-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d9957-124">Requirements</span></span>  
 <span data-ttu-id="d9957-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d9957-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9957-126">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d9957-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9957-127">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d9957-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9957-128">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9957-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9957-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="d9957-129">See also</span></span>
- [<span data-ttu-id="d9957-130">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d9957-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d9957-131">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d9957-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
