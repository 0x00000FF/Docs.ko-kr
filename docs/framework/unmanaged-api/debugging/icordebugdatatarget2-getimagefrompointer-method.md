---
title: ICorDebugDataTarget2::GetImageFromPointer 메서드
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2371072261c9c75436ab86d742ce75423587765
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969449"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="2fcd0-102">ICorDebugDataTarget2::GetImageFromPointer 메서드</span><span class="sxs-lookup"><span data-stu-id="2fcd0-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="2fcd0-103">모듈 기본 주소와 크기를 해당 모듈의 주소에서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2fcd0-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fcd0-104">구문</span><span class="sxs-lookup"><span data-stu-id="2fcd0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fcd0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2fcd0-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="2fcd0-106">모듈의 주소를 나타내는 [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2fcd0-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="2fcd0-107">제한이 모듈의 기준 주소를 나타내는 [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2fcd0-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="2fcd0-108">모듈 크기에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2fcd0-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fcd0-109">설명</span><span class="sxs-lookup"><span data-stu-id="2fcd0-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2fcd0-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fcd0-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fcd0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2fcd0-111">Requirements</span></span>  
 <span data-ttu-id="2fcd0-112">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2fcd0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fcd0-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2fcd0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2fcd0-114">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fcd0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fcd0-115">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fcd0-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fcd0-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="2fcd0-116">See also</span></span>

- [<span data-ttu-id="2fcd0-117">ICorDebugDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2fcd0-117">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="2fcd0-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2fcd0-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
