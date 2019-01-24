---
title: ISymUnmanagedNamespace::GetVariables 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11a5eb01a3e354b4360bea59af1e63ffeb0576aa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730115"
---
# <a name="isymunmanagednamespacegetvariables-method"></a><span data-ttu-id="b3129-102">ISymUnmanagedNamespace::GetVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="b3129-102">ISymUnmanagedNamespace::GetVariables Method</span></span>
<span data-ttu-id="b3129-103">이 네임 스페이스 내에서 전역 범위에서 정의 된 모든 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3129-103">Returns all variables defined at global scope within this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3129-104">구문</span><span class="sxs-lookup"><span data-stu-id="b3129-104">Syntax</span></span>  
  
```  
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b3129-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b3129-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="b3129-106">[in] A `ULONG32` 의 크기를 나타내는 `pVars` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b3129-106">[in] A `ULONG32` that indicates the size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="b3129-107">[out] 에 대 한 포인터를 `ULONG32` 네임 스페이스를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3129-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `pVars`  
 <span data-ttu-id="b3129-108">[out] 네임 스페이스를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b3129-108">[out] A pointer to a buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3129-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="b3129-109">Return Value</span></span>  
 <span data-ttu-id="b3129-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b3129-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3129-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3129-111">Requirements</span></span>  
 <span data-ttu-id="b3129-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b3129-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3129-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="b3129-113">See also</span></span>
- [<span data-ttu-id="b3129-114">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3129-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
