---
title: IMetaDataTables::GetNextUserString 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextUserString
helpviewer_keywords:
- GetNextUserString method [.NET Framework metadata]
- IMetaDataTables::GetNextUserString method [.NET Framework metadata]
ms.assetid: b7cb40ee-67b7-4f4e-8dcc-ee7ac8bc986b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b9e729732175b7249e4d3be91996bc5e4050855
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450208"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="fa0ec-102">IMetaDataTables::GetNextUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="fa0ec-102">IMetaDataTables::GetNextUserString Method</span></span>
<span data-ttu-id="fa0ec-103">현재 테이블 열에 있는 다음 하드 코드 된 문자열이 포함 된 행의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fa0ec-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa0ec-104">구문</span><span class="sxs-lookup"><span data-stu-id="fa0ec-104">Syntax</span></span>  
  
```  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa0ec-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fa0ec-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="fa0ec-106">[in] 현재 문자열 열에서 사용 되는 인덱스 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fa0ec-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="fa0ec-107">[out] 열에 다음 문자열의 행 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fa0ec-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa0ec-108">설명</span><span class="sxs-lookup"><span data-stu-id="fa0ec-108">Remarks</span></span>  
 <span data-ttu-id="fa0ec-109">권장 하지는 않습니다이 메서드를 사용 하 여 일관 된 결과 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa0ec-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="fa0ec-110">GUID 테이블에 대 한 내용은 "II: 메타 데이터 정의 및 의미" 인프라 CLI (공용 언어) 설명서를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0ec-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="fa0ec-111">이 설명서는 온라인으로 제공됩니다. MSDN의 [ECMA C# 및 공용 언어 인프라 표준](http://go.microsoft.com/fwlink/?LinkID=99212) 및 Ecma International 웹 사이트의 [표준 ECMA-335 - CLI(공용 언어 인프라)](http://go.microsoft.com/fwlink/?LinkID=65552)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa0ec-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa0ec-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fa0ec-112">Requirements</span></span>  
 <span data-ttu-id="fa0ec-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0ec-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa0ec-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fa0ec-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa0ec-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="fa0ec-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fa0ec-116">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa0ec-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa0ec-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa0ec-117">See Also</span></span>  
 [<span data-ttu-id="fa0ec-118">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa0ec-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="fa0ec-119">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa0ec-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
