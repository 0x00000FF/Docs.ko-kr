---
title: "IMetaDataImport::FindMethod 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindMethod
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b081a5e3668110ea6281c245f507b56ac48b9ab5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="6c7df-102">IMetaDataImport::FindMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="6c7df-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="6c7df-103">토큰을 가져옵니다 한 methoddef 묶여 있는 메서드에 대 한 지정 된 <xref:System.Type> 올려진 지정 된 이름 및 메타 데이터 서명을 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7df-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c7df-104">구문</span><span class="sxs-lookup"><span data-stu-id="6c7df-104">Syntax</span></span>  
  
```  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c7df-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6c7df-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="6c7df-106">[in] `mdTypeDef` 검색할 멤버를 포함 하는 형식 (클래스 또는 인터페이스)에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7df-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="6c7df-107">이 값이 `mdTokenNil`, 다음 전역 함수에 대 한 조회가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c7df-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="6c7df-108">[in] 검색할 메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7df-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="6c7df-109">[in] 이진 메타 데이터 서명 메서드의 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7df-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="6c7df-110">[in] 바이트 크기 `pvSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7df-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="6c7df-111">[out] 일치 하는 MethodDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7df-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c7df-112">설명</span><span class="sxs-lookup"><span data-stu-id="6c7df-112">Remarks</span></span>  
 <span data-ttu-id="6c7df-113">바깥쪽 클래스 또는 인터페이스를 사용 하 여 메서드를 지정 (`td`), 해당 이름 (`szName`), 및 선택적 요소인 시그니처 (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="6c7df-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="6c7df-114">클래스 또는 인터페이스에 동일한 이름 가진 메서드가 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7df-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="6c7df-115">이 경우 전달 메서드 시그니처 고유 일치 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7df-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="6c7df-116">에 전달 된 서명을 `FindMethod` 서명에 특정 범위에 바인딩되어 있기 때문에 현재 범위에서 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7df-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="6c7df-117">서명을 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7df-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="6c7df-118">토큰은 로컬 TypeDef 테이블에 대 한 인덱스.</span><span class="sxs-lookup"><span data-stu-id="6c7df-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="6c7df-119">현재 범위의 컨텍스트 외부에서 런타임에 서명을 한에 입력으로 사용할 수는 없습니다 `FindMethod`합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7df-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="6c7df-120">`FindMethod`클래스 또는 인터페이스에 직접 정의 된 메서드만을 찾습니다. 상속 된 메서드를 찾지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7df-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c7df-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c7df-121">Requirements</span></span>  
 <span data-ttu-id="6c7df-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7df-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c7df-123">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6c7df-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6c7df-124">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6c7df-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6c7df-125">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c7df-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c7df-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c7df-126">See Also</span></span>  
 <xref:System.Reflection.MethodInfo>  
 [<span data-ttu-id="6c7df-127">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c7df-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="6c7df-128">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c7df-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
