---
title: ISymUnmanagedMethod::GetNamespace 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetNamespace
helpviewer_keywords:
- ISymUnmanagedMethod::GetNamespace method [.NET Framework debugging]
- GetNamespace method [.NET Framework debugging]
ms.assetid: 7fbbac42-b966-406d-9ae9-67bf3aea74ce
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53a47cf67edb36b06c92be83cb23c2e1dd1e75cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424432"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="b1b81-102">ISymUnmanagedMethod::GetNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="b1b81-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="b1b81-103">이 메서드가 정의 된 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b1b81-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1b81-104">구문</span><span class="sxs-lookup"><span data-stu-id="b1b81-104">Syntax</span></span>  
  
```  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1b81-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b1b81-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="b1b81-106">[out] 설정 된 포인터를 반환 되 [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b1b81-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1b81-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="b1b81-107">Return Value</span></span>  
 <span data-ttu-id="b1b81-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b1b81-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1b81-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b1b81-109">Requirements</span></span>  
 <span data-ttu-id="b1b81-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b1b81-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1b81-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1b81-111">See Also</span></span>  
 [<span data-ttu-id="b1b81-112">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1b81-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
