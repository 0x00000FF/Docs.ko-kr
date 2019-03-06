---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod 메서드
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84aef2b26e008d1a3c6d95d7ec1e130ab0594a11
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484552"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="3feb6-102">ISymUnmanagedAsyncMethod::GetKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="3feb6-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="3feb6-103">참조 [DefineKickoffMethod 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3feb6-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3feb6-104">구문</span><span class="sxs-lookup"><span data-stu-id="3feb6-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3feb6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3feb6-105">Parameters</span></span>  
  
|<span data-ttu-id="3feb6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3feb6-106">Parameter</span></span>|<span data-ttu-id="3feb6-107">설명</span><span class="sxs-lookup"><span data-stu-id="3feb6-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="3feb6-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="3feb6-108">Return Value</span></span>  
 <span data-ttu-id="3feb6-109">`HRESULT`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3feb6-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3feb6-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3feb6-110">Requirements</span></span>  
 <span data-ttu-id="3feb6-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3feb6-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3feb6-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="3feb6-112">See also</span></span>
- [<span data-ttu-id="3feb6-113">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3feb6-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
