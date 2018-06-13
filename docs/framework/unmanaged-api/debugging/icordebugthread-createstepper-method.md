---
title: ICorDebugThread::CreateStepper 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 626f313c41c85e08901648f429d99c829ba35e2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419002"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="2a734-102">ICorDebugThread::CreateStepper 메서드</span><span class="sxs-lookup"><span data-stu-id="2a734-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="2a734-103">ICorDebugStepper이이 ICorDebugThread의 활성 프레임을 단계별로 수 있는 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2a734-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a734-104">구문</span><span class="sxs-lookup"><span data-stu-id="2a734-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a734-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2a734-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="2a734-106">[out] 주소에 대 한 포인터는 `ICorDebugStepper` 이 스레드의 활성 프레임을 단계별로 실행 하는 사용할 수 있는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2a734-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a734-107">설명</span><span class="sxs-lookup"><span data-stu-id="2a734-107">Remarks</span></span>  
 <span data-ttu-id="2a734-108">활성 프레임에는 관리 되지 않는 코드 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a734-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="2a734-109">`ICorDebugStepper` 인터페이스는 실제 단계별 실행을 수행 하는 데 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a734-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a734-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a734-110">Requirements</span></span>  
 <span data-ttu-id="2a734-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a734-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a734-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a734-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a734-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a734-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a734-114">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a734-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
