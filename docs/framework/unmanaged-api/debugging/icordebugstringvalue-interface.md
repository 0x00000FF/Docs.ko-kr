---
title: ICorDebugStringValue Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue
helpviewer_keywords:
- ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2814f6164f383c36bb5b8e20ce8996b30eef0f1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421702"
---
# <a name="icordebugstringvalue-interface1"></a><span data-ttu-id="785a5-102">ICorDebugStringValue Interface1</span><span class="sxs-lookup"><span data-stu-id="785a5-102">ICorDebugStringValue Interface1</span></span>
<span data-ttu-id="785a5-103">문자열 값에 적용 되는 ICorDebugHeapValue의 하위 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="785a5-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="785a5-104">메서드</span><span class="sxs-lookup"><span data-stu-id="785a5-104">Methods</span></span>  
  
|<span data-ttu-id="785a5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="785a5-105">Method</span></span>|<span data-ttu-id="785a5-106">설명</span><span class="sxs-lookup"><span data-stu-id="785a5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="785a5-107">GetLength 메서드</span><span class="sxs-lookup"><span data-stu-id="785a5-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="785a5-108">이 참조 하는 문자열의 문자 수를 가져옵니다 `ICorDebugStringValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="785a5-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="785a5-109">GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="785a5-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="785a5-110">이 참조 하는 문자열을 가져옵니다 `ICorDebugStringValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="785a5-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="785a5-111">설명</span><span class="sxs-lookup"><span data-stu-id="785a5-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="785a5-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="785a5-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="785a5-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="785a5-113">Requirements</span></span>  
 <span data-ttu-id="785a5-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="785a5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="785a5-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="785a5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="785a5-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="785a5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="785a5-117">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="785a5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="785a5-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="785a5-118">See Also</span></span>  
 [<span data-ttu-id="785a5-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="785a5-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
