---
title: ICorDebugComObjectValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugComObjectValue
helpviewer_keywords:
- ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4db005e1de043e60ffe958de732a5280fcccbea7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529949"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="2f51a-102">ICorDebugComObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f51a-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="2f51a-103">런타임 호출 가능 래퍼 (RCW)와 관련 된 정보를 검색 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f51a-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2f51a-104">메서드</span><span class="sxs-lookup"><span data-stu-id="2f51a-104">Methods</span></span>  
  
|<span data-ttu-id="2f51a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2f51a-105">Method</span></span>|<span data-ttu-id="2f51a-106">설명</span><span class="sxs-lookup"><span data-stu-id="2f51a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2f51a-107">GetCachedInterfacePointers 메서드</span><span class="sxs-lookup"><span data-stu-id="2f51a-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="2f51a-108">현재 RCW에서 캐시 된 원시 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2f51a-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="2f51a-109">GetCachedInterfaceTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="2f51a-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="2f51a-110">현재 개체에 대/소문자 되었거나으로 사용 하는 인터페이스 형식에 대 한 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f51a-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f51a-111">설명</span><span class="sxs-lookup"><span data-stu-id="2f51a-111">Remarks</span></span>  
 <span data-ttu-id="2f51a-112">디버거 호출 "ICorDebugValue" 인터페이스의 인스턴스는 RCW를 나타내는지 여부를 검사할 `QueryInterface` 에서 사용 하 여 "ICorDebugValue" `IID_ICorDebugComObjectValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="2f51a-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f51a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f51a-113">Requirements</span></span>  
 <span data-ttu-id="2f51a-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f51a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f51a-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f51a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f51a-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f51a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f51a-117">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f51a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f51a-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="2f51a-118">See also</span></span>
- [<span data-ttu-id="2f51a-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f51a-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2f51a-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="2f51a-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
