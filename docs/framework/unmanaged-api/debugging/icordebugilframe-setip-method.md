---
title: ICorDebugILFrame::SetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a25e52c6b858aaa602ffade0e407b1aaf6e5c67e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995591"
---
# <a name="icordebugilframesetip-method"></a><span data-ttu-id="9430c-102">ICorDebugILFrame::SetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="9430c-102">ICorDebugILFrame::SetIP Method</span></span>
<span data-ttu-id="9430c-103">Microsoft의 MSIL (intermediate language) 코드에서 지정된 된 오프셋된 위치에 명령 포인터를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9430c-103">Sets the instruction pointer to the specified offset location in the Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9430c-104">구문</span><span class="sxs-lookup"><span data-stu-id="9430c-104">Syntax</span></span>  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9430c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9430c-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="9430c-106">MSIL 코드 내의 오프셋된 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="9430c-106">The offset location in the MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9430c-107">설명</span><span class="sxs-lookup"><span data-stu-id="9430c-107">Remarks</span></span>  
 <span data-ttu-id="9430c-108">에 대 한 호출 `SetIP` 즉시 모든 프레임을 현재 스레드에 대 한 체인을 무효화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9430c-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="9430c-109">디버거를 호출한 후 프레임 정보가 필요한 경우 `SetIP`, 새 스택 추적을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9430c-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="9430c-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 스택 프레임을 유효한 상태로 유지 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9430c-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="9430c-111">그러나 경우에 프레임 유효한 상태, 초기화 되지 않은 로컬 변수와 같은 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9430c-111">However, even if the frame is in a valid state, there still may be problems such as uninitialized local variables.</span></span> <span data-ttu-id="9430c-112">호출자는 실행 중인 프로그램의 일관성을 보장 하는 일을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9430c-112">The caller is responsible for ensuring the coherency of the running program.</span></span>  
  
 <span data-ttu-id="9430c-113">64 비트 플랫폼에서 명령 포인터를 이동할 수 없습니다 개를 `catch` 또는 `finally` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="9430c-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="9430c-114">경우 `SetIP` 라고 하는 64 비트 플랫폼에서 이러한 이동 되도록 실패를 나타내는 HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9430c-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9430c-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9430c-115">Requirements</span></span>  
 <span data-ttu-id="9430c-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9430c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9430c-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9430c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9430c-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9430c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9430c-119">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9430c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
