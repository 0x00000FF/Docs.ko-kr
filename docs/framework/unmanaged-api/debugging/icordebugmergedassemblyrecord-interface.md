---
title: ICorDebugMergedAssemblyRecord 인터페이스
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1118c879da4376bda0c73368a8b15df4f7a3d014
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180468"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="98ea3-102">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98ea3-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="98ea3-103">병합된 어셈블리에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="98ea3-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="98ea3-104">메서드</span><span class="sxs-lookup"><span data-stu-id="98ea3-104">Methods</span></span>  
  
|<span data-ttu-id="98ea3-105">메서드</span><span class="sxs-lookup"><span data-stu-id="98ea3-105">Method</span></span>|<span data-ttu-id="98ea3-106">설명</span><span class="sxs-lookup"><span data-stu-id="98ea3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98ea3-107">GetCulture 메서드</span><span class="sxs-lookup"><span data-stu-id="98ea3-107">GetCulture Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="98ea3-108">어셈블리의 문화권 이름 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="98ea3-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="98ea3-109">GetIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="98ea3-109">GetIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="98ea3-110">어셈블리의 접두사 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="98ea3-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="98ea3-111">GetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="98ea3-111">GetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="98ea3-112">어셈블리의 공개 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="98ea3-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="98ea3-113">GetPublicKeyToken 메서드</span><span class="sxs-lookup"><span data-stu-id="98ea3-113">GetPublicKeyToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="98ea3-114">어셈블리의 공개 키 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="98ea3-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="98ea3-115">GetSimpleName 메서드</span><span class="sxs-lookup"><span data-stu-id="98ea3-115">GetSimpleName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="98ea3-116">어셈블리의 단순한 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="98ea3-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="98ea3-117">GetVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="98ea3-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="98ea3-118">어셈블리의 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="98ea3-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98ea3-119">설명</span><span class="sxs-lookup"><span data-stu-id="98ea3-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98ea3-120">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98ea3-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="98ea3-121">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="98ea3-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98ea3-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98ea3-122">Requirements</span></span>  
 <span data-ttu-id="98ea3-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="98ea3-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98ea3-124">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98ea3-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98ea3-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98ea3-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="98ea3-126">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="98ea3-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="98ea3-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="98ea3-127">See also</span></span>

- [<span data-ttu-id="98ea3-128">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98ea3-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="98ea3-129">디버깅</span><span class="sxs-lookup"><span data-stu-id="98ea3-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
