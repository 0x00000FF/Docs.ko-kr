---
title: "ISymUnmanagedWriter::RemapToken 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.RemapToken
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 857b68c0443e7b23af30ed64ecc9b78af0b40880
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="127a3-102">ISymUnmanagedWriter::RemapToken 메서드</span><span class="sxs-lookup"><span data-stu-id="127a3-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="127a3-103">메타 데이터를 내보낼 처럼 메타 데이터 토큰을 다시 매핑할 된 기호 작성기에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="127a3-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="127a3-104">기호 작성기가 이전 토큰 기호 저장소를 저장, 업데이트를 하거나 새 값으로 저장 된 토큰 읽기 단계 중에 다시 매핑하려면 해당 기호 판독기에 대 한 맵을 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="127a3-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="127a3-105">구문</span><span class="sxs-lookup"><span data-stu-id="127a3-105">Syntax</span></span>  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="127a3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="127a3-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="127a3-107">[in] 메타 데이터 토큰 다시 매핑된입니다.</span><span class="sxs-lookup"><span data-stu-id="127a3-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="127a3-108">[in] 새 메타 데이터 토큰을 `oldToken` 다시 매핑 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="127a3-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="127a3-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="127a3-109">Return Value</span></span>  
 <span data-ttu-id="127a3-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="127a3-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="127a3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="127a3-111">Requirements</span></span>  
 <span data-ttu-id="127a3-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="127a3-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="127a3-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="127a3-113">See Also</span></span>  
 [<span data-ttu-id="127a3-114">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="127a3-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
