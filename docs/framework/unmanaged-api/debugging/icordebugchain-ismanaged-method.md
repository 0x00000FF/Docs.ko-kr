---
title: "ICorDebugChain::IsManaged 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.IsManaged
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::IsManaged
helpviewer_keywords:
- ICorDebugChain::IsManaged method [.NET Framework debugging]
- IsManaged method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 17b389a0-1a4d-4e8a-8613-9bc1769930f9
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fe5736a1ca420eb361e062743ed93982e7ec3f29
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="274ca-102">ICorDebugChain::IsManaged 메서드</span><span class="sxs-lookup"><span data-stu-id="274ca-102">ICorDebugChain::IsManaged Method</span></span>
<span data-ttu-id="274ca-103">이 체인 관리 되는 코드를 실행 하 고 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="274ca-103">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="274ca-104">구문</span><span class="sxs-lookup"><span data-stu-id="274ca-104">Syntax</span></span>  
  
```  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="274ca-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="274ca-105">Parameters</span></span>  
 `pManaged`  
 <span data-ttu-id="274ca-106">[out] `true` 이 체인 관리 되는 코드를 실행 하는 경우 이렇게 하지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="274ca-106">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="274ca-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="274ca-107">Requirements</span></span>  
 <span data-ttu-id="274ca-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="274ca-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="274ca-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="274ca-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="274ca-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="274ca-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="274ca-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="274ca-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
