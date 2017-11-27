---
title: "IMetaDataImport::GetUserString 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetUserString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetUserString
helpviewer_keywords:
- IMetaDataImport::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0fd3bb47-58b5-4083-b241-b9719df7a285
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 340d5cdfcb218f74a43ed6e88f5175a1d215a1b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="a9673-102">IMetaDataImport::GetUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="a9673-102">IMetaDataImport::GetUserString Method</span></span>
<span data-ttu-id="a9673-103">지정한 메타데이터 토큰이 나타내는 리터럴 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a9673-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9673-104">구문</span><span class="sxs-lookup"><span data-stu-id="a9673-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9673-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a9673-105">Parameters</span></span>  
 `stk`  
 <span data-ttu-id="a9673-106">[in] 에 대 한 연결된 문자열을 반환 하는 문자열 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a9673-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="a9673-107">[out] 요청된 된 문자열의 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="a9673-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="a9673-108">[in] 최대 요청 된 와이드 문자 크기 `szString`합니다.</span><span class="sxs-lookup"><span data-stu-id="a9673-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="a9673-109">[out] 반환 된 와이드 문자에서 크기 `szString`합니다.</span><span class="sxs-lookup"><span data-stu-id="a9673-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9673-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9673-110">Requirements</span></span>  
 <span data-ttu-id="a9673-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a9673-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9673-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a9673-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9673-113">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a9673-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9673-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9673-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9673-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9673-115">See Also</span></span>  
 [<span data-ttu-id="a9673-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a9673-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a9673-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a9673-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
