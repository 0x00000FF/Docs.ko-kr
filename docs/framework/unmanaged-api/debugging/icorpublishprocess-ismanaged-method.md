---
title: "ICorPublishProcess::IsManaged 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess.IsManaged
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 622781a6c1ad5d5efa3bb2d5227c4f5b845bf94e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="842dd-102">ICorPublishProcess::IsManaged 메서드</span><span class="sxs-lookup"><span data-stu-id="842dd-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="842dd-103">이 프로세스를 참조 하는지 여부를 나타내는 값을 가져옵니다 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) 관리 코드가 있는 것으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="842dd-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="842dd-104">구문</span><span class="sxs-lookup"><span data-stu-id="842dd-104">Syntax</span></span>  
  
```  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="842dd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="842dd-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="842dd-106">[out] 프로세스에 코드를 관리 하는지 여부를 나타내는 부울 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="842dd-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="842dd-107">값은 `true` 프로세스에 코드를 관리 하는 경우 이렇게 하지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="842dd-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="842dd-108">설명</span><span class="sxs-lookup"><span data-stu-id="842dd-108">Remarks</span></span>  
 <span data-ttu-id="842dd-109">현재 버전의 이후 `ICorPublishProcess` 관리 코드가 있는 프로세스에만 액세스할 수 있도록 `IsManaged` 항상 반환 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="842dd-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="842dd-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="842dd-110">Requirements</span></span>  
 <span data-ttu-id="842dd-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="842dd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="842dd-112">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="842dd-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="842dd-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="842dd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="842dd-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="842dd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="842dd-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="842dd-115">See Also</span></span>  
 [<span data-ttu-id="842dd-116">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="842dd-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
