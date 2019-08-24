---
title: 디버깅 인터페이스
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff589285d81a3febf887bba976b62a9ae4a573c8
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025936"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="cd4bb-102">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd4bb-102">Debugging Interfaces</span></span>
<span data-ttu-id="cd4bb-103">이 단원에서는 CLR(공용 언어 런타임)에서 실행되는 프로그램의 디버깅을 처리하는 관리되지 않는 인터페이스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cd4bb-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="cd4bb-104">In This Section</span></span>  
 <span data-ttu-id="cd4bb-105">[ICLRDataEnumMemoryRegions 인터페이스](iclrdataenummemoryregions-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-105">[ICLRDataEnumMemoryRegions Interface](iclrdataenummemoryregions-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-106">호출자가 지정하는 메모리 영역을 열거하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 <span data-ttu-id="cd4bb-107">[ICLRDataEnumMemoryRegionsCallback 인터페이스](iclrdataenummemoryregionscallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-107">[ICLRDataEnumMemoryRegionsCallback Interface](iclrdataenummemoryregionscallback-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-108">지정된 메모리 영역을 열거하려고 시도한 결과를 디버거에 보고하는 콜백 메서드를 `EnumMemoryRegions`에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 <span data-ttu-id="cd4bb-109">[ICLRDataTarget 인터페이스](iclrdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-109">[ICLRDataTarget Interface](iclrdatatarget-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-110">대상 CLR 프로세스와 상호 작용하기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 <span data-ttu-id="cd4bb-111">[ICLRDataTarget2 인터페이스](iclrdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-111">[ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-112">데이터 액세스 서비스 계층에서 대상 프로세스의 가상 메모리 영역을 조작하는 데 사용하는 `ICLRDataTarget`의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 <span data-ttu-id="cd4bb-113">[ICLRDataTarget3 인터페이스](iclrdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-113">[ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-114">서브 클래스 [ICLRDataTarget2](iclrdatatarget2-interface.md) 예외 정보에 대 한 액세스를 제공 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-114">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 <span data-ttu-id="cd4bb-115">[ICLRDebugging 인터페이스](iclrdebugging-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-115">[ICLRDebugging Interface](iclrdebugging-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-116">디버깅을 위해 모듈을 로드 및 언로드하는 작업을 처리하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 <span data-ttu-id="cd4bb-117">[ICLRDebuggingLibraryProvider 인터페이스](iclrdebugginglibraryprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-117">[ICLRDebuggingLibraryProvider Interface](iclrdebugginglibraryprovider-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-118">포함 된 [ProvideLibrary 메서드](iclrdebugginglibraryprovider-providelibrary-method.md) 메서드 라이브러리 공급자 콜백 인터페이스 공용 언어 런타임 버전별 디버깅 라이브러리 있고에 로드 된 요청 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-118">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 <span data-ttu-id="cd4bb-119">[ICLRMetadataLocator 인터페이스](iclrmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-119">[ICLRMetadataLocator Interface](iclrmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-120">데이터 액세스 서비스 계층에서 대상 프로세스의 어셈블리 메타데이터를 찾는 데 사용되는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 <span data-ttu-id="cd4bb-121">[ICorDebug 인터페이스](icordebug-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-121">[ICorDebug Interface](icordebug-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-122">개발자가 CLR 환경에서 애플리케이션을 디버깅하는 데 사용할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="cd4bb-123">[ICorDebugAppDomain 인터페이스](icordebugappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-123">[ICorDebugAppDomain Interface](icordebugappdomain-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-124">애플리케이션 도메인 디버깅에 사용하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-124">Provides methods for debugging application domains.</span></span>  
  
 <span data-ttu-id="cd4bb-125">[ICorDebugAppDomain2 인터페이스](icordebugappdomain2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-125">[ICorDebugAppDomain2 Interface](icordebugappdomain2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-126">배열, 포인터, 함수 포인터 및 ByRef 형식에 사용할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="cd4bb-127">이 인터페이스는 `ICorDebugAppDomain` 인터페이스의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 <span data-ttu-id="cd4bb-128">[ICorDebugAppDomain3 인터페이스](icordebugappdomain3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-128">[ICorDebugAppDomain3 Interface](icordebugappdomain3-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-129">응용 프로그램 도메인에서 Windows 런타임 형식을 사용 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-129">Provides methods to work with the Windows Runtime types in an application domain.</span></span> <span data-ttu-id="cd4bb-130">이 인터페이스는 `ICorDebugAppDomain` 및 `ICorDebugAppDomain2` 인터페이스의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 <span data-ttu-id="cd4bb-131">[ICorDebugAppDomain4 인터페이스](icordebugappdomain4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-131">[ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-132">논리적으로 확장 합니다 [ICorDebugAppDomain](icordebugappdomain-interface.md) 인터페이스를 COM 호출 가능 래퍼를에서 관리 되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-132">Logically extends the [ICorDebugAppDomain](icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 <span data-ttu-id="cd4bb-133">[ICorDebugAppDomainEnum 인터페이스](icordebugappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-133">[ICorDebugAppDomainEnum Interface](icordebugappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-134">열거형의 다음 위치에서 시작하여 지정된 수만큼 `ICorDebugAppDomain` 값을 반환하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 <span data-ttu-id="cd4bb-135">[ICorDebugArrayValue 인터페이스](icordebugarrayvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-135">[ICorDebugArrayValue Interface](icordebugarrayvalue-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-136">1차원 배열이나 다차원 배열을 나타내는 `ICorDebugHeapValue`의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 <span data-ttu-id="cd4bb-137">[ICorDebugAssembly 인터페이스](icordebugassembly-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-137">[ICorDebugAssembly Interface](icordebugassembly-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-138">어셈블리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-138">Represents an assembly.</span></span>  
  
 <span data-ttu-id="cd4bb-139">[ICorDebugAssembly2 인터페이스](icordebugassembly2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-139">[ICorDebugAssembly2 Interface](icordebugassembly2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-140">어셈블리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-140">Represents an assembly.</span></span> <span data-ttu-id="cd4bb-141">이 인터페이스는 `ICorDebugAssembly` 인터페이스의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 <span data-ttu-id="cd4bb-142">[ICorDebugAssembly3 인터페이스](icordebugassembly3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-142">[ICorDebugAssembly3 Interface](icordebugassembly3-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-143">논리적으로 확장 합니다 [ICorDebugAssembly](icordebugassembly-interface.md) 컨테이너 어셈블리 및 포함 된 어셈블리에 대 한 지원을 제공 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-143">Logically extends the [ICorDebugAssembly](icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="cd4bb-144">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd4bb-144">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd4bb-145">[ICorDebugAssemblyEnum 인터페이스](icordebugassemblyenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-145">[ICorDebugAssemblyEnum Interface](icordebugassemblyenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-146">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugAssembly` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 <span data-ttu-id="cd4bb-147">[ICorDebugBlockingObjectEnum 인터페이스](icordebugblockingobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-147">[ICorDebugBlockingObjectEnum Interface](icordebugblockingobjectenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-148">목록에 대 한 열거자를 제공 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-148">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
 <span data-ttu-id="cd4bb-149">[ICorDebugBoxValue 인터페이스](icordebugboxvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-149">[ICorDebugBoxValue Interface](icordebugboxvalue-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-150">boxed 값 클래스 개체를 나타내는 `ICorDebugHeapValue`의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 <span data-ttu-id="cd4bb-151">[ICorDebugBreakpoint 인터페이스](icordebugbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-151">[ICorDebugBreakpoint Interface](icordebugbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-152">함수의 중단점 또는 값에 대한 조사식 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 <span data-ttu-id="cd4bb-153">[ICorDebugBreakpointEnum 인터페이스](icordebugbreakpointenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-153">[ICorDebugBreakpointEnum Interface](icordebugbreakpointenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-154">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugBreakpoint` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 <span data-ttu-id="cd4bb-155">[ICorDebugChain 인터페이스](icordebugchain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-155">[ICorDebugChain Interface](icordebugchain-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-156">실제 또는 논리 호출 스택의 세그먼트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 <span data-ttu-id="cd4bb-157">[ICorDebugChainEnum 인터페이스](icordebugchainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-157">[ICorDebugChainEnum Interface](icordebugchainenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-158">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugChain` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 <span data-ttu-id="cd4bb-159">[ICorDebugClass 인터페이스](icordebugclass-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-159">[ICorDebugClass Interface](icordebugclass-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-160">기본 또는 복합(즉, 사용자 정의) 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="cd4bb-161">형식이 제네릭이면 `ICorDebugClass`는 인스턴스화되지 않은 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 <span data-ttu-id="cd4bb-162">[ICorDebugClass2 인터페이스](icordebugclass2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-162">[ICorDebugClass2 Interface](icordebugclass2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-163">제네릭 클래스나 <xref:System.Type> 형식의 메서드 매개 변수를 사용하는 클래스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="cd4bb-164">이 인터페이스는 `ICorDebugClass`를 확장한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-164">This interface extends `ICorDebugClass`.</span></span>  
  
 <span data-ttu-id="cd4bb-165">[ICorDebugCode 인터페이스](icordebugcode-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-165">[ICorDebugCode Interface](icordebugcode-interface1.md)</span></span>\
 <span data-ttu-id="cd4bb-166">MSIL(Microsoft Intermediate Language) 코드나 네이티브 코드의 세그먼트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 <span data-ttu-id="cd4bb-167">[ICorDebugCode2 인터페이스](icordebugcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-167">[ICorDebugCode2 Interface](icordebugcode2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-168">`ICorDebugCode`의 기능을 확장하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 <span data-ttu-id="cd4bb-169">[ICorDebugCode3 인터페이스](icordebugcode3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-169">[ICorDebugCode3 Interface](icordebugcode3-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-170">확장 하는 메서드를 제공 [ICorDebugCode](icordebugcode-interface1.md) 하 고 [ICorDebugCode2](icordebugcode2-interface.md) 관리 되는 반환 값에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-170">Provides a method that extends [ICorDebugCode](icordebugcode-interface1.md) and [ICorDebugCode2](icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 <span data-ttu-id="cd4bb-171">[ICorDebugCode4 인터페이스](icordebugcode4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-171">[ICorDebugCode4 Interface](icordebugcode4-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-172">지역 변수 및 함수에 인수를 열거 하는 디버거를 사용 하도록 설정 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="cd4bb-173">[ICorDebugCodeEnum 인터페이스](icordebugcodeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-173">[ICorDebugCodeEnum Interface](icordebugcodeenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-174">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugCode` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 <span data-ttu-id="cd4bb-175">[ICorDebugComObjectValue 인터페이스](icordebugcomobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-175">[ICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-176">캐시된 인터페이스 개체를 검색하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 <span data-ttu-id="cd4bb-177">[ICorDebugContext 인터페이스](icordebugcontext-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-177">[ICorDebugContext Interface](icordebugcontext-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-178">컨텍스트 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-178">Represents a context object.</span></span> <span data-ttu-id="cd4bb-179">이 인터페이스는 아직 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-179">This interface has not been implemented yet.</span></span>  
  
 <span data-ttu-id="cd4bb-180">[ICorDebugController 인터페이스](icordebugcontroller-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-180">[ICorDebugController Interface](icordebugcontroller-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-181"><xref:System.Diagnostics.Process>나 <xref:System.AppDomain> 같이 코드 실행 컨텍스트를 제어할 수 있는 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 <span data-ttu-id="cd4bb-182">[ICorDebugDataTarget 인터페이스](icordebugdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-182">[ICorDebugDataTarget Interface](icordebugdatatarget-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-183">특정 대상 프로세스에 대한 액세스를 제공하는 콜백 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 <span data-ttu-id="cd4bb-184">[ICorDebugDataTarget2 인터페이스](icordebugdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-184">[ICorDebugDataTarget2 Interface](icordebugdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-185">논리적으로 확장 합니다 [ICorDebugDataTarget](icordebugdatatarget-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-185">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="cd4bb-186">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd4bb-186">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd4bb-187">[ICorDebugDataTarget3 인터페이스](icordebugdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-187">[ICorDebugDataTarget3 Interface](icordebugdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-188">논리적으로 확장 합니다 [ICorDebugDataTarget](icordebugdatatarget-interface.md) 로드 된 모듈에 대 한 정보를 제공 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-188">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="cd4bb-189">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd4bb-189">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd4bb-190">[ICorDebugDebugEvent 인터페이스](icordebugdebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-190">[ICorDebugDebugEvent Interface](icordebugdebugevent-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-191">모든 `ICorDebug` 디버그 이벤트가 파생되는 기본 인터페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="cd4bb-192">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd4bb-192">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd4bb-193">[ICorDebugEditAndContinueErrorInfo 인터페이스](icordebugeditandcontinueerrorinfo-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-193">[ICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-194">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-194">Obsolete.</span></span> <span data-ttu-id="cd4bb-195">이 인터페이스를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-195">Do not use this interface.</span></span>  
  
 <span data-ttu-id="cd4bb-196">[ICorDebugEditAndContinueSnapshot 인터페이스](icordebugeditandcontinuesnapshot-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-196">[ICorDebugEditAndContinueSnapshot Interface](icordebugeditandcontinuesnapshot-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-197">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-197">Obsolete.</span></span> <span data-ttu-id="cd4bb-198">이 인터페이스를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-198">Do not use this interface.</span></span>  
  
 <span data-ttu-id="cd4bb-199">[ICorDebugEnum 인터페이스](icordebugenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-199">[ICorDebugEnum Interface](icordebugenum-interface1.md)</span></span>\
 <span data-ttu-id="cd4bb-200">열거자를 디버깅할 수 있는 추상 기본 인터페이스로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 <span data-ttu-id="cd4bb-201">[ICorDebugErrorInfoEnum 인터페이스](icordebugerrorinfoenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-201">[ICorDebugErrorInfoEnum Interface](icordebugerrorinfoenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-202">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-202">Obsolete.</span></span> <span data-ttu-id="cd4bb-203">이 인터페이스를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-203">Do not use this interface.</span></span>  
  
 <span data-ttu-id="cd4bb-204">[ICorDebugEval 인터페이스](icordebugeval-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-204">[ICorDebugEval Interface](icordebugeval-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-205">디버깅 중인 코드의 컨텍스트 내에서 디버거가 코드를 실행할 수 있도록 하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 <span data-ttu-id="cd4bb-206">[ICorDebugEval2 인터페이스](icordebugeval2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-206">[ICorDebugEval2 Interface](icordebugeval2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-207">제네릭 형식을 지원하도록 `ICorDebugEval`을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 <span data-ttu-id="cd4bb-208">[ICorDebugExceptionDebugEvent 인터페이스](icordebugexceptiondebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-208">[ICorDebugExceptionDebugEvent Interface](icordebugexceptiondebugevent-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-209">확장 된 [ICorDebugDebugEvent](icordebugdebugevent-interface.md) 예외 이벤트를 지 원하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-209">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="cd4bb-210">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd4bb-210">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd4bb-211">[ICorDebugExceptionObjectCallStackEnum 인터페이스](icordebugexceptionobjectcallstackenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-211">[ICorDebugExceptionObjectCallStackEnum Interface](icordebugexceptionobjectcallstackenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-212">예외 개체에 포함된 호출 스택 정보에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 <span data-ttu-id="cd4bb-213">[ICorDebugExceptionObjectValue 인터페이스](icordebugexceptionobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-213">[ICorDebugExceptionObjectValue Interface](icordebugexceptionobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-214">확장 된 [ICorDebugObjectValue](icordebugobjectvalue-interface.md) 관리 되는 예외 개체에서 스택 추적 정보를 제공 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-214">Extends the [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 <span data-ttu-id="cd4bb-215">[ICorDebugFrame 인터페이스](icordebugframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-215">[ICorDebugFrame Interface](icordebugframe-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-216">현재 스택의 프레임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-216">Represents a frame on the current stack.</span></span>  
  
 <span data-ttu-id="cd4bb-217">[ICorDebugFrameEnum 인터페이스](icordebugframeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-217">[ICorDebugFrameEnum Interface](icordebugframeenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-218">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugFrame` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 <span data-ttu-id="cd4bb-219">[ICorDebugFunction 인터페이스](icordebugfunction-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-219">[ICorDebugFunction Interface](icordebugfunction-interface1.md)</span></span>\
 <span data-ttu-id="cd4bb-220">관리되는 함수 또는 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-220">Represents a managed function or method.</span></span>  
  
 <span data-ttu-id="cd4bb-221">[ICorDebugFunction2 인터페이스](icordebugfunction2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-221">[ICorDebugFunction2 Interface](icordebugfunction2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-222">`ICorDebugFunction`의 기능을 논리적으로 확장하여 "내 코드만" 단계별 실행 디버깅을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 <span data-ttu-id="cd4bb-223">[ICorDebugFunction3 인터페이스](icordebugfunction3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-223">[ICorDebugFunction3 Interface](icordebugfunction3-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-224">논리적으로 확장 합니다 [ICorDebugFunction](icordebugfunction-interface1.md) ReJIT 요청의 코드에 대 한 액세스를 제공 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-224">Logically extends the [ICorDebugFunction](icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 <span data-ttu-id="cd4bb-225">[ICorDebugFunctionBreakpoint 인터페이스](icordebugfunctionbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-225">[ICorDebugFunctionBreakpoint Interface](icordebugfunctionbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-226">함수에서 중단점을 지원하기 위해 `ICorDebugBreakpoint`를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 <span data-ttu-id="cd4bb-227">[ICorDebugGCReferenceEnum 인터페이스](icordebuggcreferenceenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-227">[ICorDebugGCReferenceEnum Interface](icordebuggcreferenceenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-228">가비지 수집되는 개체에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 <span data-ttu-id="cd4bb-229">[ICorDebugGenericValue 인터페이스](icordebuggenericvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-229">[ICorDebugGenericValue Interface](icordebuggenericvalue-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-230">모든 값에 적용되는 `ICorDebugValue`의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="cd4bb-231">이 인터페이스에서는 값의 Get 및 Set 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-231">This interface provides Get and Set methods for the value.</span></span>  
  
 <span data-ttu-id="cd4bb-232">[ICorDebugGuidToTypeEnum 인터페이스](icordebugguidtotypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-232">[ICorDebugGuidToTypeEnum Interface](icordebugguidtotypeenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-233">GUID를 매핑하는 개체와 그에 해당하는 `ICorDebugType` 개체에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 <span data-ttu-id="cd4bb-234">[ICorDebugHandleValue 인터페이스](icordebughandlevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-234">[ICorDebugHandleValue Interface](icordebughandlevalue-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-235">디버거에서 가비지 수집을 위해 핸들을 만든 대상 참조 값을 나타내는 `ICorDebugReferenceValue`의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 <span data-ttu-id="cd4bb-236">[ICorDebugHeapEnum 인터페이스](icordebugheapenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-236">[ICorDebugHeapEnum Interface](icordebugheapenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-237">관리되는 힙의 개체에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 <span data-ttu-id="cd4bb-238">[ICorDebugHeapSegmentEnum 인터페이스](icordebugheapsegmentenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-238">[ICorDebugHeapSegmentEnum Interface](icordebugheapsegmentenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-239">관리되는 힙 메모리 영역에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 <span data-ttu-id="cd4bb-240">[ICorDebugHeapValue 인터페이스](icordebugheapvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-240">[ICorDebugHeapValue Interface](icordebugheapvalue-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-241">CLR 가비지 수집기에서 수집한 개체를 나타내는 `ICorDebugValue`의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 <span data-ttu-id="cd4bb-242">[ICorDebugHeapValue2 인터페이스](icordebugheapvalue2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-242">[ICorDebugHeapValue2 Interface](icordebugheapvalue2-interface1.md)</span></span>\
 <span data-ttu-id="cd4bb-243">런타임 핸들에 대한 지원을 제공하는 `ICorDebugHeapValue`의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 <span data-ttu-id="cd4bb-244">[ICorDebugHeapValue3 인터페이스](icordebugheapvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-244">[ICorDebugHeapValue3 Interface](icordebugheapvalue3-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-245">개체의 모니터 잠금 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-245">Exposes the monitor lock properties of objects.</span></span>  
  
 <span data-ttu-id="cd4bb-246">[ICorDebugILCode 인터페이스](icordebugilcode-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-246">[ICorDebugILCode Interface](icordebugilcode-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-247">IL(중간 언어) 코드 세그먼트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 <span data-ttu-id="cd4bb-248">[ICorDebugILCode2 인터페이스](icordebugilcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-248">[ICorDebugILCode2 Interface](icordebugilcode2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-249">논리적으로 확장 합니다 [ICorDebugILCode](icordebugilcode-interface.md) 인터페이스 함수의 로컬 변수 서명에 대 한 토큰을 반환 하 고 프로파일러의 계측 된 IL (중간 언어)을 매핑하는 방법을 제공 하기 위해 원래 메서드 IL 오프셋 오프셋 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-249">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 <span data-ttu-id="cd4bb-250">[ICorDebugILFrame 인터페이스](icordebugilframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-250">[ICorDebugILFrame Interface](icordebugilframe-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-251">MSIL 코드의 스택 프레임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-251">Represents a stack frame of MSIL code.</span></span>  
  
 <span data-ttu-id="cd4bb-252">[ICorDebugILFrame2 인터페이스](icordebugilframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-252">[ICorDebugILFrame2 Interface](icordebugilframe2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-253">`ICorDebugILFrame`에서 논리적으로 확장된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 <span data-ttu-id="cd4bb-254">[ICorDebugILFrame3 인터페이스](icordebugilframe3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-254">[ICorDebugILFrame3 Interface](icordebugilframe3-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-255">함수의 반환 값을 캡슐화하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 <span data-ttu-id="cd4bb-256">[ICorDebugILFrame4 인터페이스](icordebugilframe4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-256">[ICorDebugILFrame4 Interface](icordebugilframe4-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-257">IL(중간 언어) 코드의 스택 프레임에서 로컬 변수 및 코드에 액세스하는 데 사용할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="cd4bb-258">디버거가 프로파일러 ReJIT 계측에 추가된 변수와 코드에 액세스할 수 있는지는 매개 변수를 통해 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 <span data-ttu-id="cd4bb-259">[ICorDebugInstanceFieldSymbol 인터페이스](icordebuginstancefieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-259">[ICorDebugInstanceFieldSymbol Interface](icordebuginstancefieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-260">인스턴스 필드에 대한 디버그 기호 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="cd4bb-261">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd4bb-261">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd4bb-262">[ICorDebugInternalFrame 인터페이스](icordebuginternalframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-262">[ICorDebugInternalFrame Interface](icordebuginternalframe-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-263">디버거의 프레임 형식을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-263">Identifies frame types for the debugger.</span></span>  
  
 <span data-ttu-id="cd4bb-264">[ICorDebugInternalFrame2 인터페이스](icordebuginternalframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-264">[ICorDebugInternalFrame2 Interface](icordebuginternalframe2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-265">스택 주소에 상대적인 위치를 포함 하 여 내부 프레임에 대 한 정보를 제공 [ICorDebugFrame](icordebugframe-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](icordebugframe-interface.md) objects.</span></span>  
  
 <span data-ttu-id="cd4bb-266">[ICorDebugLoadedModule 인터페이스](icordebugloadedmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-266">[ICorDebugLoadedModule Interface](icordebugloadedmodule-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-267">로드된 모듈에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-267">Provides information about a loaded module.</span></span> <span data-ttu-id="cd4bb-268">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd4bb-268">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd4bb-269">[ICorDebugManagedCallback 인터페이스](icordebugmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-269">[ICorDebugManagedCallback Interface](icordebugmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-270">디버거 콜백을 처리하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-270">Provides methods to process debugger callbacks.</span></span>  
  
 <span data-ttu-id="cd4bb-271">[ICorDebugManagedCallback2 인터페이스](icordebugmanagedcallback2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-271">[ICorDebugManagedCallback2 Interface](icordebugmanagedcallback2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-272">디버거 예외 처리 및 MDA(관리 디버깅 도우미)를 지원하기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="cd4bb-273">`ICorDebugManagedCallback2`은 `ICorDebugManagedCallback`에서 논리적으로 확장된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 <span data-ttu-id="cd4bb-274">[ICorDebugManagedCallback3 인터페이스](icordebugmanagedcallback3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-274">[ICorDebugManagedCallback3 Interface](icordebugmanagedcallback3-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-275">활성화된 사용자 지정 디버거 알림이 발생했음을 나타내는 콜백 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 <span data-ttu-id="cd4bb-276">[ICorDebugMDA 인터페이스](icordebugmda-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-276">[ICorDebugMDA Interface](icordebugmda-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-277">MDA(관리 디버깅 도우미) 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 <span data-ttu-id="cd4bb-278">[ICorDebugMemoryBuffer 인터페이스](icordebugmemorybuffer-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-278">[ICorDebugMemoryBuffer Interface](icordebugmemorybuffer-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-279">메모리 내 버퍼를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="cd4bb-280">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd4bb-280">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd4bb-281">[ICorDebugMergedAssemblyRecord 인터페이스](icordebugmergedassemblyrecord-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-281">[ICorDebugMergedAssemblyRecord Interface](icordebugmergedassemblyrecord-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-282">병합된 어셈블리에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="cd4bb-283">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd4bb-283">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd4bb-284">[ICorDebugMetaDataLocator 인터페이스](icordebugmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-284">[ICorDebugMetaDataLocator Interface](icordebugmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-285">디버거에 메타데이터 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-285">Provides metadata information to the debugger.</span></span>  
  
 <span data-ttu-id="cd4bb-286">[ICorDebugModule 인터페이스](icordebugmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-286">[ICorDebugModule Interface](icordebugmodule-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-287">실행 파일이나 DLL(동적 연결 라이브러리)인 CLR 모듈을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 <span data-ttu-id="cd4bb-288">[ICorDebugModule2 인터페이스](icordebugmodule2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-288">[ICorDebugModule2 Interface](icordebugmodule2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-289">`ICorDebugModule`에서 논리적으로 확장된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 <span data-ttu-id="cd4bb-290">[ICorDebugModule3 인터페이스](icordebugmodule3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-290">[ICorDebugModule3 Interface](icordebugmodule3-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-291">동적 모듈에 대한 기호 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 <span data-ttu-id="cd4bb-292">[ICorDebugModuleBreakpoint 인터페이스](icordebugmodulebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-292">[ICorDebugModuleBreakpoint Interface](icordebugmodulebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-293">특정 모듈에 액세스할 수 있도록 `ICorDebugBreakpoint`를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 <span data-ttu-id="cd4bb-294">[ICorDebugModuleDebugEvent 인터페이스](icordebugmoduledebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-294">[ICorDebugModuleDebugEvent Interface](icordebugmoduledebugevent-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-295">확장 된 [ICorDebugDebugEvent](icordebugdebugevent-interface.md) 모듈 수준 이벤트를 지 원하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-295">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="cd4bb-296">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd4bb-296">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd4bb-297">[ICorDebugModuleEnum 인터페이스](icordebugmoduleenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-297">[ICorDebugModuleEnum Interface](icordebugmoduleenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-298">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugModule` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 <span data-ttu-id="cd4bb-299">[ICorDebugMutableDataTarget 인터페이스](icordebugmutabledatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-299">[ICorDebugMutableDataTarget Interface](icordebugmutabledatatarget-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-300">확장 된 [ICorDebugDataTarget](icordebugdatatarget-interface.md) 인터페이스를 변경할 수 있는 데이터 대상을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-300">Extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 <span data-ttu-id="cd4bb-301">[ICorDebugNativeFrame 인터페이스](icordebugnativeframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-301">[ICorDebugNativeFrame Interface](icordebugnativeframe-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-302">네이티브 프레임에 사용되는 특수화된 `ICorDebugFrame` 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 <span data-ttu-id="cd4bb-303">[ICorDebugNativeFrame2 인터페이스](icordebugnativeframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-303">[ICorDebugNativeFrame2 Interface](icordebugnativeframe2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-304">자식 및 부모 프레임 관계를 테스트하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 <span data-ttu-id="cd4bb-305">[ICorDebugObjectEnum 인터페이스](icordebugobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-305">[ICorDebugObjectEnum Interface](icordebugobjectenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-306">`ICorDebugEnum` 메서드를 구현하고 RVA(Relative Virtual Address)로 개체의 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 <span data-ttu-id="cd4bb-307">[ICorDebugObjectValue 인터페이스](icordebugobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-307">[ICorDebugObjectValue Interface](icordebugobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-308">개체가 들어 있는 값을 나타내는 `ICorDebugValue`의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 <span data-ttu-id="cd4bb-309">[ICorDebugObjectValue2 인터페이스](icordebugobjectvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-309">[ICorDebugObjectValue2 Interface](icordebugobjectvalue2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-310">상속 및 재정의 기능을 지원하도록 `ICorDebugObjectValue`를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 <span data-ttu-id="cd4bb-311">[ICorDebugProcess 인터페이스](icordebugprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-311">[ICorDebugProcess Interface](icordebugprocess-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-312">관리 코드를 실행하는 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-312">Represents a process that is executing managed code.</span></span>  
  
 <span data-ttu-id="cd4bb-313">[ICorDebugProcess2 인터페이스](icordebugprocess2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-313">[ICorDebugProcess2 Interface](icordebugprocess2-interface1.md)</span></span>\
 <span data-ttu-id="cd4bb-314">`ICorDebugProcess`에서 논리적으로 확장된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 <span data-ttu-id="cd4bb-315">[ICorDebugProcess3 인터페이스](icordebugprocess3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-315">[ICorDebugProcess3 Interface](icordebugprocess3-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-316">사용자 지정 디버거 알림을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-316">Controls custom debugger notifications.</span></span>

 <span data-ttu-id="cd4bb-317">[ICorDebugProcess4 인터페이스](icordebugprocess4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-317">[ICorDebugProcess4 Interface](icordebugprocess4-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-318">프로세스 실행 제어가 부족에 대 한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-318">Provides support for out of process execution control.</span></span>
  
 <span data-ttu-id="cd4bb-319">[ICorDebugProcess5 인터페이스](icordebugprocess5-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-319">[ICorDebugProcess5 Interface](icordebugprocess5-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-320">확장 된 [ICorDebugProcess](icordebugprocess-interface.md) 관리 되는 개체의 가비지 수집에 대 한 정보를 제공 하 고 디버거가 응용 프로그램에서 이미지를 로드 하는지 여부를 확인 하려면 관리 되는 힙에 대 한 액세스를 지 원하는 인터페이스의 로컬 네이티브 이미지 캐시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-320">Extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 <span data-ttu-id="cd4bb-321">[ICorDebugProcess6 인터페이스](icordebugprocess6-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-321">[ICorDebugProcess6 Interface](icordebugprocess6-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-322">논리적으로 확장 합니다 [ICorDebugProcess](icordebugprocess-interface.md) 인터페이스 네이티브 예외 디버그 이벤트, 가상 모듈 분할에서 인코딩 되는 관리 되는 디버그 이벤트 디코딩 등의 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-322">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="cd4bb-323">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd4bb-323">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd4bb-324">[ICorDebugProcess7 인터페이스](icordebugprocess7-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-324">[ICorDebugProcess7 Interface](icordebugprocess7-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-325">대상 프로세스에서 디버거가 메모리 내 메타데이터 업데이트를 처리하도록 구성하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-325">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 <span data-ttu-id="cd4bb-326">[ICorDebugProcess8 인터페이스](icordebugprocess8-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-326">[ICorDebugProcess8 Interface](icordebugprocess8-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-327">논리적으로 확장 합니다 [ICorDebugProcess](icordebugprocess-interface.md) 인터페이스를 사용 하도록 설정 하거나 특정 유형의 사용 하지 않도록 [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) 예외 콜백을 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-327">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 <span data-ttu-id="cd4bb-328">[ICorDebugProcessEnum 인터페이스](icordebugprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-328">[ICorDebugProcessEnum Interface](icordebugprocessenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-329">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugProcess` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-329">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 <span data-ttu-id="cd4bb-330">[ICorDebugReferenceValue 인터페이스](icordebugreferencevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-330">[ICorDebugReferenceValue Interface](icordebugreferencevalue-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-331">참조 형식을 지원하는 `ICorDebugValue`의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-331">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 <span data-ttu-id="cd4bb-332">[ICorDebugRegisterSet 인터페이스](icordebugregisterset-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-332">[ICorDebugRegisterSet Interface](icordebugregisterset-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-333">코드가 실행되고 있는 컴퓨터에서 사용할 수 있는 레지스터 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-333">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 <span data-ttu-id="cd4bb-334">[ICorDebugRegisterSet2 인터페이스](icordebugregisterset2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-334">[ICorDebugRegisterSet2 Interface](icordebugregisterset2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-335">64개 이상의 레지스터가 있는 하드웨어 플랫폼의 `ICorDebugRegisterSet` 기능을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-335">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 <span data-ttu-id="cd4bb-336">[ICorDebugRemote 인터페이스](icordebugremote-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-336">[ICorDebugRemote Interface](icordebugremote-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-337">시작할 수 있거나 원격 대상 프로세스에 관리되는 디버거를 연결할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-337">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 <span data-ttu-id="cd4bb-338">[ICorDebugRemoteTarget 인터페이스](icordebugremotetarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-338">[ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-339">CLR 환경에서 Silverlight 기반 애플리케이션을 디버깅하는 데 사용할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-339">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="cd4bb-340">[ICorDebugRuntimeUnwindableFrame 인터페이스](icordebugruntimeunwindableframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-340">[ICorDebugRuntimeUnwindableFrame Interface](icordebugruntimeunwindableframe-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-341">프레임을 해제하는 데 CLR(공용 언어 런타임)을 필요로 하는 관리되지 않는 메서드에 대한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-341">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 <span data-ttu-id="cd4bb-342">[ICorDebugStackWalk 인터페이스](icordebugstackwalk-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-342">[ICorDebugStackWalk Interface](icordebugstackwalk-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-343">스레드 스택에서 관리되는 메서드나 프레임을 가져오기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-343">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 <span data-ttu-id="cd4bb-344">[ICorDebugStaticFieldSymbol 인터페이스](icordebugstaticfieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-344">[ICorDebugStaticFieldSymbol Interface](icordebugstaticfieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-345">정적 필드에 대한 디버그 기호 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-345">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="cd4bb-346">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd4bb-346">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd4bb-347">[ICorDebugStepper 인터페이스](icordebugstepper-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-347">[ICorDebugStepper Interface](icordebugstepper-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-348">디버거에서 수행하는 코드 실행 단계를 나타내며, 명령의 실행/완료를 구분하는 식별자로 사용되고, 단계를 취소하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-348">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 <span data-ttu-id="cd4bb-349">[ICorDebugStepper2 인터페이스](icordebugstepper2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-349">[ICorDebugStepper2 Interface](icordebugstepper2-interface1.md)</span></span>\
 <span data-ttu-id="cd4bb-350">JMC(내 코드만) 디버깅을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-350">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 <span data-ttu-id="cd4bb-351">[ICorDebugStepperEnum 인터페이스](icordebugstepperenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-351">[ICorDebugStepperEnum Interface](icordebugstepperenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-352">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugStepper` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-352">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 <span data-ttu-id="cd4bb-353">[ICorDebugStringValue 인터페이스](icordebugstringvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-353">[ICorDebugStringValue Interface](icordebugstringvalue-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-354">문자열 값에 적용되는 `ICorDebugHeapValue`의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-354">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 <span data-ttu-id="cd4bb-355">[ICorDebugSymbolProvider 인터페이스](icordebugsymbolprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-355">[ICorDebugSymbolProvider Interface](icordebugsymbolprovider-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-356">디버그 기호 정보를 검색하는 데 사용할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-356">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="cd4bb-357">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd4bb-357">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd4bb-358">[ICorDebugSymbolProvider2 인터페이스](icordebugsymbolprovider2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-358">[ICorDebugSymbolProvider2 Interface](icordebugsymbolprovider2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-359">논리적으로 확장 합니다 [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) 추가 디버그 기호 정보를 검색 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-359">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="cd4bb-360">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd4bb-360">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd4bb-361">[ICorDebugThread 인터페이스](icordebugthread-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-361">[ICorDebugThread Interface](icordebugthread-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-362">프로세스의 스레드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-362">Represents a thread in a process.</span></span> <span data-ttu-id="cd4bb-363">`ICorDebugThread` 인스턴스의 수명은 이 인스턴스가 나타내는 스레드의 수명과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-363">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 <span data-ttu-id="cd4bb-364">[ICorDebugThread2 인터페이스](icordebugthread2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-364">[ICorDebugThread2 Interface](icordebugthread2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-365">`ICorDebugThread`에서 논리적으로 확장된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-365">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 <span data-ttu-id="cd4bb-366">[ICorDebugThread3 인터페이스](icordebugthread3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-366">[ICorDebugThread3 Interface](icordebugthread3-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-367">진입점을 제공 합니다 [ICorDebugStackWalk](icordebugstackwalk-interface.md) 및 해당 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-367">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 <span data-ttu-id="cd4bb-368">[ICorDebugThread4 인터페이스](icordebugthread4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-368">[ICorDebugThread4 Interface](icordebugthread4-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-369">스레드 차단 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-369">Provides thread blocking information.</span></span>  
  
 <span data-ttu-id="cd4bb-370">[ICorDebugThreadEnum 인터페이스](icordebugthreadenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-370">[ICorDebugThreadEnum Interface](icordebugthreadenum-interface1.md)</span></span>\
 <span data-ttu-id="cd4bb-371">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugThread` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-371">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 <span data-ttu-id="cd4bb-372">[ICorDebugType 인터페이스](icordebugtype-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-372">[ICorDebugType Interface](icordebugtype-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-373">기본 또는 복합(즉, 사용자 정의) 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-373">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="cd4bb-374">형식이 제네릭이면 `ICorDebugType`는 인스턴스화된 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-374">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 <span data-ttu-id="cd4bb-375">[ICorDebugType2 인터페이스](icordebugtype2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-375">[ICorDebugType2 Interface](icordebugtype2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-376">확장 된 [ICorDebugType](icordebugtype-interface.md) 기본 형식 또는 복합 (사용자 정의 됨) 형식의 형식 식별자를 검색 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-376">Extends the [ICorDebugType](icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 <span data-ttu-id="cd4bb-377">[ICorDebugTypeEnum 인터페이스](icordebugtypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-377">[ICorDebugTypeEnum Interface](icordebugtypeenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-378">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugType` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-378">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 <span data-ttu-id="cd4bb-379">[ICorDebugUnmanagedCallback 인터페이스](icordebugunmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-379">[ICorDebugUnmanagedCallback Interface](icordebugunmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-380">CLR에 직접적으로 관련되지 않은 네이티브 이벤트에 대한 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-380">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="cd4bb-381">[ICorDebugValue](icordebugvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-381">[ICorDebugValue](icordebugvalue-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-382">디버깅 중인 프로세스의 읽기 또는 쓰기 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-382">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="cd4bb-383">[ICorDebugValue2](icordebugvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-383">[ICorDebugValue2](icordebugvalue2-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-384">`ICorDebugValue`을 지원하기 위해 `ICorDebugType`에서 확장된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-384">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="cd4bb-385">[ICorDebugValue3 인터페이스](icordebugvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-385">[ICorDebugValue3 Interface](icordebugvalue3-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-386">2GB 보다 큰 배열 지원 하기 위해 "ICorDebugValue" 및 "ICorDebugValue2" 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-386">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="cd4bb-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-388">특정 값에 액세스할 수 있도록 `ICorDebugBreakpoint`를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-388">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="cd4bb-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-390">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugValue` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-390">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 <span data-ttu-id="cd4bb-391">[ICorDebugVariableHome 인터페이스](icordebugvariablehome-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-391">[ICorDebugVariableHome Interface](icordebugvariablehome-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-392">지역 변수 또는 함수의 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-392">Represents a local variable or argument of a function.</span></span>  
  
 <span data-ttu-id="cd4bb-393">[ICorDebugVariableHomeEnum 인터페이스](icordebugvariablehomeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-393">[ICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-394">지역 변수 및 함수에 인수 하는 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-394">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="cd4bb-395">[ICorDebugVariableSymbol 인터페이스](icordebugvariablesymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-395">[ICorDebugVariableSymbol Interface](icordebugvariablesymbol-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-396">변수에 대한 디버그 기호 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-396">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="cd4bb-397">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd4bb-397">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd4bb-398">[ICorDebugVirtualUnwinder 인터페이스](icordebugvirtualunwinder-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-398">[ICorDebugVirtualUnwinder Interface](icordebugvirtualunwinder-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-399">스택 해제에 도움이 되는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-399">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="cd4bb-400">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd4bb-400">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="cd4bb-401">[ICorPublish 인터페이스](icorpublish-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-401">[ICorPublish Interface](icorpublish-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-402">게시 프로세스에 대한 일반적인 인터페이스로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-402">Serves as the general interface for the publishing processes.</span></span>  
  
 <span data-ttu-id="cd4bb-403">[ICorPublishAppDomain 인터페이스](icorpublishappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-403">[ICorPublishAppDomain Interface](icorpublishappdomain-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-404">애플리케이션 도메인을 나타내고 애플리케이션 도메인에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-404">Represents and provides information about an application domain.</span></span>  
  
 <span data-ttu-id="cd4bb-405">[ICorPublishAppDomainEnum 인터페이스](icorpublishappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-405">[ICorPublishAppDomainEnum Interface](icorpublishappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-406">프로세스 내에 현재 있는 `ICorPublishAppDomain` 개체의 컬렉션을 이동하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-406">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 <span data-ttu-id="cd4bb-407">[ICorPublishEnum 인터페이스](icorpublishenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-407">[ICorPublishEnum Interface](icorpublishenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-408">열거자를 게시하기 위한 추상 기본 열거형으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-408">Serves as the abstract base for publishing enumerators.</span></span>  
  
 <span data-ttu-id="cd4bb-409">[ICorPublishProcess 인터페이스](icorpublishprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-409">[ICorPublishProcess Interface](icorpublishprocess-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-410">프로세스에 대한 정보에 액세스하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-410">Provides methods that access information about a process.</span></span>  
  
 <span data-ttu-id="cd4bb-411">[ICorPublishProcessEnum 인터페이스](icorpublishprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-411">[ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-412">`ICorPublishProcess` 개체의 컬렉션을 이동하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-412">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  

 <span data-ttu-id="cd4bb-413">[ISOSDacInterface 인터페이스](isosdacinterface-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-413">[ISOSDacInterface Interface](isosdacinterface-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-414">데이터에 액세스할 도우미 메서드를 제공 `SOS`합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-414">Provides helper methods to access data from `SOS`.</span></span>

 <span data-ttu-id="cd4bb-415">[IXCLRDataMethodDefinition 인터페이스](ixclrdatamethoddefinition-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-415">[IXCLRDataMethodDefinition Interface](ixclrdatamethoddefinition-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-416">메서드 정의 대 한 정보를 쿼리 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-416">Provides methods for querying information about a method definition.</span></span>
 
 <span data-ttu-id="cd4bb-417">[IXCLRDataMethodInstance 인터페이스](ixclrdatamethodinstance-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-417">[IXCLRDataMethodInstance Interface](ixclrdatamethodinstance-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-418">메서드 인스턴스에 대 한 정보를 쿼리 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-418">Provides methods for querying information about a method instance.</span></span>
 
 <span data-ttu-id="cd4bb-419">[IXCLRDataModule 인터페이스](ixclrdatamodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-419">[IXCLRDataModule Interface](ixclrdatamodule-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-420">로드 된 모듈에 대 한 정보를 쿼리 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-420">Provides methods for querying information about a loaded module.</span></span>
 
 <span data-ttu-id="cd4bb-421">[IXCLRDataProcess 인터페이스](ixclrdataprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-421">[IXCLRDataProcess Interface](ixclrdataprocess-interface.md)</span></span>\
 <span data-ttu-id="cd4bb-422">프로세스에 대 한 정보를 쿼리 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4bb-422">Provides methods for querying information about a process.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="cd4bb-423">관련 단원</span><span class="sxs-lookup"><span data-stu-id="cd4bb-423">Related Sections</span></span>  
 <span data-ttu-id="cd4bb-424">[디버깅 Coclass](debugging-coclasses.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-424">[Debugging Coclasses](debugging-coclasses.md)</span></span>\
 <span data-ttu-id="cd4bb-425">[디버깅 전역 정적 함수](debugging-global-static-functions.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-425">[Debugging Global Static Functions](debugging-global-static-functions.md)</span></span>\
 <span data-ttu-id="cd4bb-426">[디버깅 열거형](debugging-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-426">[Debugging Enumerations](debugging-enumerations.md)</span></span>\
 <span data-ttu-id="cd4bb-427">[디버깅 구조체](debugging-structures.md)</span><span class="sxs-lookup"><span data-stu-id="cd4bb-427">[Debugging Structures](debugging-structures.md)</span></span>\
