---
title: "IManagedObject::GetSerializedBuffer 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IManagedObject.GetSerializedBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetSerializedBuffer
helpviewer_keywords:
- IManagedObject::GetSerializedBuffer method [.NET Framework hosting]
- GetSerializedBuffer method [.NET Framework hosting]
ms.assetid: c17105bb-b49f-434e-8f9b-77f8c85b9220
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d8ae9edab2ca943fc6fb265ab698c2c82d6c531b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="94ed4-102">IManagedObject::GetSerializedBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="94ed4-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="94ed4-103">이 관리 되는 개체의 문자열 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94ed4-104">구문</span><span class="sxs-lookup"><span data-stu-id="94ed4-104">Syntax</span></span>  
  
```  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="94ed4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="94ed4-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="94ed4-106">[out] 직렬화 된 개체를 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94ed4-107">설명</span><span class="sxs-lookup"><span data-stu-id="94ed4-107">Remarks</span></span>  
 <span data-ttu-id="94ed4-108">`GetSerializedBuffer` 메서드는 클라이언트에 마샬링할 수 있도록 개체를 직렬화 합니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94ed4-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94ed4-109">Requirements</span></span>  
 <span data-ttu-id="94ed4-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94ed4-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="94ed4-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94ed4-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="94ed4-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94ed4-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94ed4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94ed4-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94ed4-114">See Also</span></span>  
 [<span data-ttu-id="94ed4-115">IManagedObject 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94ed4-115">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
