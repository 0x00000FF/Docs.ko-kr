---
title: ICorDebugMergedAssemblyRecord 인터페이스
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0f42b8d6eb1a35052b25fda6e7cc9c7d00836df
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559361"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="5ad2a-102">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ad2a-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="5ad2a-103">병합된 어셈블리에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5ad2a-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5ad2a-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5ad2a-104">Methods</span></span>  
  
|<span data-ttu-id="5ad2a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5ad2a-105">Method</span></span>|<span data-ttu-id="5ad2a-106">설명</span><span class="sxs-lookup"><span data-stu-id="5ad2a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5ad2a-107">GetCulture 메서드</span><span class="sxs-lookup"><span data-stu-id="5ad2a-107">GetCulture Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="5ad2a-108">어셈블리의 문화권 이름 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5ad2a-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="5ad2a-109">GetIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="5ad2a-109">GetIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="5ad2a-110">어셈블리의 접두사 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5ad2a-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="5ad2a-111">GetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="5ad2a-111">GetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="5ad2a-112">어셈블리의 공개 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5ad2a-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="5ad2a-113">GetPublicKeyToken 메서드</span><span class="sxs-lookup"><span data-stu-id="5ad2a-113">GetPublicKeyToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="5ad2a-114">어셈블리의 공개 키 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5ad2a-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="5ad2a-115">GetSimpleName 메서드</span><span class="sxs-lookup"><span data-stu-id="5ad2a-115">GetSimpleName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="5ad2a-116">어셈블리의 단순한 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5ad2a-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="5ad2a-117">GetVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="5ad2a-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="5ad2a-118">어셈블리의 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5ad2a-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ad2a-119">설명</span><span class="sxs-lookup"><span data-stu-id="5ad2a-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ad2a-120">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ad2a-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="5ad2a-121">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="5ad2a-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ad2a-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ad2a-122">Requirements</span></span>  
 <span data-ttu-id="5ad2a-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ad2a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ad2a-124">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ad2a-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ad2a-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ad2a-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ad2a-126">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ad2a-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ad2a-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="5ad2a-127">See also</span></span>
- [<span data-ttu-id="5ad2a-128">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ad2a-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="5ad2a-129">디버깅</span><span class="sxs-lookup"><span data-stu-id="5ad2a-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
