---
title: "ICorDebugCode::GetSize 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetSize
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 94c530015cc1770adf31c336dfb00eb06ffd70a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="9a874-102">ICorDebugCode::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="9a874-102">ICorDebugCode::GetSize Method</span></span>
<span data-ttu-id="9a874-103">"ICorDebugCode"이 표시 되는 이진 코드를 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9a874-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a874-104">구문</span><span class="sxs-lookup"><span data-stu-id="9a874-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a874-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9a874-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="9a874-106">[out] 이 이진 파일의 바이트 단위로 크기에 대 한 포인터 코드 `ICorDebugCode` 개체가 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="9a874-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a874-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a874-107">Requirements</span></span>  
 <span data-ttu-id="9a874-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a874-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a874-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a874-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a874-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a874-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a874-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a874-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a874-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a874-112">See Also</span></span>  
 
