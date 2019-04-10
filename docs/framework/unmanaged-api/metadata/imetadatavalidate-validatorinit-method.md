---
title: IMetaDataValidate::ValidatorInit 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataValidate.ValidatorInit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate::ValidatorInit
helpviewer_keywords:
- IMetaDataValidate::ValidatorInit method [.NET Framework metadata]
- ValidatorInit method [.NET Framework metadata]
ms.assetid: 6bafd75a-e2d0-4aea-aed1-074374d5dff6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 31ff2c62810061cd8b774e934167a5ee3acf040c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195894"
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="8ae20-102">IMetaDataValidate::ValidatorInit 메서드</span><span class="sxs-lookup"><span data-stu-id="8ae20-102">IMetaDataValidate::ValidatorInit Method</span></span>
<span data-ttu-id="8ae20-103">현재 메타데이터 범위에서 모듈 형식을 지정하는 플래그를 설정하고 유효성 검사 오류에 대한 지정된 콜백 메서드를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae20-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ae20-104">구문</span><span class="sxs-lookup"><span data-stu-id="8ae20-104">Syntax</span></span>  
  
```  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ae20-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8ae20-105">Parameters</span></span>  
 `dwModule`  
 <span data-ttu-id="8ae20-106">[in] 값을 [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) 현재 메타 데이터 범위에서 모듈의 형식을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="8ae20-106">[in] A value of the [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="8ae20-107">[in] 에 대 한 포인터를 [IUnknown](/cpp/atl/iunknown) 유효성 검사 오류에 대 한 함수 콜백으로 사용 되는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="8ae20-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ae20-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8ae20-108">Requirements</span></span>  
 <span data-ttu-id="8ae20-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8ae20-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ae20-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8ae20-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ae20-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="8ae20-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="8ae20-112">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="8ae20-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8ae20-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="8ae20-113">See also</span></span>

- [<span data-ttu-id="8ae20-114">IMetaDataValidate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ae20-114">IMetaDataValidate Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)
