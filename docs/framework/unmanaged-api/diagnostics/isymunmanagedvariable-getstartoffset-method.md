---
title: ISymUnmanagedVariable::GetStartOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f551e2f8a89cf2988ce43bf72a1e87e0ddaf713
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543213"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="3821b-102">ISymUnmanagedVariable::GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="3821b-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>
<span data-ttu-id="3821b-103">부모 내에서이 변수의 시작 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3821b-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="3821b-104">범위 내에서 로컬 변수 이면 시작 오프셋 범위에 대해 정의 된 오프셋 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3821b-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3821b-105">구문</span><span class="sxs-lookup"><span data-stu-id="3821b-105">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3821b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3821b-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="3821b-107">[out] 에 대 한 포인터를 `ULONG32` 시작 오프셋을 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="3821b-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3821b-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="3821b-108">Return Value</span></span>  
 <span data-ttu-id="3821b-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="3821b-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3821b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3821b-110">Requirements</span></span>  
 <span data-ttu-id="3821b-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3821b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3821b-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="3821b-112">See also</span></span>
- [<span data-ttu-id="3821b-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3821b-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="3821b-114">GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="3821b-114">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)
