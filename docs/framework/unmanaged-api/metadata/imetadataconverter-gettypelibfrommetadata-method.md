---
title: IMetaDataConverter::GetTypeLibFromMetaData 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
ms.openlocfilehash: ef573eb9a572c27e685289b2740a55e898be2093
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177625"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="73607-102">IMetaDataConverter::GetTypeLibFromMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="73607-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="73607-103">지정된 라이브러리 및 `ITypeLib` 모듈 이름이 있는 형식 라이브러리를 나타내는 인스턴스에 대한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="73607-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73607-104">구문</span><span class="sxs-lookup"><span data-stu-id="73607-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73607-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="73607-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="73607-106">【인】 형식 라이브러리 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="73607-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="73607-107">【인】 형식 라이브러리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="73607-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="73607-108">【아웃】 형식 라이브러리를 나타내는 `ITypeLib` 인스턴스의 주소를 받는 위치에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="73607-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73607-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="73607-109">Requirements</span></span>  
 <span data-ttu-id="73607-110">**플랫폼:** [시스템 요구 사항을](../../../../docs/framework/get-started/system-requirements.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="73607-110">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73607-111">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="73607-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="73607-112">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="73607-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="73607-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73607-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73607-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73607-114">See also</span></span>

- [<span data-ttu-id="73607-115">IMetaDataConverter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73607-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
