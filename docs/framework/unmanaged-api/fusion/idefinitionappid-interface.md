---
title: "IDefinitionAppId 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDefinitionAppId
api_location: fusion.dll
api_type: COM
f1_keywords: IDefinitionAppId
helpviewer_keywords: IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 382c82ff773d0ab1c046fc131fa87a4f74d19ea6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="8f1e1-102">IDefinitionAppId 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f1e1-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="8f1e1-103">현재 범위에서 응용 프로그램을 정의 하는 코드에 대 한 고유 식별자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8f1e1-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f1e1-104">메서드</span><span class="sxs-lookup"><span data-stu-id="8f1e1-104">Methods</span></span>  
  
|<span data-ttu-id="8f1e1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8f1e1-105">Method</span></span>|<span data-ttu-id="8f1e1-106">설명</span><span class="sxs-lookup"><span data-stu-id="8f1e1-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="8f1e1-107">이 코드를 표현 하는 형식이 지정 된 문자열을 가져옵니다 `IDefinitionAppId` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8f1e1-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="8f1e1-108">이 코드를 설정 `IDefinitionAppId` 를 지정 된 형식의 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8f1e1-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="8f1e1-109">한 인터페이스 포인터를 가져옵니다는 [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) 현재 응용 프로그램 경로에 어셈블리를 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8f1e1-109">Gets an interface pointer to an [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="8f1e1-110">지정 된 참조 하는 값을 현재 범위에서 어셈블리에 대 한 응용 프로그램 경로 설정 [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8f1e1-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="8f1e1-111">이 구독에 대 한 토큰 식별자의 문자열 표현에 대 한 포인터를 가져옵니다 `IDefinitionAppId` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8f1e1-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="8f1e1-112">이 구독에 대 한 토큰 식별자를 설정 `IDefinitionAppId` 개체를 지정 된 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8f1e1-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f1e1-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f1e1-113">Requirements</span></span>  
 <span data-ttu-id="8f1e1-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8f1e1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f1e1-115">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="8f1e1-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="8f1e1-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f1e1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f1e1-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f1e1-117">See Also</span></span>  
 [<span data-ttu-id="8f1e1-118">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f1e1-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
