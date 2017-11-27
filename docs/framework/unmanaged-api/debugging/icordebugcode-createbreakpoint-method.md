---
title: "ICorDebugCode::CreateBreakpoint 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.CreateBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 214d032129613230b8c55cdd286ea637227a626e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="8b8fc-102">ICorDebugCode::CreateBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="8b8fc-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="8b8fc-103">지정된 된 오프셋에이 코드 세그먼트에 중단점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8b8fc-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b8fc-104">구문</span><span class="sxs-lookup"><span data-stu-id="8b8fc-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b8fc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b8fc-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="8b8fc-106">[in] 중단점을 만드는 데 사용할 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="8b8fc-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="8b8fc-107">[out] 중단점을 나타내는 "ICorDebugFunctionBreakpoint" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8b8fc-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b8fc-108">설명</span><span class="sxs-lookup"><span data-stu-id="8b8fc-108">Remarks</span></span>  
 <span data-ttu-id="8b8fc-109">중단점 활성 상태 이면 먼저 프로세스 개체에 추가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b8fc-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="8b8fc-110">이 코드는 Microsoft MSIL (intermediate language) 코드 되 고는-just-in-time (JIT)-컴파일된 네이티브 버전 중단점이 코드의 JIT 컴파일된 코드도에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b8fc-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="8b8fc-111">(동일한는 코드를 JIT 컴파일된 나중에 있으면 true입니다.)</span><span class="sxs-lookup"><span data-stu-id="8b8fc-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b8fc-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b8fc-112">Requirements</span></span>  
 <span data-ttu-id="8b8fc-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8b8fc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b8fc-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b8fc-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b8fc-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b8fc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b8fc-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b8fc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b8fc-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b8fc-117">See Also</span></span>  
 
