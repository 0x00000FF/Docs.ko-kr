---
title: IDefinitionAppId 인터페이스
ms.date: 03/30/2017
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e8bb31967a6ad515761e6cd03657f2c834debe5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545558"
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="51cd6-102">IDefinitionAppId 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51cd6-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="51cd6-103">현재 범위에서 응용 프로그램을 정의 하는 코드에 대 한 고유 식별자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="51cd6-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51cd6-104">메서드</span><span class="sxs-lookup"><span data-stu-id="51cd6-104">Methods</span></span>  
  
|<span data-ttu-id="51cd6-105">메서드</span><span class="sxs-lookup"><span data-stu-id="51cd6-105">Method</span></span>|<span data-ttu-id="51cd6-106">설명</span><span class="sxs-lookup"><span data-stu-id="51cd6-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="51cd6-107">이 코드를 나타내는 형식이 지정 된 문자열을 가져옵니다 `IDefinitionAppId` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="51cd6-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="51cd6-108">이 코드를 설정 `IDefinitionAppId` 를 지정 된 형식의 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="51cd6-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="51cd6-109">한 인터페이스 포인터를 가져옵니다는 [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) 현재 응용 프로그램 경로의 어셈블리가 포함 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="51cd6-109">Gets an interface pointer to an [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="51cd6-110">지정 된 참조 하는 값을 현재 범위에서 어셈블리에 대 한 응용 프로그램 경로 설정 [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="51cd6-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="51cd6-111">이 구독에 대 한 토큰 식별자의 문자열 표현으로 포인터를 가져옵니다 `IDefinitionAppId` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="51cd6-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="51cd6-112">이 구독에 대 한 토큰 식별자를 설정 하는 `IDefinitionAppId` 개체 지정된 된 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="51cd6-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="51cd6-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="51cd6-113">Requirements</span></span>  
 <span data-ttu-id="51cd6-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="51cd6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51cd6-115">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="51cd6-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="51cd6-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51cd6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51cd6-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="51cd6-117">See also</span></span>
- [<span data-ttu-id="51cd6-118">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51cd6-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
