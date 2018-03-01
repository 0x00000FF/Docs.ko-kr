---
title: "ICorDebugMDA 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9c53e03acddc5d732a684cf825bce49a65bb4c31
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="61514-102">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61514-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="61514-103">MDA(관리 디버깅 도우미) 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="61514-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="61514-104">메서드</span><span class="sxs-lookup"><span data-stu-id="61514-104">Methods</span></span>  
  
|<span data-ttu-id="61514-105">메서드</span><span class="sxs-lookup"><span data-stu-id="61514-105">Method</span></span>|<span data-ttu-id="61514-106">설명</span><span class="sxs-lookup"><span data-stu-id="61514-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="61514-107">GetDescription 메서드</span><span class="sxs-lookup"><span data-stu-id="61514-107">GetDescription Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|<span data-ttu-id="61514-108">이 MDA에 대 한 설명을 포함 하는 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="61514-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="61514-109">GetFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="61514-109">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|<span data-ttu-id="61514-110">이 MDA와 관련 된 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="61514-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="61514-111">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="61514-111">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|<span data-ttu-id="61514-112">이 MDA의 이름을 포함 하는 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="61514-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="61514-113">GetOSThreadId 메서드</span><span class="sxs-lookup"><span data-stu-id="61514-113">GetOSThreadId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|<span data-ttu-id="61514-114">이 MDA가 실행 되는 운영 체제 스레드 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="61514-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="61514-115">GetXML 메서드</span><span class="sxs-lookup"><span data-stu-id="61514-115">GetXML Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|<span data-ttu-id="61514-116">이 MDA에 연결 된 전체 XML 스트림을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="61514-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61514-117">설명</span><span class="sxs-lookup"><span data-stu-id="61514-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61514-118">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61514-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61514-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="61514-119">Requirements</span></span>  
 <span data-ttu-id="61514-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="61514-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61514-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61514-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61514-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61514-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61514-123">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61514-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61514-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61514-124">See Also</span></span>  
 [<span data-ttu-id="61514-125">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61514-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="61514-126">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="61514-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
