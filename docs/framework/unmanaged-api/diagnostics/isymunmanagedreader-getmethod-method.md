---
title: "ISymUnmanagedReader::GetMethod 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7af3f56bc258ba48abba5cba4230de3ca6904ec0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="d9d06-102">ISymUnmanagedReader::GetMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="d9d06-102">ISymUnmanagedReader::GetMethod Method</span></span>
<span data-ttu-id="d9d06-103">메서드 토큰이 지정 된 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d9d06-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9d06-104">구문</span><span class="sxs-lookup"><span data-stu-id="d9d06-104">Syntax</span></span>  
  
```  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9d06-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d9d06-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="d9d06-106">[in] 메서드 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d9d06-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="d9d06-107">[out] 반환 되는 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d9d06-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9d06-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="d9d06-108">Return Value</span></span>  
 <span data-ttu-id="d9d06-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d9d06-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9d06-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d9d06-110">Requirements</span></span>  
 <span data-ttu-id="d9d06-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d9d06-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9d06-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9d06-112">See Also</span></span>  
 [<span data-ttu-id="d9d06-113">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d9d06-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
