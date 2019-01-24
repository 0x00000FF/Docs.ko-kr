---
title: COR_DEBUG_IL_TO_NATIVE_MAP 구조체
ms.date: 03/30/2017
api_name:
- COR_DEBUG_IL_TO_NATIVE_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: 06f3b504-085f-4142-934a-25381fe23d4c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56d4255b06f1317c87685737e4ee4021c37a77f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555013"
---
# <a name="cordebugiltonativemap-structure"></a><span data-ttu-id="ab8c0-102">COR_DEBUG_IL_TO_NATIVE_MAP 구조체</span><span class="sxs-lookup"><span data-stu-id="ab8c0-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="ab8c0-103">MSIL(Microsoft Intermediate Language) 코드를 네이티브 코드에 매핑하는 데 사용되는 오프셋을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ab8c0-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab8c0-104">구문</span><span class="sxs-lookup"><span data-stu-id="ab8c0-104">Syntax</span></span>  
  
```  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="ab8c0-105">멤버</span><span class="sxs-lookup"><span data-stu-id="ab8c0-105">Members</span></span>  
  
|<span data-ttu-id="ab8c0-106">멤버</span><span class="sxs-lookup"><span data-stu-id="ab8c0-106">Member</span></span>|<span data-ttu-id="ab8c0-107">설명</span><span class="sxs-lookup"><span data-stu-id="ab8c0-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="ab8c0-108">MSIL 코드의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="ab8c0-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="ab8c0-109">네이티브 코드의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="ab8c0-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="ab8c0-110">네이티브 코드의 끝 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="ab8c0-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ab8c0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ab8c0-111">Requirements</span></span>  
 <span data-ttu-id="ab8c0-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ab8c0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab8c0-113">**헤더:** CorProf.idl, CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="ab8c0-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="ab8c0-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab8c0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab8c0-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab8c0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab8c0-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="ab8c0-116">See also</span></span>
- [<span data-ttu-id="ab8c0-117">GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="ab8c0-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="ab8c0-118">GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="ab8c0-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="ab8c0-119">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="ab8c0-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="ab8c0-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="ab8c0-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
