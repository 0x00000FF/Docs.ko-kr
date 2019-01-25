---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 메서드
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce4b41854d5d9324169b1873f431ef81c0a4c5be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677920"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="c2621-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 메서드</span><span class="sxs-lookup"><span data-stu-id="c2621-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="c2621-103">매핑 정보 토큰-소스 범위에 대 한 특별 한 사용자 지정 데이터 섹션을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="c2621-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="c2621-104">이 닫힌 후에 매핑 정보가 더 이상 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2621-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2621-105">구문</span><span class="sxs-lookup"><span data-stu-id="c2621-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c2621-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="c2621-106">Return Value</span></span>  
 <span data-ttu-id="c2621-107">`HRESULT`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c2621-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2621-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2621-108">Requirements</span></span>  
 <span data-ttu-id="c2621-109">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c2621-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2621-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="c2621-110">See also</span></span>
- [<span data-ttu-id="c2621-111">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2621-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
