---
title: "IMetaDataEmit::Save 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.Save
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8a2e77ad9ce66a04ef0530dc41f9795c501eed9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="25359-102">IMetaDataEmit::Save 메서드</span><span class="sxs-lookup"><span data-stu-id="25359-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="25359-103">지정된 된 주소에서 파일에는 현재 범위에서 모든 메타 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="25359-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25359-104">구문</span><span class="sxs-lookup"><span data-stu-id="25359-104">Syntax</span></span>  
  
```  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="25359-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="25359-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="25359-106">[in] 에 저장 하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="25359-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="25359-107">이 값이 null 이면 위치 사용 된 메모리 내 복사본이 마지막으로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25359-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="25359-108">[in] 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25359-108">[in] Reserved.</span></span> <span data-ttu-id="25359-109">0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25359-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25359-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="25359-110">Requirements</span></span>  
 <span data-ttu-id="25359-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="25359-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25359-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="25359-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="25359-113">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="25359-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="25359-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25359-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25359-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25359-115">See Also</span></span>  
 [<span data-ttu-id="25359-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25359-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="25359-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25359-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
