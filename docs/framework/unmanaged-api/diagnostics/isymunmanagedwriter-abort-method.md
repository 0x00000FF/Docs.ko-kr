---
title: "ISymUnmanagedWriter::Abort 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Abort
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 29dd11972e8db80f36820bba1eb679070d02146e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="4ce94-102">ISymUnmanagedWriter::Abort 메서드</span><span class="sxs-lookup"><span data-stu-id="4ce94-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="4ce94-103">기호를 기호 저장소로 커밋하지 않고 기호 작성기를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce94-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="4ce94-104">이 호출 후 기호 작성기 추가로 업데이트할 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ce94-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="4ce94-105">사용 하 여 커밋의 기호를 기호 작성기를 닫으려면는 [isymunmanagedwriter:: Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce94-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ce94-106">구문</span><span class="sxs-lookup"><span data-stu-id="4ce94-106">Syntax</span></span>  
  
```  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4ce94-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="4ce94-107">Return Value</span></span>  
 <span data-ttu-id="4ce94-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4ce94-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ce94-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ce94-109">Requirements</span></span>  
 <span data-ttu-id="4ce94-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4ce94-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ce94-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ce94-111">See Also</span></span>  
 [<span data-ttu-id="4ce94-112">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ce94-112">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
