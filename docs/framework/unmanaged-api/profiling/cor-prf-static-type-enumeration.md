---
title: COR_PRF_STATIC_TYPE 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_STATIC_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_STATIC_TYPE
helpviewer_keywords:
- COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 753c3b38187dd69593dcb0520acef9ce4b137039
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751903"
---
# <a name="corprfstatictype-enumeration"></a><span data-ttu-id="e8679-102">COR_PRF_STATIC_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="e8679-102">COR_PRF_STATIC_TYPE Enumeration</span></span>
<span data-ttu-id="e8679-103">필드가 정적인지 여부와 정적인 경우 필드에 적용될 정적 품질을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e8679-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="e8679-104">비트 OR 연산을 사용 하 여 필드에 여러 개의 있음을 나타내기 위해 이러한 값을 결합할 수 있습니다 다른 정적 품질입니다.</span><span class="sxs-lookup"><span data-stu-id="e8679-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8679-105">구문</span><span class="sxs-lookup"><span data-stu-id="e8679-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="e8679-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e8679-106">Members</span></span>  
  
|<span data-ttu-id="e8679-107">멤버</span><span class="sxs-lookup"><span data-stu-id="e8679-107">Member</span></span>|<span data-ttu-id="e8679-108">설명</span><span class="sxs-lookup"><span data-stu-id="e8679-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="e8679-109">필드가 static이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e8679-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="e8679-110">필드에는 응용 프로그램 도메인 정적입니다.</span><span class="sxs-lookup"><span data-stu-id="e8679-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="e8679-111">필드는 스레드에 정적인입니다.</span><span class="sxs-lookup"><span data-stu-id="e8679-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="e8679-112">필드에는 컨텍스트 정적입니다.</span><span class="sxs-lookup"><span data-stu-id="e8679-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="e8679-113">필드는 가상 RVA (상대 주소)-고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8679-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e8679-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e8679-114">Requirements</span></span>  
 <span data-ttu-id="e8679-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e8679-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8679-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e8679-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e8679-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8679-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8679-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8679-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8679-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="e8679-119">See also</span></span>

- [<span data-ttu-id="e8679-120">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="e8679-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
