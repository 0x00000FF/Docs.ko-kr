---
title: "IMetaDataImport::GetFieldProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetFieldProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d5874169e0f8c452b177309702444ea84858557e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetfieldprops-method"></a><span data-ttu-id="ee5fc-102">IMetaDataImport::GetFieldProps 메서드</span><span class="sxs-lookup"><span data-stu-id="ee5fc-102">IMetaDataImport::GetFieldProps Method</span></span>
<span data-ttu-id="ee5fc-103">지정한 FieldDef 토큰이 참조하는 필드와 연결된 메타데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ee5fc-103">Gets metadata associated with the field referenced by the specified FieldDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee5fc-104">구문</span><span class="sxs-lookup"><span data-stu-id="ee5fc-104">Syntax</span></span>  
  
```  
HRESULT GetFieldProps (  
   [in]  mdFieldDef        mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szField,  
   [in]  ULONG             cchField,   
   [out] ULONG             *pchField,  
   [out] DWORD             *pdwAttr,  
   [in]  PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee5fc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ee5fc-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="ee5fc-106">[in] 에 대 한 연결 된 메타 데이터를 가져올 필드를 나타내는 FieldDef 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5fc-106">[in] A FieldDef token that represents the field to get associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="ee5fc-107">[out] 클래스에 속하는 필드의 형식을 나타내는 TypeDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ee5fc-107">[out] A pointer to a TypeDef token that represents the type of the class that the field belongs to.</span></span>  
  
 `szField`  
 <span data-ttu-id="ee5fc-108">[out] 필드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ee5fc-108">[out] The name of the field.</span></span>  
  
 `cchField`  
 <span data-ttu-id="ee5fc-109">[in] 에 대 한 버퍼의 와이드 문자에서 크기 *szField*합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5fc-109">[in] The size in wide characters of the buffer for *szField*.</span></span>  
  
 `pchField`  
 <span data-ttu-id="ee5fc-110">[out] 반환된 된 버퍼의 실제 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ee5fc-110">[out] The actual size of the returned buffer.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="ee5fc-111">[out] 필드의 메타 데이터와 관련 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="ee5fc-111">[out] Flags associated with the field's metadata.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="ee5fc-112">[in] 필드를 설명 하는 이진 메타 데이터 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ee5fc-112">[in] A pointer to the binary metadata value that describes the field.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="ee5fc-113">[out] 바이트 크기 `ppvSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5fc-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="ee5fc-114">[out] 필드의 값 형식을 지정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="ee5fc-114">[out] A flag that specifies the value type of the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="ee5fc-115">[out] 필드는 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ee5fc-115">[out] A constant value for the field.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="ee5fc-116">[out] 크기의 문자에서 `ppValue`, 문자열이 없는 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="ee5fc-116">[out] The size in chars of `ppValue`, or zero if no string exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee5fc-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ee5fc-117">Requirements</span></span>  
 <span data-ttu-id="ee5fc-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5fc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee5fc-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ee5fc-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee5fc-120">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ee5fc-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ee5fc-121">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee5fc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee5fc-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee5fc-122">See Also</span></span>  
 [<span data-ttu-id="ee5fc-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ee5fc-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ee5fc-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ee5fc-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
