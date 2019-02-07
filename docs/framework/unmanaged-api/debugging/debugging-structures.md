---
title: 디버깅 구조체
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18bf03fee1a95c898e8273fa839e41a86b2d1c32
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828373"
---
# <a name="debugging-structures"></a><span data-ttu-id="8590c-102">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="8590c-102">Debugging Structures</span></span>
<span data-ttu-id="8590c-103">이 섹션에서는 디버깅 API에서 사용하는 관리되지 않는 구조체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-103">This section describes the unmanaged structures that the debugging API uses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8590c-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="8590c-104">In This Section</span></span>
 <span data-ttu-id="8590c-105">[CLRDATA_ADDRESS_RANGE 구조](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) 주소 범위를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-105">[CLRDATA_ADDRESS_RANGE Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) Defines an address range.</span></span>

 <span data-ttu-id="8590c-106">[CLRDATA_IL_ADDRESS_MAP 구조](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) IL 주소 매핑 정의</span><span class="sxs-lookup"><span data-stu-id="8590c-106">[CLRDATA_IL_ADDRESS_MAP Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) Defines an IL to address mapping</span></span>

 <span data-ttu-id="8590c-107">[CLR_DEBUGGING_VERSION 구조체](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) 는 CLR (공용 언어 런타임) 디버깅을 위해의 제품 버전을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-107">[CLR_DEBUGGING_VERSION Structure](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>

 <span data-ttu-id="8590c-108">[CodeChunkInfo 구조체 1](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) 메모리에서 코드의 단일 청크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-108">[CodeChunkInfo Structure1](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) Represents a single chunk of code in memory.</span></span>

 <span data-ttu-id="8590c-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) 스레드 프레임에서 현재 활성화 된 함수에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contains information about the functions that are currently active in a thread's frames.</span></span>

 <span data-ttu-id="8590c-110">[COR_ARRAY_LAYOUT 구조체](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) 메모리 내 배열 개체의 레이아웃에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-110">[COR_ARRAY_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) Provides information about the layout of an array object in memory.</span></span>

 <span data-ttu-id="8590c-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) MSIL (Microsoft intermediate language)을 매핑하는 데 사용 되는 오프셋 코드 네이티브 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>

 <span data-ttu-id="8590c-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) 코드의 범위에 대 한 오프셋된 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contains the offset information for a range of code.</span></span>

 <span data-ttu-id="8590c-113">[COR_FIELD 구조체](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) 개체의 필드에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-113">[COR_FIELD Structure](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Provides information about a field in an object.</span></span>

 <span data-ttu-id="8590c-114">[COR_GC_REFERENCE 구조체](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) 가비지 수집 될 개체에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-114">[COR_GC_REFERENCE Structure](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Contains information about an object that is to be garbage-collected.</span></span>

 <span data-ttu-id="8590c-115">[COR_HEAPINFO 구조체](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) 열거 가능 여부를 포함 하 여 가비지 컬렉션 힙에 대 한 일반 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-115">[COR_HEAPINFO Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>

 <span data-ttu-id="8590c-116">[COR_HEAPOBJECT 구조체](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 관리 되는 힙의 개체에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-116">[COR_HEAPOBJECT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Provides information about an object on the managed heap.</span></span>

 <span data-ttu-id="8590c-117">[COR_IL_MAP](cor-il-map-structure.md) 함수의 상대 오프셋 변경 내용을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-117">[COR_IL_MAP](cor-il-map-structure.md) Specifies changes in the relative offset of a function.</span></span>

 <span data-ttu-id="8590c-118">[COR_SEGMENT 구조체](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) 관리 되는 힙의 메모리 영역에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-118">[COR_SEGMENT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) Contains information about a region of memory in the managed heap.</span></span>

 <span data-ttu-id="8590c-119">[COR_TYPEID 구조체](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 유형 식별자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-119">[COR_TYPEID Structure](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Contains a type identifier.</span></span>

 <span data-ttu-id="8590c-120">[COR_TYPE_LAYOUT 구조체](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) 메모리 내 개체의 레이아웃에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-120">[COR_TYPE_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) Provides information about the layout of an object in memory.</span></span>

 <span data-ttu-id="8590c-121">[COR_VERSION](cor-version-structure.md) 공용 언어 런타임의 표준 네 부분으로 된 버전 번호를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-121">[COR_VERSION](cor-version-structure.md) Stores the standard four-part version number of the common language runtime.</span></span>

 <span data-ttu-id="8590c-122">[CorDebugBlockingObject 구조체](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 스레드가 차단 되는 이유는 이유와 스레드를 차단 하는 개체를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-122">[CorDebugBlockingObject Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>

 <span data-ttu-id="8590c-123">[CorDebugEHClause 구조체](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) 지정 된 IL (중간 언어) 부분에 대 한 예외 처리 (EH) 절을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-123">[CorDebugEHClause Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>

 <span data-ttu-id="8590c-124">[CorDebugExceptionObjectStackFrame 구조체](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) 스택 예외 개체에서 프레임 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-124">[CorDebugExceptionObjectStackFrame Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Represents stack frame information from an exception object.</span></span>

 <span data-ttu-id="8590c-125">[CorDebugGuidToTypeMapping 구조체](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) 지도 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 해당 하는 GUID [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-125">[CorDebugGuidToTypeMapping Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) object.</span></span>

 <span data-ttu-id="8590c-126">[DacpGetModuleAddress 구조](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) 모듈 주소 요청에 대 한 컨테이너를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-126">[DacpGetModuleAddress Structure](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) Defines the container for a module address request.</span></span>

 <span data-ttu-id="8590c-127">[DacpMethodDescData 구조](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) 메서드의 런타임 정보에 대 한 전송 버퍼를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-127">[DacpMethodDescData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) Defines a transport buffer for a method's runtime information.</span></span>

 <span data-ttu-id="8590c-128">[DacpModuleData 구조](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) 모듈의 런타임 정보에 대 한 전송 버퍼를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-128">[DacpModuleData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) Defines a transport buffer for a module's runtime information.</span></span>

 <span data-ttu-id="8590c-129">[DacpReJitData 구조](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) 지정 된 프로파일러가 계측 메서드에 대 한 기본 정보를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-129">[DacpReJitData Structure](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) Defines the basic information about a given profiler-instrumented method.</span></span>

 <span data-ttu-id="8590c-130">[StackTrace_SimpleContext 구조체](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) 전체 대신 사용할 수 있는 단순 컨텍스트를 제공 `CONTEXT` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="8590c-130">[StackTrace_SimpleContext Structure](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>



## <a name="related-sections"></a><span data-ttu-id="8590c-131">관련 단원</span><span class="sxs-lookup"><span data-stu-id="8590c-131">Related Sections</span></span>
 [<span data-ttu-id="8590c-132">디버깅 Coclass</span><span class="sxs-lookup"><span data-stu-id="8590c-132">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)

 [<span data-ttu-id="8590c-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8590c-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

 [<span data-ttu-id="8590c-134">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="8590c-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)

 [<span data-ttu-id="8590c-135">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="8590c-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

 [<span data-ttu-id="8590c-136">디버깅</span><span class="sxs-lookup"><span data-stu-id="8590c-136">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
