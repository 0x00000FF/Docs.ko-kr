---
title: ICorDebugThread::GetActiveFrame 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a1bbe5674ba11b5ee6033c65f229d698eff15ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420643"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="db1cc-102">ICorDebugThread::GetActiveFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="db1cc-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="db1cc-103">활성 (가장 최근) 프레임으로이 ICorDebugThread 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="db1cc-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db1cc-104">구문</span><span class="sxs-lookup"><span data-stu-id="db1cc-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="db1cc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="db1cc-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="db1cc-106">[out] 프레임을 나타내는 ICorDebugFrame 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="db1cc-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db1cc-107">설명</span><span class="sxs-lookup"><span data-stu-id="db1cc-107">Remarks</span></span>  
 <span data-ttu-id="db1cc-108">`ppFrame` 매개 변수가 없는 프레임이 현재 활성화 되어 있으면 null입니다.</span><span class="sxs-lookup"><span data-stu-id="db1cc-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db1cc-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="db1cc-109">Requirements</span></span>  
 <span data-ttu-id="db1cc-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="db1cc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db1cc-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db1cc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db1cc-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db1cc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db1cc-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db1cc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
