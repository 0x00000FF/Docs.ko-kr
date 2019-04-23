---
title: IMetaDataImport::GetMethodProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c61931f5f6a4bbbf66446d68b0d1b2d1df958a66
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137925"
---
# <a name="imetadataimportgetmethodprops-method"></a><span data-ttu-id="5d242-102">IMetaDataImport::GetMethodProps 메서드</span><span class="sxs-lookup"><span data-stu-id="5d242-102">IMetaDataImport::GetMethodProps Method</span></span>
<span data-ttu-id="5d242-103">지정한 MethodDef 토큰이 참조하는 메서드와 연결된 메타데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5d242-103">Gets the metadata associated with the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d242-104">구문</span><span class="sxs-lookup"><span data-stu-id="5d242-104">Syntax</span></span>  
  
```  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d242-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5d242-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="5d242-106">[in] 에 대 한 메타 데이터를 반환할 메서드를 나타내는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5d242-106">[in] The MethodDef token that represents the method to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="5d242-107">[out] 메서드를 구현 하는 형식을 나타내는 TypeDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5d242-107">[out] A Pointer to a TypeDef token that represents the type that implements the method.</span></span>  
  
 `szMethod`  
 <span data-ttu-id="5d242-108">[out] 메서드의 이름을 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5d242-108">[out] A Pointer to a buffer that has the method's name.</span></span>  
  
 `cchMethod`  
 <span data-ttu-id="5d242-109">[in] 요청된 된 크기의 `szMethod`합니다.</span><span class="sxs-lookup"><span data-stu-id="5d242-109">[in] The requested size of `szMethod`.</span></span>  
  
 `pchMethod`  
 <span data-ttu-id="5d242-110">[out] 와이드 문자에서 크기에 대 한 포인터 `szMethod`, 또는 메서드 이름에 와이드 문자 수가 실제 잘리는 경우.</span><span class="sxs-lookup"><span data-stu-id="5d242-110">[out] A Pointer to the size in wide characters of `szMethod`, or in the case of truncation, the actual number of wide characters in the method name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="5d242-111">[out] 메서드를 사용 하 여 연결 된 모든 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5d242-111">[out] A pointer to any flags associated with the method.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="5d242-112">[out] 메서드 서명의 이진 메타 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5d242-112">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="5d242-113">[out] 바이트의 크기에 대 한 포인터 `ppvSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="5d242-113">[out] A Pointer to the size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="5d242-114">[out] 메서드의 상대 가상 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5d242-114">[out] A pointer to the relative virtual address of the method.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="5d242-115">[out] 메서드에 대 한 구현 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5d242-115">[out] A pointer to any implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d242-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d242-116">Requirements</span></span>  
 <span data-ttu-id="5d242-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5d242-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d242-118">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5d242-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5d242-119">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5d242-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5d242-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d242-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d242-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="5d242-121">See also</span></span>

- [<span data-ttu-id="5d242-122">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d242-122">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5d242-123">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d242-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
