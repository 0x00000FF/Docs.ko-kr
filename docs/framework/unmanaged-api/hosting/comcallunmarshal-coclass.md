---
title: ComCallUnmarshal Coclass
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ComCallUnmarshal Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: ComCallUnmarshal
helpviewer_keywords: ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2760fc84466c85e022421bcc17dcee6444ec859a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="1f6b9-102">ComCallUnmarshal Coclass</span><span class="sxs-lookup"><span data-stu-id="1f6b9-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="1f6b9-103">인터페이스 포인터의 마샬링을 관리 하기 위한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6b9-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f6b9-104">구문</span><span class="sxs-lookup"><span data-stu-id="1f6b9-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="1f6b9-105">인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f6b9-105">Interfaces</span></span>  
  
|<span data-ttu-id="1f6b9-106">인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f6b9-106">Interface</span></span>|<span data-ttu-id="1f6b9-107">설명</span><span class="sxs-lookup"><span data-stu-id="1f6b9-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="1f6b9-108">초기화, 만들고 관리 하기 위한 클라이언트 프로세스에서 프록시 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6b9-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1f6b9-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f6b9-109">Requirements</span></span>  
 <span data-ttu-id="1f6b9-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6b9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f6b9-111">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="1f6b9-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="1f6b9-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1f6b9-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1f6b9-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f6b9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f6b9-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f6b9-114">See Also</span></span>  
 [<span data-ttu-id="1f6b9-115">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="1f6b9-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
