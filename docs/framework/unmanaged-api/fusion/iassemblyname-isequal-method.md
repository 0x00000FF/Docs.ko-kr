---
title: IAssemblyName::IsEqual 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyName.IsEqual
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::IsEqual
helpviewer_keywords:
- IsEqual method [.NET Framework fusion]
- IAssemblyName::IsEqual method [.NET Framework fusion]
ms.assetid: 6dfc220f-d0d4-45b3-bfce-5829f817766f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70784106798748eeaabd8e6b6c3787e27b0ece74
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746676"
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="7b371-102">IAssemblyName::IsEqual 메서드</span><span class="sxs-lookup"><span data-stu-id="7b371-102">IAssemblyName::IsEqual Method</span></span>
<span data-ttu-id="7b371-103">지정 된 결정 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 개체와 같으면이 `IAssemblyName`지정된 된 비교 플래그에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b371-103">Determines whether a specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b371-104">구문</span><span class="sxs-lookup"><span data-stu-id="7b371-104">Syntax</span></span>  
  
```  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b371-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7b371-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="7b371-106">[in] 합니다 `IAssemblyName` 비교 하는 개체 `IAssemblyName`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b371-106">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="7b371-107">[in] 비트 조합 [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) 비교에 영향을 주는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7b371-107">[in] A bitwise combination of [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b371-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b371-108">Requirements</span></span>  
 <span data-ttu-id="7b371-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7b371-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b371-110">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="7b371-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7b371-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b371-111">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b371-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="7b371-112">See also</span></span>
- [<span data-ttu-id="7b371-113">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b371-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="7b371-114">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="7b371-114">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
