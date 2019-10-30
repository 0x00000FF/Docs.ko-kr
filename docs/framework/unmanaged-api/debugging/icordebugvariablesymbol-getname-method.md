---
title: 'ICorDebugVariableSymbol:: GetName 메서드'
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
ms.openlocfilehash: 9bc32d3372710b4c4e92aa89df5e6e7839ad3078
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121010"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="d5d65-102">ICorDebugVariableSymbol:: GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="d5d65-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="d5d65-103">변수의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d5d65-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5d65-104">구문</span><span class="sxs-lookup"><span data-stu-id="d5d65-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5d65-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d5d65-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="d5d65-106">[in] `szName` 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d5d65-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="d5d65-107">[out] `szName` 버퍼에 실제로 기록된 문자 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d5d65-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="d5d65-108">변수 이름이 포함된 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d5d65-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5d65-109">주의</span><span class="sxs-lookup"><span data-stu-id="d5d65-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d5d65-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d65-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5d65-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d5d65-111">Requirements</span></span>  
 <span data-ttu-id="d5d65-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d5d65-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5d65-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5d65-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5d65-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5d65-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5d65-115">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5d65-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5d65-116">참조</span><span class="sxs-lookup"><span data-stu-id="d5d65-116">See also</span></span>

- [<span data-ttu-id="d5d65-117">ICorDebugVariableSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d5d65-117">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="d5d65-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d5d65-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
