---
title: IMetaDataAssemblyImport::GetFileProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da38c04f5d67dc0220b1828ba0e5cdeb84346bb6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137945"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="82773-102">IMetaDataAssemblyImport::GetFileProps 메서드</span><span class="sxs-lookup"><span data-stu-id="82773-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="82773-103">지정 된 메타 데이터 서명 사용 하 여 파일의 속성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="82773-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82773-104">구문</span><span class="sxs-lookup"><span data-stu-id="82773-104">Syntax</span></span>  
  
```  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,   
    [out] LPWSTR      szName,   
    [in]  ULONG       cchName,   
    [out] ULONG       *pchName,   
    [out] const void  **ppbHashValue,   
    [out] ULONG       *pcbHashValue,   
    [out] DWORD       *pdwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82773-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="82773-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="82773-106">[in] `mdFile` 속성을 가져올 파일을 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="82773-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="82773-107">[out] 파일의 단순한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="82773-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="82773-108">[in] 와이드 문자에서 크기의 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="82773-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="82773-109">[out] 와이드 문자에 실제로 반환 된 수가 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="82773-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="82773-110">[out] 해시 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="82773-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="82773-111">파일의 sha-1 알고리즘을 사용 하는 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="82773-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="82773-112">[out] 반환 된 해시 값에 와이드 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="82773-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="82773-113">[out] 파일에 적용 하는 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="82773-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="82773-114">플래그 값은 하나 이상의 조합 [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="82773-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82773-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="82773-115">Requirements</span></span>  
 <span data-ttu-id="82773-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="82773-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82773-117">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="82773-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="82773-118">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="82773-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="82773-119">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82773-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82773-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="82773-120">See also</span></span>

- [<span data-ttu-id="82773-121">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82773-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
