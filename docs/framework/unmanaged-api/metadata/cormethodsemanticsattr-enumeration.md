---
title: CorMethodSemanticsAttr 열거형
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f888c39160e52e550d07f58b9c5bcd11fd625658
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564083"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="cba62-102">CorMethodSemanticsAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="cba62-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="cba62-103">메서드와 관련 속성 또는 이벤트 간의 관계를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cba62-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cba62-104">구문</span><span class="sxs-lookup"><span data-stu-id="cba62-104">Syntax</span></span>  
  
```  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="cba62-105">멤버</span><span class="sxs-lookup"><span data-stu-id="cba62-105">Members</span></span>  
  
|<span data-ttu-id="cba62-106">멤버</span><span class="sxs-lookup"><span data-stu-id="cba62-106">Member</span></span>|<span data-ttu-id="cba62-107">설명</span><span class="sxs-lookup"><span data-stu-id="cba62-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="cba62-108">메서드는 지정 된 `set` 속성 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="cba62-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="cba62-109">메서드는 지정 된 `get` 속성 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="cba62-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="cba62-110">메서드는 속성 또는 여기에 정의 된 것과 다른 이벤트에 대 한 관계를 갖도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cba62-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="cba62-111">메서드를 이벤트 처리기 메서드를 추가 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cba62-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="cba62-112">메서드를 이벤트 처리기 메서드를 제거 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cba62-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="cba62-113">메서드는 이벤트 발생 하는지 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cba62-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cba62-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cba62-114">Requirements</span></span>  
 <span data-ttu-id="cba62-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cba62-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cba62-116">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="cba62-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="cba62-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cba62-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cba62-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="cba62-118">See also</span></span>
- [<span data-ttu-id="cba62-119">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="cba62-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
