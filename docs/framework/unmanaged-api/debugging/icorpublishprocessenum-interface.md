---
title: "ICorPublishProcessEnum 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcessEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcessEnum
helpviewer_keywords: ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 66e31911289d1ef8b590a0b7e7896adfa4998adc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="90cb8-102">ICorPublishProcessEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90cb8-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="90cb8-103">서브 클래스는 [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) 의 컬렉션을 이동 하는 메서드를 제공 하는 인터페이스 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="90cb8-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="90cb8-104">메서드</span><span class="sxs-lookup"><span data-stu-id="90cb8-104">Methods</span></span>  
  
|<span data-ttu-id="90cb8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="90cb8-105">Method</span></span>|<span data-ttu-id="90cb8-106">설명</span><span class="sxs-lookup"><span data-stu-id="90cb8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="90cb8-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="90cb8-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="90cb8-108">지정된 된 수의 가져옵니다 `ICorPublishProcess` 현재 위치부터 시작 하 고 컬렉션에서 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="90cb8-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90cb8-109">설명</span><span class="sxs-lookup"><span data-stu-id="90cb8-109">Remarks</span></span>  
 <span data-ttu-id="90cb8-110">`ICorPublishProcessEnum` 추상 인터페이스의 메서드를 구현 하는 인터페이스 [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="90cb8-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="90cb8-111">`ICorPublishProcessEnum` 인스턴스를 만든는 [icorpublish:: Enumprocesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="90cb8-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="90cb8-112">컬렉션이 `ICorPublishProcess` 시점 제공 된 필터 조건에 기반 개체는 `ICorPublishProcessEnum` 인스턴스를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="90cb8-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90cb8-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="90cb8-113">Requirements</span></span>  
 <span data-ttu-id="90cb8-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="90cb8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90cb8-115">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="90cb8-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="90cb8-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90cb8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90cb8-117">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90cb8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90cb8-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90cb8-118">See Also</span></span>  
 [<span data-ttu-id="90cb8-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90cb8-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="90cb8-120">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="90cb8-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
