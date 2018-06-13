---
title: ICLRDataEnumMemoryRegions::EnumMemoryRegions 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16d91156427c2ef7bdabd5ab11b01894fbced64c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406617"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="19c24-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions 메서드</span><span class="sxs-lookup"><span data-stu-id="19c24-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="19c24-103">메모리의 지정 된 영역을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="19c24-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19c24-104">구문</span><span class="sxs-lookup"><span data-stu-id="19c24-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19c24-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="19c24-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="19c24-106">[in] 에 대 한 포인터는 [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) 인스턴스 결과의 디버거를 알리기 위해 열거 되 고 각 메모리 영역에 대 한이 메서드에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19c24-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="19c24-107">메모리 영역의 열거에는 콜백에 실패 했음을 의미 하는 경우에 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19c24-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="19c24-108">[in] 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19c24-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="19c24-109">[in] 값은 [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) 를 열거 하는 메모리 영역을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="19c24-109">[in] A value of the [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19c24-110">설명</span><span class="sxs-lookup"><span data-stu-id="19c24-110">Remarks</span></span>  
 <span data-ttu-id="19c24-111">이 메서드를 사용 하 여 지정 된 [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) 결과의 호출자에 게 알리기 위해 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="19c24-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19c24-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19c24-112">Requirements</span></span>  
 <span data-ttu-id="19c24-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="19c24-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19c24-114">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="19c24-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="19c24-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19c24-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19c24-116">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19c24-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19c24-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19c24-117">See Also</span></span>  
 [<span data-ttu-id="19c24-118">ICLRDataEnumMemoryRegions 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19c24-118">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
