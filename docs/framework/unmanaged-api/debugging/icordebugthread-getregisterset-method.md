---
title: "ICorDebugThread::GetRegisterSet 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetRegisterSet
helpviewer_keywords:
- ICorDebugThread::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3b9b6260-98ac-4cfd-88e5-5d7614f94a0c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c3eb4acd546a2a87f7844a442110dc15343cc218
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="385b0-102">ICorDebugThread::GetRegisterSet 메서드</span><span class="sxs-lookup"><span data-stu-id="385b0-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="385b0-103">이 ICorDebugThread 개체의 활성 부분에 연관 된 레지스터 집합에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="385b0-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="385b0-104">구문</span><span class="sxs-lookup"><span data-stu-id="385b0-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="385b0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="385b0-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="385b0-106">[out] 주소에 대 한 포인터는 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) 이 스레드에의 활성 부분에 대 한 레지스터를 나타내는 인터페이스 개체를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="385b0-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="385b0-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="385b0-107">Requirements</span></span>  
 <span data-ttu-id="385b0-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="385b0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="385b0-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="385b0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="385b0-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="385b0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="385b0-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="385b0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
