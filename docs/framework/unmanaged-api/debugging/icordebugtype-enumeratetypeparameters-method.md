---
title: ICorDebugType::EnumerateTypeParameters 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugType.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b48e375286e709a2ce570769c9a0453765824ec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622680"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a><span data-ttu-id="6108d-102">ICorDebugType::EnumerateTypeParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="6108d-102">ICorDebugType::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="6108d-103">포함 하는 ICorDebugTypeEnum 인터페이스 포인터를 가져옵니다는 <xref:System.Type> 이 ICorDebugType에서 참조 하는 클래스의 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="6108d-103">Gets an interface pointer to an ICorDebugTypeEnum that contains the <xref:System.Type> parameters of the class referenced by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6108d-104">구문</span><span class="sxs-lookup"><span data-stu-id="6108d-104">Syntax</span></span>  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6108d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6108d-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="6108d-106">[out] 주소에 대 한 포인터는 `ICorDebugTypeEnum` 형식의 매개 변수를 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="6108d-106">[out] A pointer to the address of an `ICorDebugTypeEnum` that contains the parameters of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6108d-107">설명</span><span class="sxs-lookup"><span data-stu-id="6108d-107">Remarks</span></span>  
 <span data-ttu-id="6108d-108">사용할 수 있습니다 `EnumerateTypeParameters` CorElementType 값을 반환한 경우 [icordebugtype:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_ PTR, 또는 typ ELEMENT_TYPE_FNPTR 합니다.</span><span class="sxs-lookup"><span data-stu-id="6108d-108">You can use `EnumerateTypeParameters` if the CorElementType value returned by [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) is ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR, or ELEMENT_TYPE_FNPTR.</span></span> <span data-ttu-id="6108d-109">매개 변수 및 해당 순서 번호 종류에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="6108d-109">The number of parameters and their order depends on the type:</span></span>  
  
- <span data-ttu-id="6108d-110">ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE: 에 포함 된 형식 매개 변수 개수는 `ICorDebugTypeEnum` 이 메서드에서 반환 되는, 해당 클래스에 대 한 형식 매개 변수 수에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="6108d-110">ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE: The number of type parameters contained in the `ICorDebugTypeEnum` that this method returns, will depend on the number of formal type parameters for the corresponding class.</span></span> <span data-ttu-id="6108d-111">예를 들어 형식이 `class Dict<String,int32>`, 다음 `EnumerateTypeParameters` 돌아갑니다는 `ICorDebugTypeEnum` 을 나타내는 개체를 포함 하는 `String` 및 `int32` 순서로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6108d-111">For example, if the type is `class Dict<String,int32>`, then `EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains objects representing `String` and `int32` in sequence.</span></span>  
  
- <span data-ttu-id="6108d-112">ELEMENT_TYPE_FNPTR: 에 포함 된 형식 매개 변수 개수는 `ICorDebugTypeEnum` 하나가 됩니다 함수에 의해 허용 되는 인수의 수를 초과 합니다.</span><span class="sxs-lookup"><span data-stu-id="6108d-112">ELEMENT_TYPE_FNPTR: The number of type parameters contained in the `ICorDebugTypeEnum` will be one greater than the number of arguments accepted by the function.</span></span> <span data-ttu-id="6108d-113">에 포함 된 첫 번째 형식 매개 변수는 `ICorDebugTypeEnum` 함수에 대 한 반환 형식 및 후속 형식 매개 변수는 함수의 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="6108d-113">The first type parameter contained in the `ICorDebugTypeEnum` is the return type for the function, and the subsequent type parameters are the function's parameters.</span></span>  
  
- <span data-ttu-id="6108d-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, 또는 ELEMENT_TYPE_PTR: 하나의 형식 매개 변수가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6108d-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR: One type parameter will be returned.</span></span> <span data-ttu-id="6108d-115">예를 들어, 형식이 배열 형식와 같은 `int32[]`,`EnumerateTypeParameters` 돌아갑니다는 `ICorDebugTypeEnum` 나타내는 개체를 포함 하는 `int32`합니다.</span><span class="sxs-lookup"><span data-stu-id="6108d-115">For example, if the type is an array type such as `int32[]`,`EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains an object representing `int32`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6108d-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6108d-116">Requirements</span></span>  
 <span data-ttu-id="6108d-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6108d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6108d-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6108d-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6108d-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6108d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6108d-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6108d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
