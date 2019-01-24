---
title: IMetaDataTables::GetString 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c457d8a6b3ab187b7d02c9c9be800c4ef1f0f58c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537987"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="8be6f-102">IMetaDataTables::GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="8be6f-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="8be6f-103">현재 참조 범위에 있는 테이블 열에서 지정된 된 인덱스에 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8be6f-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8be6f-104">구문</span><span class="sxs-lookup"><span data-stu-id="8be6f-104">Syntax</span></span>  
  
```  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8be6f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8be6f-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="8be6f-106">[in] 다음 값에 대 한 검색을 시작 하는 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="8be6f-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="8be6f-107">[out] 반환 되는 문자열 값에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8be6f-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8be6f-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8be6f-108">Requirements</span></span>  
 <span data-ttu-id="8be6f-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8be6f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8be6f-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8be6f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8be6f-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="8be6f-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8be6f-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8be6f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8be6f-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="8be6f-113">See also</span></span>
- [<span data-ttu-id="8be6f-114">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8be6f-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="8be6f-115">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8be6f-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
