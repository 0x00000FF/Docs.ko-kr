---
title: ICorDebugProcess5::GetTypeFields 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
ms.openlocfilehash: 644b5ed751caaf1809250244b37badc8037b0f57
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792350"
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="2ed44-102">ICorDebugProcess5::GetTypeFields 메서드</span><span class="sxs-lookup"><span data-stu-id="2ed44-102">ICorDebugProcess5::GetTypeFields Method</span></span>
<span data-ttu-id="2ed44-103">형식에 속하는 필드에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ed44-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ed44-104">구문</span><span class="sxs-lookup"><span data-stu-id="2ed44-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ed44-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2ed44-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="2ed44-106">진행 필드 정보를 검색할 형식의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed44-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="2ed44-107">진행 필드 정보를 검색할 [COR_FIELD](cor-field-structure.md) 개체의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed44-107">[in] The number of [COR_FIELD](cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="2ed44-108">제한이 형식에 속하는 필드에 대 한 정보를 제공 하는 [COR_FIELD](cor-field-structure.md) 개체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed44-108">[out] An array of [COR_FIELD](cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="2ed44-109">제한이 `fields`에 포함 된 [COR_FIELD](cor-field-structure.md) 개체 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed44-109">[out] A pointer to the number of [COR_FIELD](cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ed44-110">주의</span><span class="sxs-lookup"><span data-stu-id="2ed44-110">Remarks</span></span>  
 <span data-ttu-id="2ed44-111">메서드가 `fields`를 채우는 데 사용 하는 필드 정보가 있는 필드의 수를 지정 하는 `celt` 매개 변수는 `COR_TYPE_LAYOUT::numFields` 필드의 값에 해당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ed44-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ed44-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2ed44-112">Requirements</span></span>  
 <span data-ttu-id="2ed44-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ed44-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ed44-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ed44-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ed44-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ed44-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ed44-116">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ed44-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ed44-117">참조</span><span class="sxs-lookup"><span data-stu-id="2ed44-117">See also</span></span>

- [<span data-ttu-id="2ed44-118">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ed44-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="2ed44-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ed44-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
