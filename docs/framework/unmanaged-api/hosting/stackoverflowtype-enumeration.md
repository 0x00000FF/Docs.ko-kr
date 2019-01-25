---
title: StackOverflowType 열거형
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06c9119a2b842a0efcd4af752ba72dbfda03bf13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54653864"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="0ae21-102">StackOverflowType 열거형</span><span class="sxs-lookup"><span data-stu-id="0ae21-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="0ae21-103">스택 오버플로 이벤트의 근본 원인을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae21-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ae21-104">구문</span><span class="sxs-lookup"><span data-stu-id="0ae21-104">Syntax</span></span>  
  
```  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="0ae21-105">멤버</span><span class="sxs-lookup"><span data-stu-id="0ae21-105">Members</span></span>  
  
|<span data-ttu-id="0ae21-106">멤버</span><span class="sxs-lookup"><span data-stu-id="0ae21-106">Member</span></span>|<span data-ttu-id="0ae21-107">설명</span><span class="sxs-lookup"><span data-stu-id="0ae21-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="0ae21-108">실행 엔진에서 스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae21-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="0ae21-109">관리 코드에서 스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae21-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="0ae21-110">비관리 코드에서 스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae21-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ae21-111">설명</span><span class="sxs-lookup"><span data-stu-id="0ae21-111">Remarks</span></span>  
 <span data-ttu-id="0ae21-112">이 정보는 호출을 통해 호스트에 전달 된 [iactiononclrevent:: Onevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="0ae21-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ae21-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ae21-113">Requirements</span></span>  
 <span data-ttu-id="0ae21-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0ae21-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ae21-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0ae21-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ae21-116">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0ae21-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ae21-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ae21-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ae21-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="0ae21-118">See also</span></span>
- [<span data-ttu-id="0ae21-119">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="0ae21-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
