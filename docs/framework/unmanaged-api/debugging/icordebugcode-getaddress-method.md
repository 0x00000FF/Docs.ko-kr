---
title: "ICorDebugCode::GetAddress 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetAddress
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetAddress
helpviewer_keywords:
- GetAddress method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetAddress method [.NET Framework debugging]
ms.assetid: cc507cb0-df2e-49c2-b32e-0c3271a8df9a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 38524f806b5e1669dbeb58d4fdf3a586d19c7bd7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="ddd86-102">ICorDebugCode::GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="ddd86-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="ddd86-103">이 "ICorDebugCode" 인터페이스를 나타내는 코드 세그먼트의 (RVA) 상대 가상 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ddd86-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddd86-104">구문</span><span class="sxs-lookup"><span data-stu-id="ddd86-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ddd86-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ddd86-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="ddd86-106">[out] 코드 세그먼트의 RVA에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ddd86-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddd86-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ddd86-107">Requirements</span></span>  
 <span data-ttu-id="ddd86-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ddd86-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddd86-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ddd86-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ddd86-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddd86-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddd86-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddd86-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddd86-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ddd86-112">See Also</span></span>  
 
