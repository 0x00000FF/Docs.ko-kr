---
title: IMetaDataImport::GetFieldMarshal 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldMarshal
helpviewer_keywords:
- GetFieldMarshal method [.NET Framework metadata]
- IMetaDataImport::GetFieldMarshal method [.NET Framework metadata]
ms.assetid: 4e2d88c6-8a3a-4fbe-900b-b4f4c06bf6bf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 837b2142e200e224fe32c2c673be0f317633452a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445360"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="a8576-102">IMetaDataImport::GetFieldMarshal 메서드</span><span class="sxs-lookup"><span data-stu-id="a8576-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="a8576-103">지정 된 필드 메타 데이터 토큰이 나타내는 필드의 관리 되지 않는 네이티브 형식에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a8576-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8576-104">구문</span><span class="sxs-lookup"><span data-stu-id="a8576-104">Syntax</span></span>  
  
```  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,   
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8576-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a8576-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="a8576-106">[in] Interop 마샬링 정보를 가져올 필드를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a8576-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="a8576-107">[out] 메타 데이터 서명의 필드의 네이티브 형식에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a8576-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="a8576-108">[out] 바이트 크기 `ppvNativeType`합니다.</span><span class="sxs-lookup"><span data-stu-id="a8576-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8576-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a8576-109">Requirements</span></span>  
 <span data-ttu-id="a8576-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8576-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8576-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a8576-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8576-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a8576-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a8576-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8576-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8576-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8576-114">See Also</span></span>  
 [<span data-ttu-id="a8576-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a8576-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a8576-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a8576-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
