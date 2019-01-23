---
title: CeeSectionRelocExtra 공용 구조체
ms.date: 03/30/2017
api_name:
- CeeSectionRelocExtra Union
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocExtra
helpviewer_keywords:
- CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d6a5673c2aaf287131274b0c590f00a69c64fed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517151"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="73027-102">CeeSectionRelocExtra 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="73027-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="73027-103">사용 되는 주소 오프셋을 나타내는 합니다 [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) 인터페이스에서 섹션을 재배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="73027-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73027-104">구문</span><span class="sxs-lookup"><span data-stu-id="73027-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="73027-105">멤버</span><span class="sxs-lookup"><span data-stu-id="73027-105">Members</span></span>  
  
|<span data-ttu-id="73027-106">멤버</span><span class="sxs-lookup"><span data-stu-id="73027-106">Member</span></span>|<span data-ttu-id="73027-107">설명</span><span class="sxs-lookup"><span data-stu-id="73027-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="73027-108">섹션에 대 한 상위 주소 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="73027-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73027-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="73027-109">Requirements</span></span>  
 <span data-ttu-id="73027-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="73027-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73027-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="73027-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="73027-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="73027-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="73027-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73027-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73027-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="73027-114">See also</span></span>
- [<span data-ttu-id="73027-115">메타데이터 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="73027-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
