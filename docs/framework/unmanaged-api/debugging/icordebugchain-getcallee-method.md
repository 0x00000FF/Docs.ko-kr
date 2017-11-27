---
title: "ICorDebugChain::GetCallee 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetCallee
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ed2bf8d8e91799fd0b01012d5d6e212d26a526be
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="770b6-102">ICorDebugChain::GetCallee 메서드</span><span class="sxs-lookup"><span data-stu-id="770b6-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="770b6-103">이 체인에 의해 호출 된 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="770b6-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="770b6-104">구문</span><span class="sxs-lookup"><span data-stu-id="770b6-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="770b6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="770b6-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="770b6-106">[out] 호출된 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="770b6-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="770b6-107">이 체인은 현재 실행 중인 경우 (즉,이 체인 반환할 호출된 체인에 대 한 기다리고 있지 않으면), `ppChain` null이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="770b6-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="770b6-108">설명</span><span class="sxs-lookup"><span data-stu-id="770b6-108">Remarks</span></span>  
 <span data-ttu-id="770b6-109">이 체인 호출된 체인이 실행을 다시 시작 하기 전에 반환할 되기를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="770b6-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="770b6-110">마샬링된 크로스 스레드 호출의 경우 다른 스레드에서 호출된 체인이 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="770b6-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="770b6-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="770b6-111">Requirements</span></span>  
 <span data-ttu-id="770b6-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="770b6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="770b6-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="770b6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="770b6-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="770b6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="770b6-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="770b6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
