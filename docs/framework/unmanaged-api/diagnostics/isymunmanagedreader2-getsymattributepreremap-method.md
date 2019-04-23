---
title: ISymUnmanagedReader2::GetSymAttributePreRemap 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetSymAttributePreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 543a8015e944333942b619060059273577902a74
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110294"
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a><span data-ttu-id="910ff-102">ISymUnmanagedReader2::GetSymAttributePreRemap 메서드</span><span class="sxs-lookup"><span data-stu-id="910ff-102">ISymUnmanagedReader2::GetSymAttributePreRemap Method</span></span>
<span data-ttu-id="910ff-103">해당 이름을 기준으로 사용자 지정 특성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="910ff-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="910ff-104">이러한 특성은 메타 데이터 사용자 지정 특성을 달리 기호 저장소에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="910ff-104">Unlike metadata custom attributes, these attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="910ff-105">구문</span><span class="sxs-lookup"><span data-stu-id="910ff-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="910ff-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="910ff-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="910ff-107">[in] 부모 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="910ff-107">[in] The metadata token of the parent.</span></span>  
  
 `name`  
 <span data-ttu-id="910ff-108">[in] 에 대 한 포인터를 `WCHAR` 이름을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="910ff-108">[in] A pointer to a `WCHAR` that contains the name.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="910ff-109">[in] A `ULONG32` 의 크기를 나타내는 `buffer` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="910ff-109">[in] A `ULONG32` that indicates the size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="910ff-110">[out] 에 대 한 포인터를 `ULONG32` 특성 바이트를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="910ff-110">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the attribute bytes.</span></span>  
  
 `buffer`  
 <span data-ttu-id="910ff-111">[out] 특성 바이트를 받는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="910ff-111">[out] A pointer to the buffer that receives the attribute bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="910ff-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="910ff-112">Return Value</span></span>  
 <span data-ttu-id="910ff-113">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="910ff-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="910ff-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="910ff-114">Requirements</span></span>  
 <span data-ttu-id="910ff-115">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="910ff-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="910ff-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="910ff-116">See also</span></span>

- [<span data-ttu-id="910ff-117">ISymUnmanagedReader2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="910ff-117">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
