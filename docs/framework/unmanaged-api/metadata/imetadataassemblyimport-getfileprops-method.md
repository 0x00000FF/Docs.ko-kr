---
title: "IMetaDataAssemblyImport::GetFileProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetFileProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 55984c4adaf291e3b962514cdc3bea964d1c91bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="ec882-102">IMetaDataAssemblyImport::GetFileProps 메서드</span><span class="sxs-lookup"><span data-stu-id="ec882-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="ec882-103">지정한 메타 데이터 서명 사용 하 여 파일의 속성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ec882-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec882-104">구문</span><span class="sxs-lookup"><span data-stu-id="ec882-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="ec882-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ec882-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="ec882-106">[in] `mdFile` 파일을 가져올 속성을 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ec882-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="ec882-107">[out] 파일의 단순한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec882-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ec882-108">[in] 와이드 문자에서 크기의 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec882-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="ec882-109">[out] 와이드 문자에 실제로 반환 된 수가 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec882-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="ec882-110">[out] 해시 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ec882-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="ec882-111">파일의 sha-1 알고리즘을 사용 하는 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="ec882-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="ec882-112">[out] 반환 된 해시 값의 와이드 문자 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec882-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="ec882-113">[out] 파일에 적용 하는 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ec882-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="ec882-114">플래그 값은 하나 이상의 조합 [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ec882-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec882-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ec882-115">Requirements</span></span>  
 <span data-ttu-id="ec882-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec882-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec882-117">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ec882-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ec882-118">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="ec882-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ec882-119">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec882-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec882-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec882-120">See Also</span></span>  
 [<span data-ttu-id="ec882-121">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ec882-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
