---
title: IMethodMalloc 인터페이스
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6f5c21d329ed35f82e36c2d88ac911401799e820
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596022"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="21674-102">IMethodMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21674-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="21674-103">새 Microsoft MSIL (intermediate language) 함수 본문에 대 한 메모리를 할당 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="21674-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21674-104">`IMethodMalloc` 인터페이스는 간단한 메모리 할당자입니다.</span><span class="sxs-lookup"><span data-stu-id="21674-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="21674-105">메모리를 할당할 수 있지만 해제할 수는 없습니다 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21674-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="21674-106">메서드</span><span class="sxs-lookup"><span data-stu-id="21674-106">Methods</span></span>  
  
|<span data-ttu-id="21674-107">메서드</span><span class="sxs-lookup"><span data-stu-id="21674-107">Method</span></span>|<span data-ttu-id="21674-108">설명</span><span class="sxs-lookup"><span data-stu-id="21674-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="21674-109">Alloc 메서드</span><span class="sxs-lookup"><span data-stu-id="21674-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="21674-110">새 MSIL 함수 본문에 지정된 된 양의 메모리를 할당 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="21674-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21674-111">설명</span><span class="sxs-lookup"><span data-stu-id="21674-111">Remarks</span></span>  
 <span data-ttu-id="21674-112">각 할당자는 특정 모듈 및 모듈의 기본부터 양수 오프셋에서 함수 본문 되도록 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="21674-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="21674-113">모듈의 기본 메모리 할당자를 사용 하 여 함수 본문에만 메모리를 할당 해야 하므로 귀중 한를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21674-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21674-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="21674-114">Requirements</span></span>  
 <span data-ttu-id="21674-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="21674-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21674-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="21674-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="21674-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21674-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21674-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21674-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21674-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="21674-119">See also</span></span>
- [<span data-ttu-id="21674-120">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21674-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
