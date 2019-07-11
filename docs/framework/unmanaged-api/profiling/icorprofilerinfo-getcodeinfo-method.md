---
title: ICorProfilerInfo::GetCodeInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCodeInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCodeInfo
helpviewer_keywords:
- GetCodeInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetCodeInfo method [.NET Framework profiling]
ms.assetid: 90140b0f-a926-4a7e-b6fa-23e05f703cce
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2cc587edf763a352501a0d9097bdab2c54658d98
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762850"
---
# <a name="icorprofilerinfogetcodeinfo-method"></a><span data-ttu-id="fc85a-102">ICorProfilerInfo::GetCodeInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="fc85a-102">ICorProfilerInfo::GetCodeInfo Method</span></span>
<span data-ttu-id="fc85a-103">지정된 함수 ID와 연결된 네이티브 코드의 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fc85a-103">Gets the extent of native code associated with the specified function ID.</span></span>  
  
 <span data-ttu-id="fc85a-104">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc85a-104">This method is obsolete.</span></span> <span data-ttu-id="fc85a-105">사용 된 [ICorProfilerInfo2::GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc85a-105">Use the [ICorProfilerInfo2::GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc85a-106">구문</span><span class="sxs-lookup"><span data-stu-id="fc85a-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeInfo(  
    [in]  FunctionID functionId,  
    [out] LPCBYTE    *pStart,  
    [out] ULONG      *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc85a-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc85a-107">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="fc85a-108">[in] 네이티브 코드가 연결된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fc85a-108">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `pStart`  
 <span data-ttu-id="fc85a-109">[out] 함수의 네이티브 코드를 구성하는 바이트 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fc85a-109">[out] A pointer to an array of bytes that compose the native code of the function.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="fc85a-110">[out] 네이티브 코드의 크기(바이트)를 지정하는 정수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fc85a-110">[out] A pointer to an integer that specifies the size, in bytes, of the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc85a-111">설명</span><span class="sxs-lookup"><span data-stu-id="fc85a-111">Remarks</span></span>  
 <span data-ttu-id="fc85a-112">성능을 최적화하기 위해 .NET Framework 버전 2.0의 런타임은 함수의 미리 컴파일된 네이티브 코드를 여러 영역으로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="fc85a-112">To optimize performance, the runtime in the .NET Framework version 2.0 splits the precompiled, native code of a function into multiple regions.</span></span> <span data-ttu-id="fc85a-113">결과적으로 `GetCodeInfo` 메서드는 함수의 네이티브 코드 범위를 처리할 수 없으므로 .NET Framework 2.0에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc85a-113">Consequently, the `GetCodeInfo` method is obsolete in the .NET Framework 2.0 because it is unable to handle the extent of a function's native code.</span></span> <span data-ttu-id="fc85a-114">프로파일러가 보다 일반적인 `ICorProfilerInfo2::GetCodeInfo2` 메서드 사용으로 전환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc85a-114">Profilers should switch to using the more general `ICorProfilerInfo2::GetCodeInfo2` method instead.</span></span>  
  
 <span data-ttu-id="fc85a-115">이 함수는 호출자 할당 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fc85a-115">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc85a-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fc85a-116">Requirements</span></span>  
 <span data-ttu-id="fc85a-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fc85a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc85a-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fc85a-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fc85a-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc85a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc85a-120">**.NET framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="fc85a-120">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc85a-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="fc85a-121">See also</span></span>

- [<span data-ttu-id="fc85a-122">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc85a-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="fc85a-123">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc85a-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="fc85a-124">프로파일링</span><span class="sxs-lookup"><span data-stu-id="fc85a-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
