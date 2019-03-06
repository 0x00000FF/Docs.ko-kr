---
title: ICorDebugChain::IsManaged 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::IsManaged
helpviewer_keywords:
- ICorDebugChain::IsManaged method [.NET Framework debugging]
- IsManaged method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 17b389a0-1a4d-4e8a-8613-9bc1769930f9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a27ea95ca78f7db8f67ec2a13f02767e67619e97
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488060"
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="779b8-102">ICorDebugChain::IsManaged 메서드</span><span class="sxs-lookup"><span data-stu-id="779b8-102">ICorDebugChain::IsManaged Method</span></span>
<span data-ttu-id="779b8-103">이 체인 관리 코드를 실행 중인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="779b8-103">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="779b8-104">구문</span><span class="sxs-lookup"><span data-stu-id="779b8-104">Syntax</span></span>  
  
```  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="779b8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="779b8-105">Parameters</span></span>  
 `pManaged`  
 <span data-ttu-id="779b8-106">[out] `true` 이 체인은 관리 되는 코드를 실행 하는 경우이 고, 그렇지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="779b8-106">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="779b8-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="779b8-107">Requirements</span></span>  
 <span data-ttu-id="779b8-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="779b8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="779b8-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="779b8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="779b8-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="779b8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="779b8-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="779b8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
