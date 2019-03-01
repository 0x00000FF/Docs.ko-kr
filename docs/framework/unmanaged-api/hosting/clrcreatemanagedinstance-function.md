---
title: ClrCreateManagedInstance 함수
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5103490da7f3056cf95f7986b46837e059f8212f
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57211834"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="96559-102">ClrCreateManagedInstance 함수</span><span class="sxs-lookup"><span data-stu-id="96559-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="96559-103">지정 된 관리 되는 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96559-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="96559-104">이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="96559-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="96559-105">관리 되는 형식의 인스턴스를 만드는 COM 정품 인증을 사용 하거나 호스팅을 사용 (참조 [인터페이스는.NET Framework 4 및 4.5에 추가 호스트 된 CLR](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span><span class="sxs-lookup"><span data-stu-id="96559-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96559-106">구문</span><span class="sxs-lookup"><span data-stu-id="96559-106">Syntax</span></span>  
  
```  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96559-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="96559-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="96559-108">[in] 요청 된 인스턴스의 형식 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="96559-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="96559-109">[in] `IID` 요청 중인 인스턴스의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="96559-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="96559-110">[out] 호출자가 요청 된 관리 되는 형식 인스턴스에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="96559-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96559-111">설명</span><span class="sxs-lookup"><span data-stu-id="96559-111">Remarks</span></span>  
 <span data-ttu-id="96559-112">공용 언어 런타임 프로세스를 이미 로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96559-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="96559-113">예를 들어,에 대 한 호출을 사용 하 여 로드할 수는 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 하기 전에 함수를 `ClrCreateManagedInstance` 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="96559-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="96559-114">런타임이 로드 되지 않은 경우 `ClrCreateManagedInstance` 먼저 런타임의 v1.0.3705를 로드 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="96559-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="96559-115">실패 하는 경우 런타임의 최신 버전을 로드 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="96559-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96559-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="96559-116">Requirements</span></span>  
 <span data-ttu-id="96559-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="96559-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96559-118">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="96559-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="96559-119">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="96559-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96559-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96559-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96559-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="96559-121">See also</span></span>
- [<span data-ttu-id="96559-122">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="96559-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="96559-123">호스팅</span><span class="sxs-lookup"><span data-stu-id="96559-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
