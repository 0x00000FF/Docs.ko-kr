---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 049f8e4d04498b70533134c01765af2d996d86dc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499108"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="7b121-102">ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="7b121-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="7b121-103">경우 메서드가 async 정보 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b121-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="7b121-104">이 메서드가 반환 하는 경우 `FALSE` 이 인터페이스에서 다른 메서드를 호출 하는 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b121-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="7b121-105">모든 반환 되며이 `E_UNEXPECTED` 이 경우.</span><span class="sxs-lookup"><span data-stu-id="7b121-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b121-106">구문</span><span class="sxs-lookup"><span data-stu-id="7b121-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b121-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7b121-107">Parameters</span></span>  
  
|<span data-ttu-id="7b121-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7b121-108">Parameter</span></span>|<span data-ttu-id="7b121-109">설명</span><span class="sxs-lookup"><span data-stu-id="7b121-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="7b121-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="7b121-110">Return Value</span></span>  
 <span data-ttu-id="7b121-111">`HRESULT`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7b121-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b121-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b121-112">Requirements</span></span>  
 <span data-ttu-id="7b121-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7b121-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b121-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="7b121-114">See also</span></span>
- [<span data-ttu-id="7b121-115">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b121-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
