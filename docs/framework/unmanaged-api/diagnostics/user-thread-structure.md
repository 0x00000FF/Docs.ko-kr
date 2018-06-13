---
title: USER_THREAD 구조체
ms.date: 03/30/2017
api_name:
- USER_THREAD
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- USER_THREAD
helpviewer_keywords:
- USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 93e96d6f8570e6aef7bfc18ef2859dc1e86ec8fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429033"
---
# <a name="userthread-structure"></a><span data-ttu-id="d486d-102">USER_THREAD 구조체</span><span class="sxs-lookup"><span data-stu-id="d486d-102">USER_THREAD Structure</span></span>
<span data-ttu-id="d486d-103">디버거가 스레드에 대 한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d486d-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="d486d-104">자세한 내용은 참조는 [inotifysource2:: Setnotifyfilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="d486d-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d486d-105">구문</span><span class="sxs-lookup"><span data-stu-id="d486d-105">Syntax</span></span>  
  
```  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="d486d-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d486d-106">Members</span></span>  
  
|<span data-ttu-id="d486d-107">멤버</span><span class="sxs-lookup"><span data-stu-id="d486d-107">Member</span></span>|<span data-ttu-id="d486d-108">설명</span><span class="sxs-lookup"><span data-stu-id="d486d-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="d486d-109">스레드 버퍼의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d486d-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="d486d-110">스레드 버퍼의 바이트의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="d486d-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="d486d-111">스레드 id입니다.</span><span class="sxs-lookup"><span data-stu-id="d486d-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d486d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d486d-112">Requirements</span></span>  
 <span data-ttu-id="d486d-113">**헤더:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="d486d-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d486d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d486d-114">See Also</span></span>  
 [<span data-ttu-id="d486d-115">SetNotifyFilter 메서드</span><span class="sxs-lookup"><span data-stu-id="d486d-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)  
 [<span data-ttu-id="d486d-116">진단 기호 저장소 구조체</span><span class="sxs-lookup"><span data-stu-id="d486d-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
