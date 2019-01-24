---
title: IDENTITY_ATTRIBUTE 구조체
ms.date: 03/30/2017
api_name:
- IDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE
helpviewer_keywords:
- IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e26a90b6725d53774053293c04842b761da6ab12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717677"
---
# <a name="identityattribute-structure"></a><span data-ttu-id="ed32e-102">IDENTITY_ATTRIBUTE 구조체</span><span class="sxs-lookup"><span data-stu-id="ed32e-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="ed32e-103">에 대 한 메타 데이터 특성 정보를 [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="ed32e-103">Contains metadata attribute information about an [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed32e-104">구문</span><span class="sxs-lookup"><span data-stu-id="ed32e-104">Syntax</span></span>  
  
```  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="ed32e-105">멤버</span><span class="sxs-lookup"><span data-stu-id="ed32e-105">Members</span></span>  
  
|<span data-ttu-id="ed32e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="ed32e-106">Member</span></span>|<span data-ttu-id="ed32e-107">설명</span><span class="sxs-lookup"><span data-stu-id="ed32e-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="ed32e-108">네임 스페이스를 포함 하는 null로 끝나는 문자열에 대 한 포인터에서 특성이입니다.</span><span class="sxs-lookup"><span data-stu-id="ed32e-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="ed32e-109">특성의 이름이 포함 된 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ed32e-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="ed32e-110">특성의 값이 포함 된 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ed32e-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed32e-111">설명</span><span class="sxs-lookup"><span data-stu-id="ed32e-111">Remarks</span></span>  
 <span data-ttu-id="ed32e-112">`IDENTITY_ATTRIBUTE` 구조 null로 끝나는 문자열에 대 한 세 포인터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed32e-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="ed32e-113">이러한 세 가지 문자열 특성 하나를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ed32e-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="ed32e-114">인스턴스를 `IDENTITY_ATTRIBUTE` 구조체의 인스턴스를 사용 하 여 연결 된를 [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="ed32e-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="ed32e-115">합니다 `IDENTITY_ATTRIBUTE` 실제 문자열 및 해당 구조에 포함 되어 있습니다 `IDENTITY_ATTRIBUTE_BLOB` 구조에 나열 된 세 개의 문자열에 오프셋을 나열 합니다 `IDENTITY_ATTRIBUTE` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="ed32e-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed32e-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed32e-116">Requirements</span></span>  
 <span data-ttu-id="ed32e-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ed32e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed32e-118">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="ed32e-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="ed32e-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed32e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed32e-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="ed32e-120">See also</span></span>
- [<span data-ttu-id="ed32e-121">IDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed32e-121">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
- [<span data-ttu-id="ed32e-122">IDENTITY_ATTRIBUTE_BLOB 구조체</span><span class="sxs-lookup"><span data-stu-id="ed32e-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)
- [<span data-ttu-id="ed32e-123">Fusion 구조체</span><span class="sxs-lookup"><span data-stu-id="ed32e-123">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
