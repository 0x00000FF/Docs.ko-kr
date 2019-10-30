---
title: IReferenceAppId 인터페이스
ms.date: 03/30/2017
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
ms.openlocfilehash: 6f20fb2e9e026253fb02b47dfcd63cf655acc4ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131654"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="b7c6a-102">IReferenceAppId 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7c6a-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="b7c6a-103">현재 범위의 응용 프로그램에 대 한 고유 식별자에 대 한 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7c6a-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7c6a-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b7c6a-104">Methods</span></span>  
  
|<span data-ttu-id="b7c6a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b7c6a-105">Method</span></span>|<span data-ttu-id="b7c6a-106">설명</span><span class="sxs-lookup"><span data-stu-id="b7c6a-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="b7c6a-107">이 `IReferenceAppId`에서 참조 하는 응용 프로그램의 코드 식별자에 대 한 문자열 표현에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b7c6a-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="b7c6a-108">이 `IReferenceAppId`에서 참조 하는 응용 프로그램에 대 한 코드 식별자를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c6a-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="b7c6a-109">이 `IReferenceAppId`의 멤버를 나타내는 `IReferenceIdentity` 인스턴스를 포함 하는 `IEnumReferenceIdentity` 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b7c6a-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="b7c6a-110">이 `IReferenceAppId`에 대 한 구독의 토큰 식별자에 대 한 문자열 표현에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b7c6a-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="b7c6a-111">이 `IReferenceAppId`에 대 한 구독의 토큰 식별자를 지정 된 문자열 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c6a-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b7c6a-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7c6a-112">Requirements</span></span>  
 <span data-ttu-id="b7c6a-113">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7c6a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7c6a-114">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="b7c6a-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="b7c6a-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7c6a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7c6a-116">참조</span><span class="sxs-lookup"><span data-stu-id="b7c6a-116">See also</span></span>

- [<span data-ttu-id="b7c6a-117">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7c6a-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="b7c6a-118">IEnumReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7c6a-118">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)
- [<span data-ttu-id="b7c6a-119">IReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7c6a-119">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
