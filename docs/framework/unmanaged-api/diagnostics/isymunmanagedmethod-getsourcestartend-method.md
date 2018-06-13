---
title: ISymUnmanagedMethod::GetSourceStartEnd 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSourceStartEnd
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1e15bab136540c73f8e1cff0e6bb52ec1d6c0063
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426226"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="76dd5-102">ISymUnmanagedMethod::GetSourceStartEnd 메서드</span><span class="sxs-lookup"><span data-stu-id="76dd5-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>
<span data-ttu-id="76dd5-103">이 방법의 원본에 대 한 시작 및 끝 문서 위치를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="76dd5-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="76dd5-104">첫 번째 배열 위치 시작, 이며 두 번째 배열 위치 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="76dd5-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76dd5-105">구문</span><span class="sxs-lookup"><span data-stu-id="76dd5-105">Syntax</span></span>  
  
```  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76dd5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="76dd5-106">Parameters</span></span>  
 `docs`  
 <span data-ttu-id="76dd5-107">[in] 시작 및 종료 소스 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="76dd5-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="76dd5-108">[in] 소스 문서 시작 및 종료 줄입니다 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="76dd5-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="76dd5-109">[in] 소스 문서의 시작 및 끝 열에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="76dd5-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="76dd5-110">[out] `true` 위치 고, 그렇지 않으면 정의 되었으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="76dd5-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76dd5-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="76dd5-111">Return Value</span></span>  
 <span data-ttu-id="76dd5-112">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="76dd5-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76dd5-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76dd5-113">Requirements</span></span>  
 <span data-ttu-id="76dd5-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="76dd5-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76dd5-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76dd5-115">See Also</span></span>  
 [<span data-ttu-id="76dd5-116">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76dd5-116">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
