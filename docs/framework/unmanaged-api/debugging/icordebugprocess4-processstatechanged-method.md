---
title: ICorDebugProcess4::ProcessStateChanged 메서드
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: b434f30fc187af8b118ac926fec96d28182b0bfc
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221429"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="ba676-102">ICorDebugProcess4::ProcessStateChanged 메서드</span><span class="sxs-lookup"><span data-stu-id="ba676-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="ba676-103">디버거 프로세스의 디버기의 실행을 계속 되는 ICorDebug 파이프라인에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ba676-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="ba676-104">구문</span><span class="sxs-lookup"><span data-stu-id="ba676-104">Syntax</span></span>

```
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

#### <a name="parameters"></a><span data-ttu-id="ba676-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ba676-105">Parameters</span></span>

 `eChange`

 <span data-ttu-id="ba676-106">[in] 멤버는 [CorDebugStateChange 열거형](cordebugstatechange-enumeration.md) 프로세스의 실행 상태 변경을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba676-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="ba676-107">설명</span><span class="sxs-lookup"><span data-stu-id="ba676-107">Remarks</span></span>

<span data-ttu-id="ba676-108">제공 된 메서드는의 일부는 `ICorDebugProcess4` 인터페이스 및 가상 메서드 테이블의 네 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba676-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="ba676-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ba676-109">Requirements</span></span>

 <span data-ttu-id="ba676-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ba676-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="ba676-111">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="ba676-111">**Header:** None</span></span>

 <span data-ttu-id="ba676-112">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="ba676-112">**Library:** None</span></span>
 
 <span data-ttu-id="ba676-113">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba676-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ba676-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="ba676-114">See also</span></span>

- [<span data-ttu-id="ba676-115">ICorDebugProcess4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba676-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="ba676-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba676-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ba676-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="ba676-117">Debugging</span></span>](index.md)
