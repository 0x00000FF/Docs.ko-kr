---
title: ICorDebugAppDomain2 Interface1
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
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c811107fcf32696aee17810af06ac0b2ddc9102d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomain2-interface1"></a><span data-ttu-id="585fd-102">ICorDebugAppDomain2 Interface1</span><span class="sxs-lookup"><span data-stu-id="585fd-102">ICorDebugAppDomain2 Interface1</span></span>
<span data-ttu-id="585fd-103">배열, 포인터, 함수 포인터 및 참조 형식만 사용 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="585fd-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="585fd-104">이 인터페이스는 ICorDebugAppDomain 인터페이스의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="585fd-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="585fd-105">메서드</span><span class="sxs-lookup"><span data-stu-id="585fd-105">Methods</span></span>  
  
|<span data-ttu-id="585fd-106">메서드</span><span class="sxs-lookup"><span data-stu-id="585fd-106">Method</span></span>|<span data-ttu-id="585fd-107">설명</span><span class="sxs-lookup"><span data-stu-id="585fd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="585fd-108">GetArrayOrPointerType 메서드</span><span class="sxs-lookup"><span data-stu-id="585fd-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="585fd-109">지정된 된 형식, 포인터 또는 지정된 된 형식에 대 한 참조의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="585fd-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="585fd-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="585fd-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="585fd-111">지정 된 시그니처가 있는 함수에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="585fd-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="585fd-112">설명</span><span class="sxs-lookup"><span data-stu-id="585fd-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="585fd-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="585fd-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="585fd-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="585fd-114">Requirements</span></span>  
 <span data-ttu-id="585fd-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="585fd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="585fd-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="585fd-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="585fd-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="585fd-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="585fd-118">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="585fd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="585fd-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="585fd-119">See Also</span></span>  
 [<span data-ttu-id="585fd-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="585fd-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
