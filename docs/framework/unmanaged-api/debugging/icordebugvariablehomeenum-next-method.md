---
title: ICorDebugVariableHomeEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d383d4bf0f3d203c331ff00981885cbc6c0c35d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519205"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="a358d-102">ICorDebugVariableHomeEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="a358d-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="a358d-103">지정 된 개수를 가져옵니다 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 지역 변수 및 함수에 인수에 대 한 정보를 포함 하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="a358d-103">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a358d-104">구문</span><span class="sxs-lookup"><span data-stu-id="a358d-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a358d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a358d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a358d-106">[in] 검색할 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a358d-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="a358d-107">각각 가리키는 포인터 배열을 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 로컬 변수 또는 함수의 인수에 대 한 정보를 제공 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a358d-107">An array of pointers, each of which points to a [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a358d-108">[out] 개체에 실제로 반환 된 인스턴스의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a358d-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a358d-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="a358d-109">Return Value</span></span>  
 <span data-ttu-id="a358d-110">메서드는 다음 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a358d-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="a358d-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a358d-111">HRESULT</span></span>|<span data-ttu-id="a358d-112">설명</span><span class="sxs-lookup"><span data-stu-id="a358d-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a358d-113">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a358d-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a358d-114">실제 인스턴스 수가 검색에 반영 된 대로 `pceltFetched`, 요청 된 인스턴스 수보다 작습니다.</span><span class="sxs-lookup"><span data-stu-id="a358d-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a358d-115">설명</span><span class="sxs-lookup"><span data-stu-id="a358d-115">Remarks</span></span>  
 <span data-ttu-id="a358d-116">합니다 [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) 메서드는 최대 검색 `celt` 열거자의 현재 위치부터 시작 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a358d-116">The [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="a358d-117">메서드는 반환 될 때 `pceltFetched` 검색 된 개체의 실제 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a358d-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a358d-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a358d-118">Requirements</span></span>  
 <span data-ttu-id="a358d-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a358d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a358d-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a358d-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a358d-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a358d-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a358d-122">**.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a358d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a358d-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="a358d-123">See also</span></span>
- [<span data-ttu-id="a358d-124">ICorDebugVariableHomeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a358d-124">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
- [<span data-ttu-id="a358d-125">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a358d-125">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
