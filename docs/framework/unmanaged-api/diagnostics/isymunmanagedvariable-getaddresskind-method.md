---
title: ISymUnmanagedVariable::GetAddressKind 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressKind
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressKind
helpviewer_keywords:
- GetAddressKind method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressKind method [.NET Framework debugging]
ms.assetid: a71563c0-62f2-4eb4-970c-825d61827613
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f5b4cb07cbc1ea3f8f297b96a124b8f5a04f0fce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647272"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="3fc16-102">ISymUnmanagedVariable::GetAddressKind 메서드</span><span class="sxs-lookup"><span data-stu-id="3fc16-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>
<span data-ttu-id="3fc16-103">이 변수의 주소가의 종류를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3fc16-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fc16-104">구문</span><span class="sxs-lookup"><span data-stu-id="3fc16-104">Syntax</span></span>  
  
```  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3fc16-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3fc16-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="3fc16-106">[out] 에 대 한 포인터를 `ULONG32` 값을 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="3fc16-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="3fc16-107">에 정의 된 가능한 값은 [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="3fc16-107">The possible values are defined in the [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3fc16-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="3fc16-108">Return Value</span></span>  
 <span data-ttu-id="3fc16-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="3fc16-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fc16-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3fc16-110">Requirements</span></span>  
 <span data-ttu-id="3fc16-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3fc16-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc16-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="3fc16-112">See also</span></span>
- [<span data-ttu-id="3fc16-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fc16-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
