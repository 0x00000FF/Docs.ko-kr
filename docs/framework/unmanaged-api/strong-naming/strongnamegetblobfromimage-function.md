---
title: StrongNameGetBlobFromImage 함수
ms.date: 03/30/2017
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d562aef58c1e3b5bbbe690b54eb08384052c657
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456777"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="ad23d-102">StrongNameGetBlobFromImage 함수</span><span class="sxs-lookup"><span data-stu-id="ad23d-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="ad23d-103">지정 된 메모리 주소에서 어셈블리 이미지의 이진 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ad23d-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="ad23d-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad23d-104">This function has been deprecated.</span></span> <span data-ttu-id="ad23d-105">사용 하 여 [iclrstrongname:: Strongnamegetblobfromimage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad23d-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad23d-106">구문</span><span class="sxs-lookup"><span data-stu-id="ad23d-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad23d-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ad23d-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="ad23d-108">[in] 매핑된 어셈블리 매니페스트에의 메모리 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ad23d-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="ad23d-109">[in] 에 있는 이미지를 바이트 단위로 크기 `pbBase`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad23d-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="ad23d-110">[in] 이미지의 이진 표현을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="ad23d-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="ad23d-111">[out에서] 최대 크기를 바이트, 요청 된 `pbBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad23d-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="ad23d-112">반환 되 면 실제 크기를 바이트 단위로 `pbBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad23d-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad23d-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="ad23d-113">Return Value</span></span>  
 <span data-ttu-id="ad23d-114">`true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad23d-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad23d-115">설명</span><span class="sxs-lookup"><span data-stu-id="ad23d-115">Remarks</span></span>  
 <span data-ttu-id="ad23d-116">경우는 `StrongNameGetBlobFromImage` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad23d-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad23d-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ad23d-117">Requirements</span></span>  
 <span data-ttu-id="ad23d-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ad23d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad23d-119">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="ad23d-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="ad23d-120">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ad23d-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ad23d-121">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad23d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad23d-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad23d-122">See Also</span></span>  
 [<span data-ttu-id="ad23d-123">StrongNameGetBlobFromImage 메서드</span><span class="sxs-lookup"><span data-stu-id="ad23d-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [<span data-ttu-id="ad23d-124">StrongNameGetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="ad23d-124">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [<span data-ttu-id="ad23d-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ad23d-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
