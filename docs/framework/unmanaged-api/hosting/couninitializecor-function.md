---
title: "CoUninitializeCor 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoUninitializeCor
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CoUninitializeCor
helpviewer_keywords: CoUninitializeCor function [.NET Framework hosting]
ms.assetid: 50a95b8b-9766-470e-bb29-2c7ecddfd4a1
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9f50892b44cf8ce22cc126fe22323c8b0bbe6be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="couninitializecor-function"></a><span data-ttu-id="a3806-102">CoUninitializeCor 함수</span><span class="sxs-lookup"><span data-stu-id="a3806-102">CoUninitializeCor Function</span></span>
<span data-ttu-id="a3806-103">`CoUninitializeCor`는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3806-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3806-104">구문</span><span class="sxs-lookup"><span data-stu-id="a3806-104">Syntax</span></span>  
  
```  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="a3806-105">설명</span><span class="sxs-lookup"><span data-stu-id="a3806-105">Remarks</span></span>  
 <span data-ttu-id="a3806-106">공용 언어 런타임 프로세스에서 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3806-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="a3806-107">런타임에 실행 중인 프로세스에서를 완전히 제거 하려면 해당 프로세스를 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3806-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3806-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3806-108">See Also</span></span>  
 [<span data-ttu-id="a3806-109">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="a3806-109">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
