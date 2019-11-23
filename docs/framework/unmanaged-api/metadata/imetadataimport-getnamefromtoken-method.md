---
title: IMetaDataImport::GetNameFromToken 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNameFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type:
- apiref
ms.openlocfilehash: 6ed30f07fcec9c730e1514350c594399f0aa16e5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437268"
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="0f7e0-102">IMetaDataImport::GetNameFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="0f7e0-102">IMetaDataImport::GetNameFromToken Method</span></span>
<span data-ttu-id="0f7e0-103">지정한 메타데이터 토큰에서 참조된 개체의 UTF-8 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f7e0-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="0f7e0-104">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f7e0-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f7e0-105">구문</span><span class="sxs-lookup"><span data-stu-id="0f7e0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f7e0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f7e0-106">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="0f7e0-107">[in] The token representing the object to return the name for.</span><span class="sxs-lookup"><span data-stu-id="0f7e0-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="0f7e0-108">[out] A pointer to the UTF-8 object name in the heap.</span><span class="sxs-lookup"><span data-stu-id="0f7e0-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f7e0-109">주의</span><span class="sxs-lookup"><span data-stu-id="0f7e0-109">Remarks</span></span>  
 <span data-ttu-id="0f7e0-110">`GetNameFromToken`는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f7e0-110">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="0f7e0-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span><span class="sxs-lookup"><span data-stu-id="0f7e0-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f7e0-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f7e0-112">Requirements</span></span>  
 <span data-ttu-id="0f7e0-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f7e0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f7e0-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0f7e0-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0f7e0-115">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0f7e0-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0f7e0-116">**.NET Framework Versions:** 1.0</span><span class="sxs-lookup"><span data-stu-id="0f7e0-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f7e0-117">참조</span><span class="sxs-lookup"><span data-stu-id="0f7e0-117">See also</span></span>

- [<span data-ttu-id="0f7e0-118">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f7e0-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0f7e0-119">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f7e0-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
