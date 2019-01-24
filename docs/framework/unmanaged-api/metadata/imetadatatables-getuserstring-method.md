---
title: IMetaDataTables::GetUserString 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 52f3f382e022600e946a4c8f531f4eea5f3d8a34
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693745"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="45e29-102">IMetaDataTables::GetUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="45e29-102">IMetaDataTables::GetUserString Method</span></span>
<span data-ttu-id="45e29-103">현재 범위의 문자열 열에 지정된 된 인덱스에 하드 코드 된 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="45e29-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45e29-104">구문</span><span class="sxs-lookup"><span data-stu-id="45e29-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
    [in]  ULONG       ixUserString,  
    [out] ULONG       *pcbData,  
    [out] const void  **ppData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45e29-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="45e29-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="45e29-106">[in] 하드 코드 된 문자열을 검색할 인덱스 값입니다.</span><span class="sxs-lookup"><span data-stu-id="45e29-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="45e29-107">[out] P;의 크기에 대 한 포인터 `ppData`합니다.</span><span class="sxs-lookup"><span data-stu-id="45e29-107">[out] A p;ointer to the size of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="45e29-108">[out] 반환된 된 문자열에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="45e29-108">[out] A pointer to a pointer to the returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45e29-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="45e29-109">Requirements</span></span>  
 <span data-ttu-id="45e29-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="45e29-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45e29-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="45e29-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="45e29-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="45e29-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="45e29-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45e29-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45e29-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="45e29-114">See also</span></span>
- [<span data-ttu-id="45e29-115">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="45e29-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="45e29-116">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="45e29-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
