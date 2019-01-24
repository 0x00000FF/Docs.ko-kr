---
title: IMetaDataEmit::GetSaveSize 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 164cdc5c04a55e9c33dda51e10dfb37f38ec1b6d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746546"
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="66e47-102">IMetaDataEmit::GetSaveSize 메서드</span><span class="sxs-lookup"><span data-stu-id="66e47-102">IMetaDataEmit::GetSaveSize Method</span></span>
<span data-ttu-id="66e47-103">현재 범위에서 어셈블리 및 해당 메타 데이터의 이진 예상된 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="66e47-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66e47-104">구문</span><span class="sxs-lookup"><span data-stu-id="66e47-104">Syntax</span></span>  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66e47-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="66e47-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="66e47-106">[in] 값을 [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) 정확 하거나 대략적인 크기를 가져올 것인지를 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="66e47-106">[in] A value of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="66e47-107">세 개의 값이 유효한: cssAccurate, cssQuick, 및 cssDiscardTransientCAs:</span><span class="sxs-lookup"><span data-stu-id="66e47-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
-   <span data-ttu-id="66e47-108">cssAccurate 정확한 저장 크기를 반환 하지만 계산 하는 데 시간이 오래 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="66e47-108">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
-   <span data-ttu-id="66e47-109">cssQuick은 안전을 위해 패딩 크기를 반환 하지만 계산 시간이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="66e47-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
-   <span data-ttu-id="66e47-110">cssDiscardTransientCAs 지시 `GetSaveSize` 는 발생할 수 있습니다 제거 사용자 지정 특성을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e47-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="66e47-111">[out] 파일을 저장 하는 데 필요한 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="66e47-111">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66e47-112">설명</span><span class="sxs-lookup"><span data-stu-id="66e47-112">Remarks</span></span>  
 <span data-ttu-id="66e47-113">`GetSaveSize` 하는 데 필요한 바이트를 현재 범위에서 어셈블리 및 해당 모든 메타 데이터를 저장 공간을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e47-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="66e47-114">(에 대 한 호출을 [imetadataemit:: Savetostream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) 메서드는이 바이트 수를 내보냅니다.)</span><span class="sxs-lookup"><span data-stu-id="66e47-114">(A call to the [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="66e47-115">호출자가 구현 하는 경우는 [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) 인터페이스 (통해 [imetadataemit:: Sethandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) 하거나 [imetadataemit:: 병합](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` 두 가지 단계로 수행 됩니다 최적화 하 고 압축 메타 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="66e47-115">If the caller implements the [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="66e47-116">그렇지 않으면 없습니다 최적화가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e47-116">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="66e47-117">최적화를 수행 하는 경우 첫 번째 패스는 단순히 가져올 때 검색의 성능을 조정 하기 위해 메타 데이터 구조를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e47-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="66e47-118">이 단계는 일반적으로 나중에 참조할 수에 대 한 도구에서 유지 하는 토큰이 유효 하지 않습니다는 부작용으로 레코드가 이동에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e47-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="66e47-119">하지만 메타 데이터를 알리지 않습니다 토큰 변경 될 때까지 호출자에 게 두 번째 패스 후.</span><span class="sxs-lookup"><span data-stu-id="66e47-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="66e47-120">두 번째 단계에서는 다양 한 최적화가 수행 됩니다 (초기 바인딩)를 최적화 하는 등의 메타 데이터의 전체 크기를 줄이기 위한 `mdTypeRef` 고 `mdMemberRef` 참조 형식 또는 멤버에 선언 된 경우 토큰을 현재 메타 데이터 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="66e47-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="66e47-121">이 단계에서는 또 다른 토큰 매핑이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="66e47-121">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="66e47-122">이 단계 후 메타 데이터 엔진에 알립니다. 호출자를 통해 해당 `IMapToken` 인터페이스의 토큰 값을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e47-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66e47-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="66e47-123">Requirements</span></span>  
 <span data-ttu-id="66e47-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="66e47-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66e47-125">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="66e47-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="66e47-126">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="66e47-126">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="66e47-127">**.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66e47-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66e47-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="66e47-128">See also</span></span>
- [<span data-ttu-id="66e47-129">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66e47-129">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="66e47-130">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66e47-130">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
