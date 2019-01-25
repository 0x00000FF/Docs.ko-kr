---
title: ICeeGen::AddSectionReloc 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.AddSectionReloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a8e270f45300bd5f8c2e6cd87f9b84f31ec42320
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722194"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="0dc80-102">ICeeGen::AddSectionReloc 메서드</span><span class="sxs-lookup"><span data-stu-id="0dc80-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="0dc80-103">코드 베이스.reloc 명령을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc80-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="0dc80-104">이 메서드는 사용 되지 않습니다 및 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc80-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dc80-105">구문</span><span class="sxs-lookup"><span data-stu-id="0dc80-105">Syntax</span></span>  
  
```  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0dc80-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0dc80-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="0dc80-107">[in] .Reloc 명령을 추가 하는 메모리 내 코드의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="0dc80-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="0dc80-108">[in] 섹션의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="0dc80-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="0dc80-109">[in] 섹션 `offset` 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc80-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="0dc80-110">[in] 중 하나는 [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) 추가할.reloc 명령의 종류를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0dc80-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dc80-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0dc80-111">Requirements</span></span>  
 <span data-ttu-id="0dc80-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0dc80-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dc80-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0dc80-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0dc80-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="0dc80-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0dc80-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dc80-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dc80-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="0dc80-116">See also</span></span>
- [<span data-ttu-id="0dc80-117">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0dc80-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
