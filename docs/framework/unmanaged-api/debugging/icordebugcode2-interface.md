---
title: ICorDebugCode2 Interface1
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
- ICorDebugCode2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2
helpviewer_keywords:
- ICorDebugCode2 interface [.NET Framework debugging]
ms.assetid: 9321903b-7dea-40d8-ba32-99016c00cc46
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 54cada8e8211b3837e30f3d058d54af1eaf96a83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcode2-interface1"></a><span data-ttu-id="50e7b-102">ICorDebugCode2 Interface1</span><span class="sxs-lookup"><span data-stu-id="50e7b-102">ICorDebugCode2 Interface1</span></span>
<span data-ttu-id="50e7b-103">"ICorDebugCode"의 기능을 확장 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="50e7b-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50e7b-104">메서드</span><span class="sxs-lookup"><span data-stu-id="50e7b-104">Methods</span></span>  
  
|<span data-ttu-id="50e7b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="50e7b-105">Method</span></span>|<span data-ttu-id="50e7b-106">설명</span><span class="sxs-lookup"><span data-stu-id="50e7b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50e7b-107">GetCodeChunks 메서드</span><span class="sxs-lookup"><span data-stu-id="50e7b-107">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="50e7b-108">이 코드 개체를 구성 하는 코드 청크를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="50e7b-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="50e7b-109">GetCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="50e7b-109">GetCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="50e7b-110">이 코드 개체의 중 하나에서 적시 (JIT)의 컴파일 또는 네이티브 이미지 생성기 (Ngen.exe)를 사용 하 여 생성 되었습니다는 조건을 지정 하는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="50e7b-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50e7b-111">설명</span><span class="sxs-lookup"><span data-stu-id="50e7b-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50e7b-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50e7b-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50e7b-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="50e7b-113">Requirements</span></span>  
 <span data-ttu-id="50e7b-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="50e7b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50e7b-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50e7b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50e7b-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50e7b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50e7b-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50e7b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50e7b-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50e7b-118">See Also</span></span>  
    
 [<span data-ttu-id="50e7b-119">ICorDebugCode3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="50e7b-119">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [<span data-ttu-id="50e7b-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="50e7b-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
