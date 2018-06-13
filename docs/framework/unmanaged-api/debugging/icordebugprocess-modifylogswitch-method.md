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
ms.openlocfilehash: 20ceed164631169b3a47809381b2cc4e630ae718
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418619"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="44613-102">ICorDebugProcess::ModifyLogSwitch 메서드</span><span class="sxs-lookup"><span data-stu-id="44613-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="44613-103">지정 된 로그 스위치의 심각도 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="44613-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44613-104">구문</span><span class="sxs-lookup"><span data-stu-id="44613-104">Syntax</span></span>  
  
```  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44613-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="44613-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="44613-106">[in] Log 스위치의 이름을 지정 하는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="44613-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="44613-107">[in] 지정 된 로그 스위치에 대해 설정할 심각도 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="44613-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44613-108">설명</span><span class="sxs-lookup"><span data-stu-id="44613-108">Remarks</span></span>  
 <span data-ttu-id="44613-109">이 메서드는 한 후에 유효는 [icordebugmanagedcallback:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) 콜백이 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="44613-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44613-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="44613-110">Requirements</span></span>  
 <span data-ttu-id="44613-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44613-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44613-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44613-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44613-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44613-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44613-114">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44613-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
