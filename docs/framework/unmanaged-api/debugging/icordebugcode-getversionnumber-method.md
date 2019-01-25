---
title: ICorDebugCode::GetVersionNumber 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b383c322f1119ff13ac4df9a8dc0563d26dcf895
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499712"
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="6e8a0-102">ICorDebugCode::GetVersionNumber 메서드</span><span class="sxs-lookup"><span data-stu-id="6e8a0-102">ICorDebugCode::GetVersionNumber Method</span></span>
<span data-ttu-id="6e8a0-103">이 "ICorDebugCode"를 나타내는 코드의 버전을 식별 하는 1부터 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e8a0-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e8a0-104">구문</span><span class="sxs-lookup"><span data-stu-id="6e8a0-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32    *nVersion  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e8a0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e8a0-105">Parameters</span></span>  
 `nVersion`  
 <span data-ttu-id="6e8a0-106">[out] 코드의 버전 번호에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6e8a0-106">[out] A pointer to the version number of the code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e8a0-107">설명</span><span class="sxs-lookup"><span data-stu-id="6e8a0-107">Remarks</span></span>  
 <span data-ttu-id="6e8a0-108">버전 번호를 코드에 편집 하며 계속 하기 (EnC) 연산이 수행 될 때마다 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8a0-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e8a0-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e8a0-109">Requirements</span></span>  
 <span data-ttu-id="6e8a0-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e8a0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e8a0-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e8a0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e8a0-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e8a0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e8a0-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e8a0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e8a0-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="6e8a0-114">See also</span></span>

