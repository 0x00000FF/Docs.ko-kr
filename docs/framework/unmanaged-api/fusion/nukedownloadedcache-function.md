---
title: NukeDownloadedCache 함수
ms.date: 03/30/2017
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80891da7d61aa5114d5cc4d8aff4c7ce82020237
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720095"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="ff810-102">NukeDownloadedCache 함수</span><span class="sxs-lookup"><span data-stu-id="ff810-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="ff810-103">공용 언어 런타임 (CLR) 다운로드 캐시를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="ff810-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff810-104">구문</span><span class="sxs-lookup"><span data-stu-id="ff810-104">Syntax</span></span>  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ff810-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="ff810-105">Return Value</span></span>  
 <span data-ttu-id="ff810-106">이 메서드는 Winerror에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff810-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff810-107">설명</span><span class="sxs-lookup"><span data-stu-id="ff810-107">Remarks</span></span>  
 <span data-ttu-id="ff810-108">CLR 다운로드 캐시에 다시 사용할 수 있도록 URL에서 다운로드 하는 강력한 이름의 어셈블리를 저장할 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="ff810-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff810-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff810-109">Requirements</span></span>  
 <span data-ttu-id="ff810-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ff810-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff810-111">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ff810-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ff810-112">**라이브러리:** Fusion.dll 및 Mscorwks.dll 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff810-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="ff810-113">올바른 버전의.NET Framework 대상 지정 하는 데 Mscorwks.dll 대신 Fusion.dll를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff810-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="ff810-114">**.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff810-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff810-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="ff810-115">See also</span></span>
- [<span data-ttu-id="ff810-116">CreateHistoryReader 함수</span><span class="sxs-lookup"><span data-stu-id="ff810-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [<span data-ttu-id="ff810-117">GetHistoryFileDirectory 함수</span><span class="sxs-lookup"><span data-stu-id="ff810-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)
- [<span data-ttu-id="ff810-118">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="ff810-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
