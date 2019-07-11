---
title: ISymUnmanagedWriter::OpenScope 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenScope
helpviewer_keywords:
- OpenScope method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::OpenScope method [.NET Framework debugging]
ms.assetid: dbea0644-3873-4329-90b8-624163e87467
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fa6d563873045b4b5b427f06f0caa5420d31590b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777214"
---
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="f52be-102">ISymUnmanagedWriter::OpenScope 메서드</span><span class="sxs-lookup"><span data-stu-id="f52be-102">ISymUnmanagedWriter::OpenScope Method</span></span>
<span data-ttu-id="f52be-103">현재 메서드에서 새 어휘 범위를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f52be-103">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="f52be-104">범위는 현재 범위가 새 하 고 범위 스택에 푸시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f52be-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="f52be-105">범위 계층 구조를 형성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f52be-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="f52be-106">형제 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f52be-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f52be-107">구문</span><span class="sxs-lookup"><span data-stu-id="f52be-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f52be-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f52be-108">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="f52be-109">[in] 오프셋 (바이트)를 메서드의 시작 부분에서 어휘 범위에서 첫 번째 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="f52be-109">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="f52be-110">[out] 에 대 한 포인터를 `ULONG32` 범위 식별자를 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="f52be-110">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f52be-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="f52be-111">Return Value</span></span>  
 <span data-ttu-id="f52be-112">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f52be-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f52be-113">설명</span><span class="sxs-lookup"><span data-stu-id="f52be-113">Remarks</span></span>  
 <span data-ttu-id="f52be-114">`ISymUnmanagedWriter::OpenScope` 사용 하 여 사용할 수 있는 불투명 한 범위 식별자를 반환 합니다 [isymunmanagedwriter:: Setscoperange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) 범위를 정의 하의 시작과 끝 이후에 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="f52be-114">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="f52be-115">이 경우에 전달 된 오프셋 `ISymUnmanagedWriter::OpenScope` 하 고 [isymunmanagedwriter:: Closescope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f52be-115">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="f52be-116">범위 식별자는 현재 메서드에서만에서 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="f52be-116">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f52be-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f52be-117">Requirements</span></span>  
 <span data-ttu-id="f52be-118">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f52be-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f52be-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="f52be-119">See also</span></span>

- [<span data-ttu-id="f52be-120">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f52be-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
