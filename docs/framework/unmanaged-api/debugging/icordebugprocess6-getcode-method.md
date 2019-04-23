---
title: ICorDebugProcess6::GetCode 메서드
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7349a20da35eb0b87894440026a0974d49ae2aa0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097299"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="b1e15-102">ICorDebugProcess6::GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="b1e15-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="b1e15-103">특정 코드 주소에서 관리 코드에 대한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b1e15-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1e15-104">구문</span><span class="sxs-lookup"><span data-stu-id="b1e15-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1e15-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b1e15-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="b1e15-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) 관리 코드 세그먼트의 시작 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b1e15-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="b1e15-107">[out] 관리 코드의 세그먼트를 나타내는 "ICorDebugCode" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b1e15-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1e15-108">설명</span><span class="sxs-lookup"><span data-stu-id="b1e15-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1e15-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1e15-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1e15-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b1e15-110">Requirements</span></span>  
 <span data-ttu-id="b1e15-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b1e15-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1e15-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1e15-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1e15-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1e15-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1e15-114">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1e15-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e15-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="b1e15-115">See also</span></span>

- [<span data-ttu-id="b1e15-116">ICorDebugProcess6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1e15-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="b1e15-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1e15-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
