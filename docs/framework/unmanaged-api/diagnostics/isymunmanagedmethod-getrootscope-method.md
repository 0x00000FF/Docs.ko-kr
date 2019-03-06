---
title: ISymUnmanagedMethod::GetRootScope 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRootScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b55b379f0b2e47acbec03eebf92e1e107a52f918
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502951"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="e259b-102">ISymUnmanagedMethod::GetRootScope 메서드</span><span class="sxs-lookup"><span data-stu-id="e259b-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="e259b-103">이 메서드 내에서 루트 어휘 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e259b-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="e259b-104">이 범위는 전체 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e259b-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e259b-105">구문</span><span class="sxs-lookup"><span data-stu-id="e259b-105">Syntax</span></span>  
  
```  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e259b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e259b-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="e259b-107">[out] 설정 된 포인터를 반환 [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e259b-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e259b-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="e259b-108">Return Value</span></span>  
 <span data-ttu-id="e259b-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e259b-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e259b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e259b-110">Requirements</span></span>  
 <span data-ttu-id="e259b-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e259b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e259b-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="e259b-112">See also</span></span>
- [<span data-ttu-id="e259b-113">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e259b-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
