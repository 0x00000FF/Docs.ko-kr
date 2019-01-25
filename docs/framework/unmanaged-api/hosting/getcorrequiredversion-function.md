---
title: GetCORRequiredVersion 함수
ms.date: 03/30/2017
api_name:
- GetCORRequiredVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetCORRequiredVersion
helpviewer_keywords:
- GetCORRequiredVersion function [.NET Framework hosting]
ms.assetid: 1588fe7b-c378-4f4b-9c4b-48647f1119cc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92ee0570a1a9bcc48cea744d5cc707750742d51a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534084"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="dcc7a-102">GetCORRequiredVersion 함수</span><span class="sxs-lookup"><span data-stu-id="dcc7a-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="dcc7a-103">필요한 공용 언어 런타임 (CLR) 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7a-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="dcc7a-104">이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7a-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcc7a-105">구문</span><span class="sxs-lookup"><span data-stu-id="dcc7a-105">Syntax</span></span>  
  
```  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dcc7a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dcc7a-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="dcc7a-107">[out] 버전 번호를 지정 하는 문자열을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7a-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="dcc7a-108">[in] 버퍼의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7a-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="dcc7a-109">[out] 버퍼의 바이트 수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc7a-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcc7a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dcc7a-110">Requirements</span></span>  
 <span data-ttu-id="dcc7a-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dcc7a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcc7a-112">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dcc7a-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dcc7a-113">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dcc7a-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dcc7a-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcc7a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcc7a-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="dcc7a-115">See also</span></span>
- [<span data-ttu-id="dcc7a-116">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="dcc7a-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
