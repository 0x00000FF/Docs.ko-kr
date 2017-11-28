---
title: "ICorDebugEval2::RudeAbort 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.RudeAbort
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::RudeAbort
helpviewer_keywords:
- ICorDebugEval2::RudeAbort method [.NET Framework debugging]
- RudeAbort method, ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: 02468edf-d32b-4cb3-aaa8-3dd2abfc8b25
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1dd0d00338f3f9ff9ac63e84a29124913cc9febe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="d77ec-102">ICorDebugEval2::RudeAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="d77ec-102">ICorDebugEval2::RudeAbort Method</span></span>
<span data-ttu-id="d77ec-103">계산 중단이 `ICorDebugEval2` 현재 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d77ec-103">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d77ec-104">구문</span><span class="sxs-lookup"><span data-stu-id="d77ec-104">Syntax</span></span>  
  
```  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d77ec-105">설명</span><span class="sxs-lookup"><span data-stu-id="d77ec-105">Remarks</span></span>  
 <span data-ttu-id="d77ec-106">`RudeAbort`디버깅 세션 안전 하지 않은 상태로 둡니다 평가기 보유 하 고 있는 모든 잠금을 해제 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d77ec-106">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="d77ec-107">매우 주의 하 여이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d77ec-107">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d77ec-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d77ec-108">Requirements</span></span>  
 <span data-ttu-id="d77ec-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d77ec-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d77ec-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d77ec-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d77ec-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d77ec-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d77ec-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d77ec-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
