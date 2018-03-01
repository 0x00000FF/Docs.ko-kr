---
title: "ISymUnmanagedVariable::GetAttributes 메서드"
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
- ISymUnmanagedVariable.GetAttributes
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAttributes
helpviewer_keywords:
- GetAttributes method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAttributes method [.NET Framework debugging]
ms.assetid: 80f168af-a6a6-4c8f-b9e6-8a82dc834ed5
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4fa57fcb214f465a57af9638d6f5a44acf746225
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="628b1-102">ISymUnmanagedVariable::GetAttributes 메서드</span><span class="sxs-lookup"><span data-stu-id="628b1-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="628b1-103">이 변수에 대 한 특성 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="628b1-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="628b1-104">구문</span><span class="sxs-lookup"><span data-stu-id="628b1-104">Syntax</span></span>  
  
```  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="628b1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="628b1-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="628b1-106">[out] 에 대 한 포인터는 `ULONG32` 받는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="628b1-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="628b1-107">반환 된 값에 정의 된 값 중 하나가 됩니다는 [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="628b1-107">The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="628b1-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="628b1-108">Return Value</span></span>  
 <span data-ttu-id="628b1-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="628b1-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="628b1-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="628b1-110">Requirements</span></span>  
 <span data-ttu-id="628b1-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="628b1-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="628b1-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="628b1-112">See Also</span></span>  
 [<span data-ttu-id="628b1-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="628b1-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
