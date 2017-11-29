---
title: "ICorDebugStaticFieldSymbol::GetName 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: af3cea14e29c987d2d24d5adc803afd5b9084651
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="dbe6c-102">ICorDebugStaticFieldSymbol::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="dbe6c-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="dbe6c-103">정적 필드의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbe6c-104">구문</span><span class="sxs-lookup"><span data-stu-id="dbe6c-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dbe6c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dbe6c-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="dbe6c-106">[in] `szName` 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="dbe6c-107">[out] `szName` 버퍼에 실제로 기록된 문자 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="dbe6c-108">[out] 반환된 이름을 저장하는 문자 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbe6c-109">설명</span><span class="sxs-lookup"><span data-stu-id="dbe6c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dbe6c-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbe6c-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dbe6c-111">Requirements</span></span>  
 <span data-ttu-id="dbe6c-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbe6c-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbe6c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbe6c-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbe6c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbe6c-115">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbe6c-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbe6c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dbe6c-116">See Also</span></span>  
 [<span data-ttu-id="dbe6c-117">ICorDebugStaticFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dbe6c-117">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="dbe6c-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dbe6c-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
