---
title: ICorDebugAssembly2::IsFullyTrusted 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2.IsFullyTrusted
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 895c8bc7b550fd063a9215c60f10f183e24bac83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402954"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="b2901-102">ICorDebugAssembly2::IsFullyTrusted 메서드</span><span class="sxs-lookup"><span data-stu-id="b2901-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="b2901-103">여부 어셈블리에 완전 신뢰가 부여 런타임 보안 시스템에서 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b2901-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2901-104">구문</span><span class="sxs-lookup"><span data-stu-id="b2901-104">Syntax</span></span>  
  
```  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2901-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b2901-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="b2901-106">[out] `true` 어셈블리 부여 된 경우 완전 신뢰는 런타임 보안 시스템; 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="b2901-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2901-107">설명</span><span class="sxs-lookup"><span data-stu-id="b2901-107">Remarks</span></span>  
 <span data-ttu-id="b2901-108">이 메서드는 HRESULT의 CORDBG_E_NOTREADY 어셈블리에 대 한 보안 정책을 아직 해결 되지 않았다고, 즉, 어셈블리의 코드가 없으면 경우 아직 실행을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2901-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2901-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2901-109">Requirements</span></span>  
 <span data-ttu-id="b2901-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2901-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2901-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2901-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2901-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2901-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2901-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2901-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
