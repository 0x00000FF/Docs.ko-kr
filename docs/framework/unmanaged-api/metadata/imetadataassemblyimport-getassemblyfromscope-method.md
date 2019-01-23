---
title: IMetaDataAssemblyImport::GetAssemblyFromScope 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope method [.NET Framework metadata]
- GetAssemblyFromScope method [.NET Framework metadata]
ms.assetid: 0b437f70-561d-48c7-abe0-0cb9ace10c08
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7914257d167d0f54d3625d252076576e5e40296b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634950"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="625ca-102">IMetaDataAssemblyImport::GetAssemblyFromScope 메서드</span><span class="sxs-lookup"><span data-stu-id="625ca-102">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>
<span data-ttu-id="625ca-103">현재 범위에서 어셈블리에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="625ca-103">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="625ca-104">구문</span><span class="sxs-lookup"><span data-stu-id="625ca-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="625ca-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="625ca-105">Parameters</span></span>  
 `ptkAssembly`  
 <span data-ttu-id="625ca-106">[out] 검색에 대 한 포인터 `mdAssembly` 어셈블리를 식별 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="625ca-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="625ca-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="625ca-107">Requirements</span></span>  
 <span data-ttu-id="625ca-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="625ca-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="625ca-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="625ca-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="625ca-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="625ca-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="625ca-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="625ca-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="625ca-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="625ca-112">See also</span></span>
- [<span data-ttu-id="625ca-113">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="625ca-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
