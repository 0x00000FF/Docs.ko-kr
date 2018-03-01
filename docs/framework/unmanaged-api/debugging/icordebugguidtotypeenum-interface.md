---
title: "ICorDebugGuidToTypeEnum 인터페이스"
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
- ICorDebugGuidToTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum
helpviewer_keywords:
- ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: aa32b12b-05fc-4ea8-a904-adae25034269
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9993a5aaaef3d5b83d21e3641029af12119188da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="4b8fb-102">ICorDebugGuidToTypeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b8fb-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="4b8fb-103">Guid 집합과 ICorDebugType 인스턴스에 의해 표시 되는 해당 형식 간의 매핑을 정의 하는 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b8fb-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="4b8fb-104">이 인터페이스는 ICorDebugEnum 인터페이스에서 메서드를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="4b8fb-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4b8fb-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4b8fb-105">Methods</span></span>  
  
|<span data-ttu-id="4b8fb-106">메서드</span><span class="sxs-lookup"><span data-stu-id="4b8fb-106">Method</span></span>|<span data-ttu-id="4b8fb-107">설명</span><span class="sxs-lookup"><span data-stu-id="4b8fb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4b8fb-108">Icordebugguidtotypeenum:: Next</span><span class="sxs-lookup"><span data-stu-id="4b8fb-108">ICorDebugGuidToTypeEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="4b8fb-109">지정된 된 수의 가져옵니다 [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Guid 형식 정보를 매핑하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="4b8fb-109">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b8fb-110">설명</span><span class="sxs-lookup"><span data-stu-id="4b8fb-110">Remarks</span></span>  
 <span data-ttu-id="4b8fb-111">`ICorDebugGuidToTypeEnum` 인터페이스 개체를 호출 하 여 검색할 수는 [icordebugappdomain3:: Getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="4b8fb-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="4b8fb-112">디버거는이 인터페이스를 호출할 수 [다음](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) 를 검색할 메서드 [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) 의 매핑을 나타내는 개체의 표현을 관리 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 형식이 로드에 에 대 한 호출에 사용 되는 응용 프로그램 도메인에서 [icordebugappdomain3:: Getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="4b8fb-112">A debugger can call this interface's [Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b8fb-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4b8fb-113">Requirements</span></span>  
 <span data-ttu-id="4b8fb-114">**플랫폼:**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b8fb-114">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="4b8fb-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b8fb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b8fb-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b8fb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b8fb-117">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b8fb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b8fb-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b8fb-118">See Also</span></span>  
 [<span data-ttu-id="4b8fb-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b8fb-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
