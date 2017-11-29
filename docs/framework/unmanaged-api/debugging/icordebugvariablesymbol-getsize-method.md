---
title: "ICorDebugVariableSymbol::GetSize 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ea4a77b08b12c3f067d51f9dfe2c961192c3354
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="6d224-102">ICorDebugVariableSymbol::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="6d224-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="6d224-103">변수의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6d224-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d224-104">구문</span><span class="sxs-lookup"><span data-stu-id="6d224-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d224-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6d224-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="6d224-106">변수의 크기를 포함하는 32비트 부호 없는 정수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6d224-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d224-107">설명</span><span class="sxs-lookup"><span data-stu-id="6d224-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d224-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d224-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d224-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d224-109">Requirements</span></span>  
 <span data-ttu-id="6d224-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6d224-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d224-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d224-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d224-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d224-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d224-113">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d224-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d224-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d224-114">See Also</span></span>  
 [<span data-ttu-id="6d224-115">ICorDebugVariableSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6d224-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="6d224-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6d224-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
