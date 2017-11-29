---
title: "프로파일링 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
caps.latest.revision: "31"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5c0423f9c8b01c1289e1107c0c16c59968a6e2a4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="profiling-interfaces"></a><span data-ttu-id="f3942-102">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-102">Profiling Interfaces</span></span>
<span data-ttu-id="f3942-103">이 섹션에서는 CLR(공용 언어 런타임)에서 실행되는 프로그램을 프로파일링하는 데 사용할 수 있는 관리되지 않는 인터페이스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f3942-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="f3942-104">In This Section</span></span>  
 [<span data-ttu-id="f3942-105">ICLRProfiling 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-105">ICLRProfiling Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 <span data-ttu-id="f3942-106">제공 된 [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) 프로파일러를 실행 중인 프로세스에 연결할 수 있도록 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-106">Provides the [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="f3942-107">ICorProfilerAssemblyReferenceProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="f3942-108">CLR 프로파일러에 추가할 어셈블리 참조에 알릴 수 있습니다는 [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="f3942-109">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-109">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 <span data-ttu-id="f3942-110">코드 프로파일러가 구독한 이벤트가 발생하면 CLR이 해당 프로파일러에 알림을 보내는 데 사용되는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="f3942-111">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-111">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 <span data-ttu-id="f3942-112">.NET Framework 2.0 이상 버전에서 지원되는 콜백으로 `ICorProfilerCallback` 인터페이스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="f3942-113">ICorProfilerCallback3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-113">ICorProfilerCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 <span data-ttu-id="f3942-114">CLR이 프로파일러에 연결 및 분리 상태 정보를 전달하는 데 사용하는 콜백 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="f3942-115">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-115">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 <span data-ttu-id="f3942-116">CLR이 프로파일러에 정보를 전달하는 데 사용하는 콜백 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="f3942-117">ICorProfilerCallback5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-117">ICorProfilerCallback5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 <span data-ttu-id="f3942-118">가비지 컬렉션 루트에서 참조하는 개체의 전이적 Closure를 식별하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="f3942-119">ICorProfilerCallback6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-119">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 <span data-ttu-id="f3942-120">CLR이 어셈블리를 로드하는 중임을 프로파일러에 알리는 데 사용하는 콜백 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="f3942-121">ICorProfilerCallback7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 <span data-ttu-id="f3942-122">메모리 내 모듈과 연관 된 기호 스트림이 업데이트 되었음을 프로파일러에 알리기 위해 공용 언어 런타임에서 사용 하는 콜백 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
 [<span data-ttu-id="f3942-123">ICorProfilerFunctionControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-123">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="f3942-124">코드 프로파일러가 CLR과 통신하여 특정 메서드를 다시 컴파일할 때 JIT 컴파일러가 코드를 생성하는 방법을 제어할 수 있도록 하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-124">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="f3942-125">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-125">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="f3942-126">CLR에서 함수 컬렉션을 순서대로 반복하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-126">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="f3942-127">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 <span data-ttu-id="f3942-128">코드 프로파일러가 CLR과 통신하여 이벤트 모니터링을 제어하고 정보를 요청하는 데 사용하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-128">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="f3942-129">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-129">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 <span data-ttu-id="f3942-130">.NET Framework 2.0 이상 버전에서 지원되는 메서드로 `ICorProfilerInfo` 인터페이스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-130">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="f3942-131">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-131">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 <span data-ttu-id="f3942-132">`ICorProfilerInfo2` 이상 버전에서 지원되는 메서드로 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 인터페이스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-132">Extends the `ICorProfilerInfo2` interface with methods supported in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] and later versions.</span></span>  
  
 [<span data-ttu-id="f3942-133">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-133">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 <span data-ttu-id="f3942-134">코드 프로파일러가 CLR과 통신하여 이벤트 모니터링을 제어하고 정보를 요청하는 데 사용하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-134">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="f3942-135">ICorProfilerInfo5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-135">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 <span data-ttu-id="f3942-136">코드 프로파일러가 CLR과 통신하여 이벤트 모니터링을 제어하는 데 사용하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-136">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="f3942-137">ICorProfilerInfo6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-137">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 <span data-ttu-id="f3942-138">지정 된 NGen 모듈에 속하고 지정 된 메서드의 본문에 인라인 처리 되지 않은 모든 메서드에 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-138">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="f3942-139">ICorProfilerInfo7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-139">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 <span data-ttu-id="f3942-140">메모리 기호 스트림에 대 한 액세스를 제공 하는 및 모듈에 정의 된 메타 데이터가 새로 적용할 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-140">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="f3942-141">ICorProfilerModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-141">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="f3942-142">응용 프로그램이나 프로파일러가 로드한 모듈 컬렉션을 순서대로 반복하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-142">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="f3942-143">ICorProfilerObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-143">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="f3942-144">생성 되는 고정된 개체의 컬렉션을 순차적으로 반복 하는 방법을 제공 [Ngen.exe (네이티브 이미지 생성기)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-144">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="f3942-145">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-145">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="f3942-146">CLR에서 스레드 컬렉션을 순서대로 반복하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f3942-146">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="f3942-147">IMethodMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3942-147">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 <span data-ttu-id="f3942-148">제공 된 [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) 새 Microsoft MSIL (intermediate language) 함수 본문에 메모리를 할당 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="f3942-148">Provides the [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f3942-149">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f3942-149">Related Sections</span></span>  
 [<span data-ttu-id="f3942-150">프로 파일링 개요</span><span class="sxs-lookup"><span data-stu-id="f3942-150">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="f3942-151">프로 파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="f3942-151">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="f3942-152">프로 파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="f3942-152">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [<span data-ttu-id="f3942-153">프로 파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="f3942-153">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
