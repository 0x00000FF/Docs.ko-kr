---
title: IMetaDataEmit2::SaveDelta 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDelta
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDelta
helpviewer_keywords:
- IMetaDataEmit2::SaveDelta method [.NET Framework metadata]
- SaveDelta method [.NET Framework metadata]
ms.assetid: b95739fe-d2fa-4776-ae0d-31d9707ef799
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 27d9b891475d0fb45c9ec34f3363b0d76fe394c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493206"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="aa580-102">IMetaDataEmit2::SaveDelta 메서드</span><span class="sxs-lookup"><span data-stu-id="aa580-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="aa580-103">편집 하며 계속 하기는 현재 세션에서 지정된 된 파일 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa580-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa580-104">구문</span><span class="sxs-lookup"><span data-stu-id="aa580-104">Syntax</span></span>  
  
```  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa580-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aa580-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="aa580-106">[in] 변경 내용을 저장 하는 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="aa580-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="aa580-107">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa580-107">[in] Reserved.</span></span> <span data-ttu-id="aa580-108">0이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa580-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa580-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa580-109">Requirements</span></span>  
 <span data-ttu-id="aa580-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="aa580-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa580-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aa580-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aa580-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="aa580-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aa580-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa580-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa580-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="aa580-114">See also</span></span>
- [<span data-ttu-id="aa580-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa580-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="aa580-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa580-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
