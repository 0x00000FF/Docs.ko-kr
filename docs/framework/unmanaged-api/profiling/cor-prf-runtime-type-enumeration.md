---
title: COR_PRF_RUNTIME_TYPE 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_RUNTIME_TYPE Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_RUNTIME_TYPE
helpviewer_keywords:
- COR_PRF_RUNTIME_TYPE enumeration [.NET Framework profiling]
ms.assetid: 35449514-333f-4918-9c60-7aa198d655d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e57c622780f0bc92061fd2928ea861f904d9eb37
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122111"
---
# <a name="corprfruntimetype-enumeration"></a><span data-ttu-id="23ba1-102">COR_PRF_RUNTIME_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="23ba1-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="23ba1-103">CLR (공용 언어 런타임)의 버전을 나타내는 값을 포함 합니다: 데스크톱 또는 silverlight에서는 CoreCLR 합니다.</span><span class="sxs-lookup"><span data-stu-id="23ba1-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23ba1-104">구문</span><span class="sxs-lookup"><span data-stu-id="23ba1-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="23ba1-105">멤버</span><span class="sxs-lookup"><span data-stu-id="23ba1-105">Members</span></span>  
  
|<span data-ttu-id="23ba1-106">멤버</span><span class="sxs-lookup"><span data-stu-id="23ba1-106">Member</span></span>|<span data-ttu-id="23ba1-107">설명</span><span class="sxs-lookup"><span data-stu-id="23ba1-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="23ba1-108">CLR의 데스크톱 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="23ba1-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="23ba1-109">Silverlight에서 사용 되는 CLR의 core 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="23ba1-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23ba1-110">설명</span><span class="sxs-lookup"><span data-stu-id="23ba1-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23ba1-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="23ba1-111">Requirements</span></span>  
 <span data-ttu-id="23ba1-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="23ba1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23ba1-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="23ba1-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="23ba1-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23ba1-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="23ba1-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="23ba1-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="23ba1-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="23ba1-116">See also</span></span>

- [<span data-ttu-id="23ba1-117">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="23ba1-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
