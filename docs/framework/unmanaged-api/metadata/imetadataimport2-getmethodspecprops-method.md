---
title: IMetaDataImport2::GetMethodSpecProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetMethodSpecProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetMethodSpecProps
helpviewer_keywords:
- GetMethodSpecProps method [.NET Framework metadata]
- IMetaDataImport2::GetMethodSpecProps method [.NET Framework metadata]
ms.assetid: 9544b711-e669-4eaf-8630-ee862e5e4489
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69af794d5405894d24f0d7545613a0e85ca3ec6a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574016"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="a8070-102">IMetaDataImport2::GetMethodSpecProps 메서드</span><span class="sxs-lookup"><span data-stu-id="a8070-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="a8070-103">지정 된 MethodSpec에서 참조 하는 메서드 메타 데이터 서명의 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a8070-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8070-104">구문</span><span class="sxs-lookup"><span data-stu-id="a8070-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,   
   [out] ULONG            *pcbSigBlob  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8070-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a8070-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="a8070-106">[in] 메서드의 인스턴스화를 나타내는 MethodSpec 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a8070-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="a8070-107">[out] 메서드 정의 나타내는 MethodDef 또는 MethodRef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a8070-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="a8070-108">[out] 메서드 서명의 이진 메타 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a8070-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="a8070-109">[out] 크기 (바이트)의 `ppvSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="a8070-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8070-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a8070-110">Requirements</span></span>  
 <span data-ttu-id="a8070-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a8070-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8070-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a8070-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8070-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="a8070-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a8070-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8070-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8070-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="a8070-115">See also</span></span>
- [<span data-ttu-id="a8070-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a8070-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="a8070-117">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a8070-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
