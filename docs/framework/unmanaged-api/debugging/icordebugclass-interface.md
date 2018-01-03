---
title: ICorDebugClass Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass
helpviewer_keywords: ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3998cf76430612759f69df07fb4f5afebd7a25ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugclass-interface1"></a><span data-ttu-id="a24df-102">ICorDebugClass Interface1</span><span class="sxs-lookup"><span data-stu-id="a24df-102">ICorDebugClass Interface1</span></span>
<span data-ttu-id="a24df-103">기본 또는 복합(즉, 사용자 정의) 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a24df-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="a24df-104">형식이 제네릭이면 `ICorDebugClass`는 인스턴스화되지 않은 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a24df-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a24df-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a24df-105">Methods</span></span>  
  
|<span data-ttu-id="a24df-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a24df-106">Method</span></span>|<span data-ttu-id="a24df-107">설명</span><span class="sxs-lookup"><span data-stu-id="a24df-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a24df-108">GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="a24df-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|<span data-ttu-id="a24df-109">이 클래스를 정의 하는 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a24df-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="a24df-110">GetStaticFieldValue 메서드</span><span class="sxs-lookup"><span data-stu-id="a24df-110">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="a24df-111">지정된 된 정적 필드의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a24df-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="a24df-112">GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="a24df-112">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|<span data-ttu-id="a24df-113">가져옵니다는 `TypeDef` 이 클래스에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a24df-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a24df-114">설명</span><span class="sxs-lookup"><span data-stu-id="a24df-114">Remarks</span></span>  
 <span data-ttu-id="a24df-115">`ICorDebugClass` 인터페이스는 인스턴스화되지 않은 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a24df-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="a24df-116">ICorDebugType 인터페이스는 인스턴스화된 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a24df-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="a24df-117">예를 들어 `Hashtable<K, V>` 표시 `ICorDebugClass`반면, `Hashtable<Int32, String>` 표시 `ICorDebugType`합니다.</span><span class="sxs-lookup"><span data-stu-id="a24df-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="a24df-118">제네릭이 아닌 형식은 둘 다로 표현 됩니다 `ICorDebugClass` 및 `ICorDebugType`합니다.</span><span class="sxs-lookup"><span data-stu-id="a24df-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="a24df-119">두 번째 인터페이스 형식 인스턴스화 처리 하는.NET Framework 버전 2.0에서에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a24df-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a24df-120">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a24df-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a24df-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a24df-121">Requirements</span></span>  
 <span data-ttu-id="a24df-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a24df-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a24df-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a24df-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a24df-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a24df-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a24df-125">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a24df-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a24df-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a24df-126">See Also</span></span>  
 [<span data-ttu-id="a24df-127">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a24df-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
