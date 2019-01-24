---
title: IMetaDataTables::GetRow 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetRow
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a6f6f3018d5e9a1b49191d8e82f91ac8e5c21b77
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681952"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="ae500-102">IMetaDataTables::GetRow 메서드</span><span class="sxs-lookup"><span data-stu-id="ae500-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="ae500-103">지정된 된 테이블 인덱스에 있는 표에 지정 된 행 인덱스에 행을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae500-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae500-104">구문</span><span class="sxs-lookup"><span data-stu-id="ae500-104">Syntax</span></span>  
  
```  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae500-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae500-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="ae500-106">[in] 행을 검색할 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="ae500-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="ae500-107">[in] 가져올 행의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="ae500-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="ae500-108">[out] 행에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ae500-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae500-109">설명</span><span class="sxs-lookup"><span data-stu-id="ae500-109">Remarks</span></span>  
 <span data-ttu-id="ae500-110">바람직하지 않습니다이 메서드를 사용 하 여 일관 된 결과 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae500-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="ae500-111">GUID 테이블에 대 한 자세한 내용은 공용 언어 인프라 (CLI), 특히 "파티션 II: 메타 데이터 정 및 의미 체계 "입니다.</span><span class="sxs-lookup"><span data-stu-id="ae500-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="ae500-112">이 설명서는 온라인으로 제공됩니다. MSDN의 [ECMA C# 및 공용 언어 인프라 표준](https://go.microsoft.com/fwlink/?LinkID=99212) 및 Ecma International 웹 사이트의 [표준 ECMA-335 - CLI(공용 언어 인프라)](https://go.microsoft.com/fwlink/?LinkID=65552)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae500-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae500-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae500-113">Requirements</span></span>  
 <span data-ttu-id="ae500-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ae500-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae500-115">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ae500-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ae500-116">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="ae500-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ae500-117">**.NET framework 버전**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae500-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae500-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="ae500-118">See also</span></span>
- [<span data-ttu-id="ae500-119">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae500-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="ae500-120">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae500-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
