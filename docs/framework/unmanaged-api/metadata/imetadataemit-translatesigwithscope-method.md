---
title: IMetaDataEmit::TranslateSigWithScope 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.TranslateSigWithScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 71029d6ebfb3248da791d4371dfe3e39589af443
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049991"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="864f6-102">IMetaDataEmit::TranslateSigWithScope 메서드</span><span class="sxs-lookup"><span data-stu-id="864f6-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="864f6-103">현재 범위에 어셈블리를 가져오고 병합 된 범위에 대 한 새 메타 데이터 서명을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="864f6-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="864f6-104">구문</span><span class="sxs-lookup"><span data-stu-id="864f6-104">Syntax</span></span>  
  
```  
HRESULT TranslateSigWithScope (   
    [in]  IMetaDataAssemblyImport   *pAssemImport,   
    [in]  const void                *pbHashValue,   
    [in]  ULONG                     cbHashValue,   
    [in]  IMetaDataImport           *import,   
    [in]  PCCOR_SIGNATURE           pbSigBlob,   
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,   
    [in]  IMetaDataEmit             *emit,   
    [out] PCOR_SIGNATURE            pvTranslatedSig,   
    [in]  ULONG                     cbTranslatedSigMax,   
    [out] ULONG                     *pcbTranslatedSig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="864f6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="864f6-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="864f6-106">[in] \(서명을 정의 됨) 가져오기 어셈블리에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="864f6-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="864f6-107">[in] 어셈블리에 대 한 해시 blob입니다.</span><span class="sxs-lookup"><span data-stu-id="864f6-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="864f6-108">[in] 바이트 수가 `pbHashValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="864f6-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="864f6-109">[in] 가져오기 메타 데이터 범위에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="864f6-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="864f6-110">[in] 가져올 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="864f6-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="864f6-111">[in] 크기 (바이트)의 `pbSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="864f6-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="864f6-112">[in] 내보내기 어셈블리에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="864f6-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="864f6-113">[in] 내보내기 메타 데이터 범위에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="864f6-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="864f6-114">[out] 번역 된 시그니처 blob을 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="864f6-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="864f6-115">[in] 용량 (바이트)에서의 `pvTranslatedSig`합니다.</span><span class="sxs-lookup"><span data-stu-id="864f6-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="864f6-116">[out] 번역 된 서명의 실제 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="864f6-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="864f6-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="864f6-117">Requirements</span></span>  
 <span data-ttu-id="864f6-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="864f6-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="864f6-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="864f6-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="864f6-120">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="864f6-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="864f6-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="864f6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="864f6-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="864f6-122">See also</span></span>

- [<span data-ttu-id="864f6-123">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="864f6-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="864f6-124">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="864f6-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="864f6-125">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="864f6-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="864f6-126">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="864f6-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="864f6-127">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="864f6-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
