---
title: IAppIdAuthority 인터페이스
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 724ee01e91f1e9f4e34d2262610152a977ed4f53
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206657"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="00116-102">IAppIdAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00116-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="00116-103">생성 하 고 응용 프로그램 id 및 참조에 대 한 키를 비교 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="00116-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="00116-104">메서드</span><span class="sxs-lookup"><span data-stu-id="00116-104">Methods</span></span>  
  
|<span data-ttu-id="00116-105">메서드</span><span class="sxs-lookup"><span data-stu-id="00116-105">Method</span></span>|<span data-ttu-id="00116-106">설명</span><span class="sxs-lookup"><span data-stu-id="00116-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="00116-107">두 개의 지정 되었는지 여부를 나타내는 값을 가져옵니다 [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) 인스턴스는 서로 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00116-107">Gets a value that indicates whether the two specified [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="00116-108">가 해당 버전 정보를 무시 하도록 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00116-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="00116-109">두 개의 지정 되었는지 여부를 나타내는 값을 가져옵니다 [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) 인스턴스는 서로 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00116-109">Gets a value that indicates whether the two specified [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="00116-110">가 해당 버전 정보를 무시 하도록 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00116-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="00116-111">두 개의 지정 된 문자열 정의 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="00116-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="00116-112">가 해당 버전 정보를 무시 하도록 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00116-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="00116-113">두 개의 지정 된 문자열 참조 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="00116-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="00116-114">가 해당 버전 정보를 무시 하도록 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00116-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="00116-115">새로 생성 된 인터페이스 포인터를 가져옵니다 `IDefinitionAppId` 현재 범위에 있는 어셈블리를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="00116-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="00116-116">새로 만든 인터페이스 포인터를 가져옵니다 `IReferenceAppId` 현재 범위에서 어셈블리를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="00116-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="00116-117">지정 된 문자열 버전을 가져옵니다 `IDefinitionAppId`, 지정 된 플래그 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="00116-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="00116-118">나타내는 값을 가져옵니다 여부를 지정 된 `IDefinitionAppId` 및 `IReferenceAppId` 동일한 어셈블리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="00116-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="00116-119">지정한 정의 문자열 및 참조 문자열 같은 어셈블리를 나타내는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="00116-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="00116-120">지정 된 나타내는 문자열 키를 가져옵니다 `IDefinitionAppId` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="00116-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="00116-121">지정 된 나타내는 문자열 키를 가져옵니다 `IReferenceAppId` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="00116-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="00116-122">지정 된 해시 키를 가져옵니다 `IDefinitionAppId` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="00116-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="00116-123">지정 된 해시 키를 가져옵니다 `IReferenceAppId` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="00116-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="00116-124">지정 된 문자열 버전을 가져옵니다 `IReferenceAppId`, 지정 된 플래그 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="00116-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="00116-125">한 인터페이스 포인터를 가져옵니다는 `IDefinitionAppId` 지정 된 문자열 키에서 참조 되는 어셈블리를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="00116-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="00116-126">한 인터페이스 포인터를 가져옵니다는 `IReferenceAppId` 지정 된 문자열 키에서 참조 되는 어셈블리를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="00116-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="00116-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="00116-127">Requirements</span></span>  
 <span data-ttu-id="00116-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="00116-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00116-129">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="00116-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="00116-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00116-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00116-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="00116-131">See also</span></span>

- [<span data-ttu-id="00116-132">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00116-132">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
