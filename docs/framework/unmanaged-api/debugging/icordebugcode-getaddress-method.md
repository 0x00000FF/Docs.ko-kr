---
title: ICorDebugCode::GetAddress 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetAddress
helpviewer_keywords:
- GetAddress method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetAddress method [.NET Framework debugging]
ms.assetid: cc507cb0-df2e-49c2-b32e-0c3271a8df9a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 229bf968d21516d48468610c8f47367324fb6b13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695519"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="0f18a-102">ICorDebugCode::GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="0f18a-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="0f18a-103">이 "ICorDebugCode" 인터페이스를 나타내는 코드 세그먼트의 상대 가상 주소를 RVA ()를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f18a-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f18a-104">구문</span><span class="sxs-lookup"><span data-stu-id="0f18a-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f18a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f18a-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="0f18a-106">[out] 코드 세그먼트의 RVA 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0f18a-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f18a-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f18a-107">Requirements</span></span>  
 <span data-ttu-id="0f18a-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0f18a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f18a-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f18a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f18a-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f18a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f18a-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f18a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f18a-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="0f18a-112">See also</span></span>

