---
title: "ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2f8a89532999f599c8ec595fa709044b7d13a53a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="fb0ed-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 메서드</span><span class="sxs-lookup"><span data-stu-id="fb0ed-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="fb0ed-103">매핑 정보 토큰 소스 범위에 대 한 특수 한 사용자 지정 데이터 섹션을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ed-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="fb0ed-104">이 닫힌 후에 매핑 정보가 더 이상 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ed-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb0ed-105">구문</span><span class="sxs-lookup"><span data-stu-id="fb0ed-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fb0ed-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="fb0ed-106">Return Value</span></span>  
 <span data-ttu-id="fb0ed-107">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ed-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb0ed-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb0ed-108">Requirements</span></span>  
 <span data-ttu-id="fb0ed-109">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fb0ed-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb0ed-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb0ed-110">See Also</span></span>  
 [<span data-ttu-id="fb0ed-111">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb0ed-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
