---
title: IMetaDataEmit::DefinePermissionSet 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePermissionSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4188d1ef83f685bf39bdf951939e0ec6493b323d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466403"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="523cc-102">IMetaDataEmit::DefinePermissionSet 메서드</span><span class="sxs-lookup"><span data-stu-id="523cc-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="523cc-103">지정 된 메타 데이터 서명을 가진 권한 집합에 대 한 정의 만들고 해당 권한 집합 정의에 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="523cc-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="523cc-104">구문</span><span class="sxs-lookup"><span data-stu-id="523cc-104">Syntax</span></span>  
  
```  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,   
    [in]  DWORD          dwAction,   
    [in]  void const     *pvPermission,   
    [in]  ULONG          cbPermission,   
    [out] mdPermission   *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="523cc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="523cc-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="523cc-106">[in] 데코 레이트 되어야 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="523cc-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="523cc-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) 사용할 선언적 보안의 형식을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="523cc-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="523cc-108">[in] BLOB 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="523cc-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="523cc-109">[in] 크기 (바이트)의 `pvPermission`합니다.</span><span class="sxs-lookup"><span data-stu-id="523cc-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="523cc-110">[out] 반환 된 권한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="523cc-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="523cc-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="523cc-111">Requirements</span></span>  
 <span data-ttu-id="523cc-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="523cc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="523cc-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="523cc-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="523cc-114">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="523cc-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="523cc-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="523cc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="523cc-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="523cc-116">See also</span></span>
- [<span data-ttu-id="523cc-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="523cc-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="523cc-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="523cc-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
