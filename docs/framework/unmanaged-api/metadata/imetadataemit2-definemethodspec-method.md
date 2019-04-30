---
title: IMetaDataEmit2::DefineMethodSpec 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineMethodSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce6df232f3793b8b61d9fa7c18c9c90ca9fa3900
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043695"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="98d0e-102">IMetaDataEmit2::DefineMethodSpec 메서드</span><span class="sxs-lookup"><span data-stu-id="98d0e-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="98d0e-103">메서드의 제네릭 인스턴스를 만들고 정의 하는 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="98d0e-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98d0e-104">구문</span><span class="sxs-lookup"><span data-stu-id="98d0e-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98d0e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="98d0e-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="98d0e-106">[in] 제네릭 인스턴스를 만들려고 하는 방법에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="98d0e-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="98d0e-107">토큰 형식 이어야 합니다 `mdMethodDef` 또는 `mdMemberRef`합니다.</span><span class="sxs-lookup"><span data-stu-id="98d0e-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="98d0e-108">[in] 메서드의 이진 COM + 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="98d0e-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="98d0e-109">[in] 크기 (바이트)의 `pvSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="98d0e-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="98d0e-110">[out] 메서드의 메타 데이터 서명 정의 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="98d0e-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98d0e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98d0e-111">Requirements</span></span>  
 <span data-ttu-id="98d0e-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="98d0e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98d0e-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="98d0e-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="98d0e-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="98d0e-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="98d0e-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98d0e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98d0e-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="98d0e-116">See also</span></span>

- [<span data-ttu-id="98d0e-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98d0e-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="98d0e-118">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98d0e-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
