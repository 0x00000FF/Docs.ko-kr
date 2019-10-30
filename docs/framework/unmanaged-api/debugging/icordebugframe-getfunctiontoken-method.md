---
title: ICorDebugFrame::GetFunctionToken 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunctionToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunctionToken
helpviewer_keywords:
- ICorDebugFrame::GetFunctionToken method [.NET Framework debugging]
- GetFunctionToken method [.NET Framework debugging]
ms.assetid: a46925b3-3bf8-404f-9f30-a86ae41032c1
topic_type:
- apiref
ms.openlocfilehash: e7821022e6966dbdea90d57b6899f09b2ed1964e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090522"
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="f63b0-102">ICorDebugFrame::GetFunctionToken 메서드</span><span class="sxs-lookup"><span data-stu-id="f63b0-102">ICorDebugFrame::GetFunctionToken Method</span></span>
<span data-ttu-id="f63b0-103">이 스택 프레임과 연결 된 코드를 포함 하는 함수에 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f63b0-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f63b0-104">구문</span><span class="sxs-lookup"><span data-stu-id="f63b0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f63b0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f63b0-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="f63b0-106">제한이 함수에 대 한 메타 데이터를 참조 하는 `mdMethodDef` 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f63b0-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f63b0-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f63b0-107">Requirements</span></span>  
 <span data-ttu-id="f63b0-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f63b0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f63b0-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f63b0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f63b0-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f63b0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f63b0-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f63b0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
