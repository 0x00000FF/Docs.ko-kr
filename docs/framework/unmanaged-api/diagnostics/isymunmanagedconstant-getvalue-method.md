---
title: ISymUnmanagedConstant::GetValue 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetValue
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type:
- apiref
ms.openlocfilehash: 00be35e9a15349b8bca5f76b948b8477dd240888
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449246"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="fe2d6-102">ISymUnmanagedConstant::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="fe2d6-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="fe2d6-103">상수 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fe2d6-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe2d6-104">구문</span><span class="sxs-lookup"><span data-stu-id="fe2d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe2d6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fe2d6-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="fe2d6-106">제한이 값을 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fe2d6-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe2d6-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="fe2d6-107">Return Value</span></span>  
 <span data-ttu-id="fe2d6-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="fe2d6-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe2d6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fe2d6-109">Requirements</span></span>  
 <span data-ttu-id="fe2d6-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="fe2d6-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe2d6-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe2d6-111">See also</span></span>

- [<span data-ttu-id="fe2d6-112">ISymUnmanagedConstant 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe2d6-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="fe2d6-113">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="fe2d6-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="fe2d6-114">GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="fe2d6-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
