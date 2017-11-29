---
title: "COR_PRF_GC_REASON 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_REASON
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_REASON
helpviewer_keywords: COR_PRF_GC_REASON enumeration [.NET Framework profiling]
ms.assetid: 72822b95-a7fb-485e-9d55-1cb016d9a458
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7a5797c3e629bc87caf40b187bba47bc1cffbfdf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corprfgcreason-enumeration"></a><span data-ttu-id="0533d-102">COR_PRF_GC_REASON 열거형</span><span class="sxs-lookup"><span data-stu-id="0533d-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="0533d-103">가비지 컬렉션이 수행되는 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0533d-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0533d-104">구문</span><span class="sxs-lookup"><span data-stu-id="0533d-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="0533d-105">멤버</span><span class="sxs-lookup"><span data-stu-id="0533d-105">Members</span></span>  
  
|<span data-ttu-id="0533d-106">멤버</span><span class="sxs-lookup"><span data-stu-id="0533d-106">Member</span></span>|<span data-ttu-id="0533d-107">설명</span><span class="sxs-lookup"><span data-stu-id="0533d-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="0533d-108">가비지 수집이 발생 하 여 한 <xref:System.GC.Collect%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="0533d-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="0533d-109">이유 지정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="0533d-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0533d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0533d-110">Requirements</span></span>  
 <span data-ttu-id="0533d-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0533d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0533d-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0533d-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0533d-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0533d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0533d-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0533d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0533d-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0533d-115">See Also</span></span>  
 [<span data-ttu-id="0533d-116">프로 파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="0533d-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
