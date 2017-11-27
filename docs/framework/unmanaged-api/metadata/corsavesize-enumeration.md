---
title: "CorSaveSize 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSaveSize
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSaveSize
helpviewer_keywords: CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 34d4d42c7cf385bca77de37dce52689778aa5b1f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="7b2f6-102">CorSaveSize 열거형</span><span class="sxs-lookup"><span data-stu-id="7b2f6-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="7b2f6-103">저장 작업의 크기를 쿼리할 때 필요한 전체 자릿수 수준을 나타내는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b2f6-104">구문</span><span class="sxs-lookup"><span data-stu-id="7b2f6-104">Syntax</span></span>  
  
```  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="7b2f6-105">멤버</span><span class="sxs-lookup"><span data-stu-id="7b2f6-105">Members</span></span>  
  
|<span data-ttu-id="7b2f6-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7b2f6-106">Member</span></span>|<span data-ttu-id="7b2f6-107">설명</span><span class="sxs-lookup"><span data-stu-id="7b2f6-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="7b2f6-108">반환 값은 정확 하 게 해야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="7b2f6-109">반환 값을 예상할 수 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="7b2f6-110">삭제 가능한 형식을 제거 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7b2f6-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b2f6-111">Requirements</span></span>  
 <span data-ttu-id="7b2f6-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b2f6-113">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="7b2f6-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7b2f6-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="7b2f6-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7b2f6-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b2f6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b2f6-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b2f6-116">See Also</span></span>  
 [<span data-ttu-id="7b2f6-117">메타 데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="7b2f6-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
