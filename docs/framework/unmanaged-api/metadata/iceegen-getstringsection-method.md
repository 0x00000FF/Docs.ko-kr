---
title: ICeeGen::GetStringSection 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.GetStringSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetStringSection
helpviewer_keywords:
- ICeeGen::GetStringSection method [.NET Framework metadata]
- GetStringSection method [.NET Framework metadata]
ms.assetid: a2267d39-69d1-4de1-bf37-f752cafacc71
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0e306ccc824910226e522bc664f8f87f828a0d52
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477051"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="a002d-102">ICeeGen::GetStringSection 메서드</span><span class="sxs-lookup"><span data-stu-id="a002d-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="a002d-103">지정된 된 핸들에서 참조 하는 코드 섹션의 문자열 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a002d-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="a002d-104">이 메서드는 사용 되지 않습니다 및 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a002d-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a002d-105">구문</span><span class="sxs-lookup"><span data-stu-id="a002d-105">Syntax</span></span>  
  
```  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a002d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a002d-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="a002d-107">[out에서] 코드 섹션에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="a002d-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a002d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a002d-108">Requirements</span></span>  
 <span data-ttu-id="a002d-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a002d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a002d-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a002d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a002d-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="a002d-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a002d-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a002d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a002d-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="a002d-113">See also</span></span>
- [<span data-ttu-id="a002d-114">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a002d-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
