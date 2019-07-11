---
title: ICorDebugProcess::ModifyLogSwitch 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ModifyLogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ModifyLogSwitch
helpviewer_keywords:
- ICorDebugProcess::ModifyLogSwitch method [.NET Framework debugging]
- ModifyLogSwitch method [.NET Framework debugging]
ms.assetid: 5fd30875-555e-4e96-877b-5dd266cde7c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96db1ca115ffed47b5eb8eadd9c3d2f620060c4a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755455"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="2a105-102">ICorDebugProcess::ModifyLogSwitch 메서드</span><span class="sxs-lookup"><span data-stu-id="2a105-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="2a105-103">지정 된 로그 스위치의 심각도 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a105-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a105-104">구문</span><span class="sxs-lookup"><span data-stu-id="2a105-104">Syntax</span></span>  
  
```cpp  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a105-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2a105-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="2a105-106">[in] Log 스위치의 이름을 지정 하는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2a105-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="2a105-107">[in] 지정된 된 로그 스위치에 대해 설정할 심각도 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="2a105-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a105-108">설명</span><span class="sxs-lookup"><span data-stu-id="2a105-108">Remarks</span></span>  
 <span data-ttu-id="2a105-109">이 메서드는 한 후에 유효 합니다 [icordebugmanagedcallback:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) 콜백 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2a105-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a105-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a105-110">Requirements</span></span>  
 <span data-ttu-id="2a105-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2a105-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a105-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a105-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a105-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a105-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a105-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a105-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
