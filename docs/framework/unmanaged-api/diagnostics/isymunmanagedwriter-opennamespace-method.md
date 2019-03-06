---
title: ISymUnmanagedWriter::OpenNamespace 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4cf0fbcbf6af53c6a7865e2a2cf7874ea44581e4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474620"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="32670-102">ISymUnmanagedWriter::OpenNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="32670-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="32670-103">새 네임스페이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="32670-103">Opens a new namespace.</span></span> <span data-ttu-id="32670-104">메서드 또는 네임 스페이스를 차지 하는 변수를 정의 하기 전에이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="32670-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="32670-105">네임 스페이스를 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32670-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32670-106">구문</span><span class="sxs-lookup"><span data-stu-id="32670-106">Syntax</span></span>  
  
```  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32670-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32670-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="32670-108">[in] 새 네임 스페이스의 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="32670-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32670-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="32670-109">Return Value</span></span>  
 <span data-ttu-id="32670-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="32670-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32670-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32670-111">Requirements</span></span>  
 <span data-ttu-id="32670-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="32670-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32670-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="32670-113">See also</span></span>
- [<span data-ttu-id="32670-114">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32670-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="32670-115">CloseNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="32670-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
