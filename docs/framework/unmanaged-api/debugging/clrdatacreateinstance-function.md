---
title: CLRDataCreateInstance 함수
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- COM
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c22d9bf286a2241b0c1c5512e29532a01032cb3d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648874"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="791d9-102">CLRDataCreateInstance 함수</span><span class="sxs-lookup"><span data-stu-id="791d9-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="791d9-103">지정 된 대상 항목에 대 한 인터페이스 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="791d9-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="791d9-104">구문</span><span class="sxs-lookup"><span data-stu-id="791d9-104">Syntax</span></span>  
  
```  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="791d9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="791d9-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="791d9-106">[in] 인스턴스화할 인터페이스의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="791d9-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="791d9-107">[in] 사용자가 구현한 포인터로 [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) 인터페이스 개체를 만들 대상 항목을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="791d9-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="791d9-108">[out] 반환 된 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="791d9-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="791d9-109">설명</span><span class="sxs-lookup"><span data-stu-id="791d9-109">Remarks</span></span>  
 <span data-ttu-id="791d9-110">`ICLRDataTarget` 개체 작성기는 디버깅 응용 프로그램에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="791d9-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="791d9-111">구현을 표시 되는 대상 항목의 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="791d9-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="791d9-112">프로세스, 메모리 덤프, 원격 컴퓨터 및 등 대상 항목 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="791d9-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="791d9-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="791d9-113">Requirements</span></span>  
 <span data-ttu-id="791d9-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="791d9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="791d9-115">**헤더:** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="791d9-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="791d9-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="791d9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="791d9-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="791d9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="791d9-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="791d9-118">See also</span></span>
- [<span data-ttu-id="791d9-119">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="791d9-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
