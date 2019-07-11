---
title: AssemblyComparisonResult 열거형
ms.date: 03/30/2017
api_name:
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6c417eec9583ff069c9d61fa31e9c14f3931130
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778514"
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="1c188-102">AssemblyComparisonResult 열거형</span><span class="sxs-lookup"><span data-stu-id="1c188-102">AssemblyComparisonResult Enumeration</span></span>
<span data-ttu-id="1c188-103">상응 하는 두 개의 어셈블리 id 기준으로 나타냅니다 합니다 [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1c188-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c188-104">구문</span><span class="sxs-lookup"><span data-stu-id="1c188-104">Syntax</span></span>  
  
```cpp  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,   
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,    
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,      
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,    
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion    
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a><span data-ttu-id="1c188-105">멤버</span><span class="sxs-lookup"><span data-stu-id="1c188-105">Members</span></span>  
  
|<span data-ttu-id="1c188-106">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="1c188-106">Member name</span></span>|<span data-ttu-id="1c188-107">Description</span><span class="sxs-lookup"><span data-stu-id="1c188-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="1c188-108">모든 어셈블리 비교 일치 항목에 필드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c188-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="1c188-109">어셈블리 동일 하다 고 간주 어셈블리 버전 번호는.NET Framework 버전 2.0의 공용 언어 런타임 버전 (CLR) 통합 기반을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c188-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="1c188-110">.NET Framework 2.0에서 어셈블리 버전 번호의 CLR 통합에 따라 어셈블리가 부분적으로 일치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c188-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="1c188-111">어셈블리의 부분 일치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c188-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="1c188-112">어셈블리 버전 번호의 레거시 통합에 따라 부분적으로 일치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c188-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="1c188-113">단순한 이름의 어셈블리를 부분적으로 일치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c188-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="1c188-114">어셈블리 동일 하다 고 간주 레거시 버전의.NET Framework 버전 번호의 CLR 통합에 기반을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c188-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="1c188-115">해당 버전 번호는 무시 하는 두 명의 단순한 이름의 어셈블리 간에 일치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c188-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="1c188-116">일치 항목이 없는 두 어셈블리 간에 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c188-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="1c188-117">두 어셈블리를 부분적 으로만 일치 하는 해당 버전 번호와 일치 하는지 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c188-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="1c188-118">두 어셈블리 해당 버전 번호는 일치 하지 않는 일치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c188-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="1c188-119">알 수 없는 같지 않은 이유는 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c188-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1c188-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c188-120">Requirements</span></span>  
 <span data-ttu-id="1c188-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c188-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c188-122">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="1c188-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1c188-123">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1c188-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1c188-124">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c188-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c188-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="1c188-125">See also</span></span>

- [<span data-ttu-id="1c188-126">CompareAssemblyIdentity 함수</span><span class="sxs-lookup"><span data-stu-id="1c188-126">CompareAssemblyIdentity Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)
- [<span data-ttu-id="1c188-127">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="1c188-127">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
