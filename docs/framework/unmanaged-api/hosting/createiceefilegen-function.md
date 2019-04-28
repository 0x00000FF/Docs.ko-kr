---
title: CreateICeeFileGen 함수
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 566f73335861a8eb769b21a254e0e93b51a78d02
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756392"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="b2459-102">CreateICeeFileGen 함수</span><span class="sxs-lookup"><span data-stu-id="b2459-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="b2459-103">만듭니다는 [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b2459-103">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="b2459-104">이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="b2459-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2459-105">구문</span><span class="sxs-lookup"><span data-stu-id="b2459-105">Syntax</span></span>  
  
```  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2459-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b2459-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="b2459-107">[out] 새 주소에 대 한 포인터 `ICeeFileGen` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b2459-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2459-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="b2459-108">Return Value</span></span>  
 <span data-ttu-id="b2459-109">이 메서드는 표준 COM 오류 코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b2459-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2459-110">설명</span><span class="sxs-lookup"><span data-stu-id="b2459-110">Remarks</span></span>  
 <span data-ttu-id="b2459-111">`ICeeFileGen` 개체가 공용 언어 런타임 (CLR) pe (이식 가능) 파일을 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2459-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="b2459-112">호출 된 [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) 제거할 함수는 `ICeeFileGen` 완료 되 면 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b2459-112">Call the [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2459-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2459-113">Requirements</span></span>  
 <span data-ttu-id="b2459-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b2459-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2459-115">**헤더:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="b2459-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="b2459-116">**라이브러리:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="b2459-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="b2459-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2459-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2459-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="b2459-118">See also</span></span>

- [<span data-ttu-id="b2459-119">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="b2459-119">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
