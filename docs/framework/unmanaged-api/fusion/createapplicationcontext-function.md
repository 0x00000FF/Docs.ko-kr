---
title: CreateApplicationContext 함수
ms.date: 03/30/2017
api_name:
- CreateApplicationContext
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateApplicationContext
helpviewer_keywords:
- CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 709769c336d875ee5ddd00b4e1cf919c61e2c394
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746624"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="91985-102">CreateApplicationContext 함수</span><span class="sxs-lookup"><span data-stu-id="91985-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="91985-103">이 함수는.NET Framework 인프라를 지원 하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91985-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91985-104">구문</span><span class="sxs-lookup"><span data-stu-id="91985-104">Syntax</span></span>  
  
```  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="91985-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="91985-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="91985-106">[in] 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="91985-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="91985-107">[out] 응용 프로그램 컨텍스트 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="91985-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91985-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="91985-108">Requirements</span></span>  
 <span data-ttu-id="91985-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="91985-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91985-110">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="91985-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="91985-111">**라이브러리:** Fusion.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="91985-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="91985-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91985-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91985-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="91985-113">See also</span></span>
- [<span data-ttu-id="91985-114">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="91985-114">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="91985-115">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="91985-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [<span data-ttu-id="91985-116">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="91985-116">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
