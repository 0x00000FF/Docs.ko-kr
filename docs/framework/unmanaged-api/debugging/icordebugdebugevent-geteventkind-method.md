---
title: ICorDebugDebugEvent::GetEventKind 메서드
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93dc268e65578a80fe8562f4c4d4fd71fa6db981
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711842"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="c6ec6-102">ICorDebugDebugEvent::GetEventKind 메서드</span><span class="sxs-lookup"><span data-stu-id="c6ec6-102">ICorDebugDebugEvent::GetEventKind Method</span></span>
<span data-ttu-id="c6ec6-103">이 `ICorDebugDebugEvent` 개체가 나타내는 이벤트의 종류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c6ec6-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6ec6-104">구문</span><span class="sxs-lookup"><span data-stu-id="c6ec6-104">Syntax</span></span>  
  
```  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6ec6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c6ec6-105">Parameters</span></span>  
 <span data-ttu-id="c6ec6-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="c6ec6-106">pDebugEventKind</span></span>  
 <span data-ttu-id="c6ec6-107">에 대 한 포인터를 [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) 이벤트의 형식을 나타내는 열거형 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="c6ec6-107">A pointer to a [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6ec6-108">설명</span><span class="sxs-lookup"><span data-stu-id="c6ec6-108">Remarks</span></span>  
 <span data-ttu-id="c6ec6-109">`pDebugEventKind`의 값에 따라 `QueryInterface`를 호출하여 추가 데이터를 포함하는 보다 정확한 디버그 이벤트 인터페이스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6ec6-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6ec6-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6ec6-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6ec6-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6ec6-111">Requirements</span></span>  
 <span data-ttu-id="c6ec6-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c6ec6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6ec6-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6ec6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6ec6-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6ec6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6ec6-115">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6ec6-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6ec6-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="c6ec6-116">See also</span></span>
- [<span data-ttu-id="c6ec6-117">ICorDebugDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6ec6-117">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="c6ec6-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6ec6-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
