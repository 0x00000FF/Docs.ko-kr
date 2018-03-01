---
title: "IBindingDisplay::GetCurrentDisplay 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cce7638bfe6ffe0d4b5f7f9a64aaff0c59c860cb
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="ed486-102">IBindingDisplay::GetCurrentDisplay 메서드</span><span class="sxs-lookup"><span data-stu-id="ed486-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="ed486-103">현재 바인딩 표시 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ed486-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed486-104">구문</span><span class="sxs-lookup"><span data-stu-id="ed486-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed486-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ed486-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="ed486-106">[out, retval] 바인딩 표시 정보를 포함 하는 safearray에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ed486-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed486-107">설명</span><span class="sxs-lookup"><span data-stu-id="ed486-107">Remarks</span></span>  
 <span data-ttu-id="ed486-108">[ibindingdisplay:: Initializeforprocess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) 메서드 이전에 성공 했습니다 해야 프로그램은 디버거에서 중지 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed486-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="ed486-109">호출자는 반환 된 할당을 취소 해야 `SAFEARRAY` 메모리를 사용 하 여 [SafeArrayDestroy](http://msdn.microsoft.com/library/fc94f7e7-b903-4c78-905c-54df1f8d13fa)합니다.</span><span class="sxs-lookup"><span data-stu-id="ed486-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](http://msdn.microsoft.com/library/fc94f7e7-b903-4c78-905c-54df1f8d13fa).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed486-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed486-110">Requirements</span></span>  
 <span data-ttu-id="ed486-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ed486-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed486-112">**헤더:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="ed486-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="ed486-113">**라이브러리:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="ed486-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="ed486-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed486-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed486-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed486-115">See Also</span></span>  
 [<span data-ttu-id="ed486-116">IBindingDisplay 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed486-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 [<span data-ttu-id="ed486-117">InitializeForProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="ed486-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
