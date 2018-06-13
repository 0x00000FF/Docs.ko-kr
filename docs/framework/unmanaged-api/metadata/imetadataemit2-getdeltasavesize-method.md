---
title: IMetaDataEmit2::GetDeltaSaveSize 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.GetDeltaSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ad6e565db634477e4f0382afdec12361ce7111a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446511"
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="d68be-102">IMetaDataEmit2::GetDeltaSaveSize 메서드</span><span class="sxs-lookup"><span data-stu-id="d68be-102">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>
<span data-ttu-id="d68be-103">편집 하며 계속 하기는 현재 세션의 결과로 생성 되는 메타 데이터 크기의 변화를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d68be-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d68be-104">구문</span><span class="sxs-lookup"><span data-stu-id="d68be-104">Syntax</span></span>  
  
```  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d68be-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d68be-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="d68be-106">[in] 중 하나는 [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) 필요한 전체 자릿수 수준을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d68be-106">[in] One of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="d68be-107">.NET Framework 버전 2.0에서는이 매개 변수는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d68be-107">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="d68be-108">[out] 메타 데이터의 크기 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d68be-108">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d68be-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d68be-109">Requirements</span></span>  
 <span data-ttu-id="d68be-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d68be-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d68be-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d68be-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d68be-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="d68be-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d68be-113">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d68be-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d68be-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d68be-114">See Also</span></span>  
 [<span data-ttu-id="d68be-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d68be-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="d68be-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d68be-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
