---
title: ICorDebugRemote 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugRemote
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemote
helpviewer_keywords:
- ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: 53d073c6-fa02-40d2-82e1-b9452bb6abaa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbed34f53ff43ca7887a58b3c879eaa74703da3e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744754"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="d187f-102">ICorDebugRemote 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d187f-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="d187f-103">시작할 수 있거나 원격 대상 프로세스에 관리되는 디버거를 연결할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d187f-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d187f-104">구문</span><span class="sxs-lookup"><span data-stu-id="d187f-104">Syntax</span></span>  
  
```cpp  
interface ICorDebugRemote : IUnknown  
{  
    HRESULT CreateProcessEx  
      (  
      [in] ICorDebugRemoteTarget *     pRemoteTarget,  
      [in] LPCWSTR                     lpApplicationName,  
      [in] LPWSTR                      lpCommandLine,  
      [in] LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
      [in] LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
      [in] BOOL                        bInheritHandles,  
      [in] DWORD                       dwCreationFlags,  
      [in] PVOID                       lpEnvironment,  
      [in] LPCWSTR                     lpCurrentDirectory,  
      [in] LPSTARTUPINFOW              lpStartupInfo,  
      [in] LPPROCESS_INFORMATION       lpProcessInformation,  
      [in] CorDebugCreateProcessFlags  debuggingFlags,  
      [out] ICorDebugProcess **        ppProcess  
      );  
  
    HRESULT DebugActiveProcessEx  
      (  
      [in] ICorDebugRemoteTarget *   pRemoteTarget,  
      [in] DWORD                     dwProcessId,  
      [in] BOOL                      fWin32Attach,  
      [out] ICorDebugProcess **      ppProcess  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d187f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d187f-105">Methods</span></span>  
  
|<span data-ttu-id="d187f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="d187f-106">Method</span></span>|<span data-ttu-id="d187f-107">설명</span><span class="sxs-lookup"><span data-stu-id="d187f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d187f-108">ICorDebugRemote::CreateProcessEx 메서드</span><span class="sxs-lookup"><span data-stu-id="d187f-108">ICorDebugRemote::CreateProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-createprocessex-method.md)|<span data-ttu-id="d187f-109">관리 되는 디버깅에 대 한 원격 컴퓨터에서 프로세스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d187f-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="d187f-110">ICorDebugRemote::DebugActiveProcessEx 메서드</span><span class="sxs-lookup"><span data-stu-id="d187f-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="d187f-111">디버거에서 원격 컴퓨터의 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d187f-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d187f-112">설명</span><span class="sxs-lookup"><span data-stu-id="d187f-112">Remarks</span></span>  
 <span data-ttu-id="d187f-113">현재,이 기능은 원격 Macintosh 컴퓨터에서 실행 되는 Silverlight 기반 응용 프로그램 대상 디버깅에 대해서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d187f-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d187f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d187f-114">Requirements</span></span>  
 <span data-ttu-id="d187f-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d187f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d187f-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d187f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d187f-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d187f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d187f-118">**.NET framework 버전:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="d187f-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d187f-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="d187f-119">See also</span></span>

- [<span data-ttu-id="d187f-120">ICorDebugRemoteTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d187f-120">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="d187f-121">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d187f-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="d187f-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d187f-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
