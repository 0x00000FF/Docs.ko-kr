---
title: "IMetaDataImport::IsValidToken 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.IsValidToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3c916e71518ded93c90b270205dd975201762846
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="35862-102">IMetaDataImport::IsValidToken 메서드</span><span class="sxs-lookup"><span data-stu-id="35862-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="35862-103">지정한 토큰이 코드 개체에 대한 유효한 참조를 포함하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="35862-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35862-104">구문</span><span class="sxs-lookup"><span data-stu-id="35862-104">Syntax</span></span>  
  
```  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35862-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="35862-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="35862-106">[in] 에 대 한 참조 유효성을 검사 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="35862-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35862-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="35862-107">Return Value</span></span>  
 <span data-ttu-id="35862-108">`true`경우 `tk` 현재 범위 내 올바른 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="35862-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="35862-109">그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="35862-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35862-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="35862-110">Requirements</span></span>  
 <span data-ttu-id="35862-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="35862-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35862-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="35862-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35862-113">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="35862-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="35862-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35862-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35862-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35862-115">See Also</span></span>  
 [<span data-ttu-id="35862-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35862-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="35862-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35862-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
