---
title: ICorDebugRemoteTarget 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget
helpviewer_keywords:
- ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3eb57295b72dade0bb396b3caa724b21722b26db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743506"
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="2f3e1-102">ICorDebugRemoteTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f3e1-102">ICorDebugRemoteTarget Interface</span></span>
<span data-ttu-id="2f3e1-103">개발자가 CLR(공용 언어 런타임) 환경에서 Silverlight 기반 응용 프로그램을 디버깅하는 데 사용할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2f3e1-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f3e1-104">구문</span><span class="sxs-lookup"><span data-stu-id="2f3e1-104">Syntax</span></span>  
  
```  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2f3e1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2f3e1-105">Methods</span></span>  
  
|<span data-ttu-id="2f3e1-106">메서드</span><span class="sxs-lookup"><span data-stu-id="2f3e1-106">Method</span></span>|<span data-ttu-id="2f3e1-107">설명</span><span class="sxs-lookup"><span data-stu-id="2f3e1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2f3e1-108">ICorDebugRemoteTarget::GetHostName 메서드</span><span class="sxs-lookup"><span data-stu-id="2f3e1-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="2f3e1-109">원격 컴퓨터의 IP 주소나 호스트 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2f3e1-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f3e1-110">설명</span><span class="sxs-lookup"><span data-stu-id="2f3e1-110">Remarks</span></span>  
 <span data-ttu-id="2f3e1-111">Windows 95, Windows 98, Windows ME 또는 x86이 아닌 플랫폼(IA-64, AMD64 등)에서는 관리 코드와 네이티브 코드가 혼합된 혼합 모드에서의 디버깅이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f3e1-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f3e1-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f3e1-112">Requirements</span></span>  
 <span data-ttu-id="2f3e1-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f3e1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f3e1-114">**헤더:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="2f3e1-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="2f3e1-115">**라이브러리:** : CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f3e1-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f3e1-116">**.NET framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="2f3e1-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f3e1-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="2f3e1-117">See also</span></span>
- [<span data-ttu-id="2f3e1-118">ICorDebugRemote 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f3e1-118">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="2f3e1-119">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f3e1-119">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="2f3e1-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f3e1-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
