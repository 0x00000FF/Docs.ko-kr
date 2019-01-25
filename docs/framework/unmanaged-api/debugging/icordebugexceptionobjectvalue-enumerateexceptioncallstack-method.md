---
title: ICorDebugExceptionObjectValue::EnumerateExceptionCallStack 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 028787ef0b93811f42f6c5b28e10665ea12aa334
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727848"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="45fa8-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack 메서드</span><span class="sxs-lookup"><span data-stu-id="45fa8-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="45fa8-103">예외 개체에 포함 된 호출 스택에 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="45fa8-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45fa8-104">구문</span><span class="sxs-lookup"><span data-stu-id="45fa8-104">Syntax</span></span>  
  
```  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45fa8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="45fa8-105">Parameters</span></span>  
 <span data-ttu-id="45fa8-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="45fa8-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="45fa8-107">[out] 주소에 대 한 포인터를 [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) 인터페이스 개체는 관리 되는 예외 개체에 대 한 스택 추적 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="45fa8-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45fa8-108">설명</span><span class="sxs-lookup"><span data-stu-id="45fa8-108">Remarks</span></span>  
 <span data-ttu-id="45fa8-109">호출 스택 정보가 없는 경우 사용할 수 있는 메서드는 반환 `S_OK`, 및 [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) 길이가 0 인 유효한 열거자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45fa8-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="45fa8-110">메서드에 스택 추적 정보를 검색할 수 없는 경우 반환 값은 `E_FAIL` 없습니다 열거자가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45fa8-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="45fa8-111">합니다 [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) 개체는 스택 추적 데이터 디코딩는 `_stackTrace` 예외 개체의 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="45fa8-111">The [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45fa8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="45fa8-112">Requirements</span></span>  
 <span data-ttu-id="45fa8-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="45fa8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45fa8-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45fa8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45fa8-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45fa8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45fa8-116">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45fa8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45fa8-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="45fa8-117">See also</span></span>
- [<span data-ttu-id="45fa8-118">ICorDebugExceptionObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="45fa8-118">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)
- [<span data-ttu-id="45fa8-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="45fa8-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
