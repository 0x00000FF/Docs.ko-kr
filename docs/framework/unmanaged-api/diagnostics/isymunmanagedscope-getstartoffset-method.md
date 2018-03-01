---
title: "ISymUnmanagedScope::GetStartOffset 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9e0328af628eec062dc9efa7012bbeff213f1b86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="7a570-102">ISymUnmanagedScope::GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="7a570-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="7a570-103">이 범위에 대 한 시작 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7a570-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a570-104">구문</span><span class="sxs-lookup"><span data-stu-id="7a570-104">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a570-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7a570-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="7a570-106">[out] 에 대 한 포인터는 `ULONG32` 시작 오프셋을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a570-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a570-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="7a570-107">Return Value</span></span>  
 <span data-ttu-id="7a570-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7a570-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a570-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7a570-109">Requirements</span></span>  
 <span data-ttu-id="7a570-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7a570-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a570-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a570-111">See Also</span></span>  
 [<span data-ttu-id="7a570-112">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a570-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="7a570-113">GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="7a570-113">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)
