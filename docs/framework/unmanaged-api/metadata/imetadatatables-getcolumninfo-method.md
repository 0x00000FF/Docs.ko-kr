---
title: IMetaDataTables::GetColumnInfo 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetColumnInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bcab5adf30648f6b5a614a407478977bc37c7062
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480704"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="a432b-102">IMetaDataTables::GetColumnInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="a432b-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="a432b-103">지정된 된 테이블의 지정한 열에 대 한 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a432b-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a432b-104">구문</span><span class="sxs-lookup"><span data-stu-id="a432b-104">Syntax</span></span>  
  
```  
HRESULT GetColumnInfo (   
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a432b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a432b-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="a432b-106">[in] 원하는 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="a432b-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="a432b-107">[in] 원하는 열의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="a432b-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="a432b-108">[out] 행의 열 오프셋에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a432b-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="a432b-109">[out] 열의 바이트 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a432b-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="a432b-110">[out] 열에서 값의 형식에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a432b-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="a432b-111">[out] 열 이름에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a432b-111">[out] A pointer to a pointer to the column name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a432b-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a432b-112">Requirements</span></span>  
 <span data-ttu-id="a432b-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a432b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a432b-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a432b-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a432b-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="a432b-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a432b-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a432b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a432b-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="a432b-117">See also</span></span>
- [<span data-ttu-id="a432b-118">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a432b-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="a432b-119">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a432b-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
