---
title: ICorDebugILFrame2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame2
helpviewer_keywords: ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ef3cc011afebc98e57bffbf0cba2a90cd28e3a19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe2-interface1"></a><span data-ttu-id="ccbb3-102">ICorDebugILFrame2 Interface1</span><span class="sxs-lookup"><span data-stu-id="ccbb3-102">ICorDebugILFrame2 Interface1</span></span>
<span data-ttu-id="ccbb3-103">ICorDebugILFrame 인터페이스 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbb3-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ccbb3-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ccbb3-104">Methods</span></span>  
  
|<span data-ttu-id="ccbb3-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ccbb3-105">Method</span></span>|<span data-ttu-id="ccbb3-106">설명</span><span class="sxs-lookup"><span data-stu-id="ccbb3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ccbb3-107">EnumerateTypeParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="ccbb3-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="ccbb3-108">포함 된 ICorDebugTypeEnum 개체를 가져옵니다는 <xref:System.Type> 이 프레임에서 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ccbb3-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="ccbb3-109">RemapFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="ccbb3-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="ccbb3-110">새 MSIL 오프셋을 지정 하 여 편집된 된 함수를 다시 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbb3-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccbb3-111">설명</span><span class="sxs-lookup"><span data-stu-id="ccbb3-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ccbb3-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ccbb3-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccbb3-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ccbb3-113">Requirements</span></span>  
 <span data-ttu-id="ccbb3-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbb3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccbb3-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ccbb3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ccbb3-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccbb3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccbb3-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccbb3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccbb3-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ccbb3-118">See Also</span></span>  
 [<span data-ttu-id="ccbb3-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccbb3-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
