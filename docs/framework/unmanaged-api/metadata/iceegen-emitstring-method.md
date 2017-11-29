---
title: "ICeeGen::EmitString 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.EmitString
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::EmitString
helpviewer_keywords:
- EmitString method [.NET Framework metadata]
- ICeeGen::EmitString method [.NET Framework metadata]
ms.assetid: ad2710a7-edb8-4493-8619-3fce235e3334
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f988e54a37212beeeebfbef15e6b148021e0b759
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="3f575-102">ICeeGen::EmitString 메서드</span><span class="sxs-lookup"><span data-stu-id="3f575-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="3f575-103">코드 베이스에 지정 된 문자열을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3f575-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="3f575-104">이 메서드는 사용 되지 않으며 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f575-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f575-105">구문</span><span class="sxs-lookup"><span data-stu-id="3f575-105">Syntax</span></span>  
  
```  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f575-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3f575-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="3f575-107">[in] 내보내는 데 사용 되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3f575-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="3f575-108">[out] 내보낸된 문자열의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3f575-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f575-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f575-109">Requirements</span></span>  
 <span data-ttu-id="3f575-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f575-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f575-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3f575-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3f575-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="3f575-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3f575-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f575-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f575-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f575-114">See Also</span></span>  
 [<span data-ttu-id="3f575-115">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f575-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
