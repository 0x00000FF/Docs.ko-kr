---
title: ISymUnmanagedBinder::GetReaderFromStream 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderFromStream
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 630895e131c2b3fd5a175a7a3c45140ad65d03aa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503036"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="28ca2-102">ISymUnmanagedBinder::GetReaderFromStream 메서드</span><span class="sxs-lookup"><span data-stu-id="28ca2-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="28ca2-103">지정 된 메타 데이터 인터페이스 및 기호 저장소를 포함 하는 스트림을 올바른 반환 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 디버깅 읽을 구조에서 지정 된 기호 저장소 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="28ca2-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28ca2-104">구문</span><span class="sxs-lookup"><span data-stu-id="28ca2-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28ca2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="28ca2-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="28ca2-106">[in] 메타 데이터 가져오기 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="28ca2-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="28ca2-107">[in] 기호 저장소를 포함 하는 스트림에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="28ca2-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="28ca2-108">[out] 설정 된 포인터를 반환 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="28ca2-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28ca2-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="28ca2-109">Return Value</span></span>  
 <span data-ttu-id="28ca2-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="28ca2-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28ca2-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="28ca2-111">Requirements</span></span>  
 <span data-ttu-id="28ca2-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="28ca2-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28ca2-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="28ca2-113">See also</span></span>
- [<span data-ttu-id="28ca2-114">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="28ca2-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
