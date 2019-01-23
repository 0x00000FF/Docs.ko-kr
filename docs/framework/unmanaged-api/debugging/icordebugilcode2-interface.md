---
title: ICorDebugILCode2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugILCode2
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d511999cac312c785e528cda24c215555a62ae76
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491170"
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="2b6f2-102">ICorDebugILCode2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b6f2-102">ICorDebugILCode2 Interface</span></span>
<span data-ttu-id="2b6f2-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="2b6f2-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="2b6f2-104">논리적으로 확장 합니다 [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) 인터페이스 함수의 로컬 변수 서명에 대 한 토큰을 반환 하 고 프로파일러의 계측 된 IL (중간 언어)을 매핑하는 방법을 제공 하기 위해 원래 메서드 IL 오프셋 오프셋 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f2-104">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2b6f2-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2b6f2-105">Methods</span></span>  
  
|<span data-ttu-id="2b6f2-106">메서드</span><span class="sxs-lookup"><span data-stu-id="2b6f2-106">Method</span></span>|<span data-ttu-id="2b6f2-107">설명</span><span class="sxs-lookup"><span data-stu-id="2b6f2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2b6f2-108">GetInstrumentedILMap 메서드</span><span class="sxs-lookup"><span data-stu-id="2b6f2-108">GetInstrumentedILMap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="2b6f2-109">이 인스턴스에 대해 프로파일러가 계측한 IL 오프셋에서 원래 메서드 IL 오프셋으로의 맵을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f2-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="2b6f2-110">GetLocalVarSigToken 메서드</span><span class="sxs-lookup"><span data-stu-id="2b6f2-110">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="2b6f2-111">이 인스턴스로 표시되는 함수의 로컬 변수 서명에 대한 메타데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f2-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2b6f2-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b6f2-112">Requirements</span></span>  
 <span data-ttu-id="2b6f2-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b6f2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b6f2-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b6f2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b6f2-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b6f2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b6f2-116">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b6f2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b6f2-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="2b6f2-117">See also</span></span>
- [<span data-ttu-id="2b6f2-118">ICorDebugILCode 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b6f2-118">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)
- [<span data-ttu-id="2b6f2-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b6f2-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2b6f2-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="2b6f2-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
