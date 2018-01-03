---
title: "ICorDebugEval::Abort 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.Abort
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 064febeec32e5c43b6b73ef2b3a44625f151eb48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="032ec-102">ICorDebugEval::Abort 메서드</span><span class="sxs-lookup"><span data-stu-id="032ec-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="032ec-103">이 ICorDebugEval 개체에서 현재 수행 중인 계산을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="032ec-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="032ec-104">구문</span><span class="sxs-lookup"><span data-stu-id="032ec-104">Syntax</span></span>  
  
```  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="032ec-105">설명</span><span class="sxs-lookup"><span data-stu-id="032ec-105">Remarks</span></span>  
 <span data-ttu-id="032ec-106">평가 중첩 되어 있고 한 최신 없는 경우는 `Abort` 메서드가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="032ec-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="032ec-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="032ec-107">Requirements</span></span>  
 <span data-ttu-id="032ec-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="032ec-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="032ec-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="032ec-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="032ec-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="032ec-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="032ec-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="032ec-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
