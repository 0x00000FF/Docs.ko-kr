---
title: ICorDebugAppDomain::GetName 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7939f7b1c0c725bb4e8c642bc38121dd755da5e2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471057"
---
# <a name="icordebugappdomaingetname-method"></a><span data-ttu-id="4b624-102">ICorDebugAppDomain::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="4b624-102">ICorDebugAppDomain::GetName Method</span></span>
<span data-ttu-id="4b624-103">응용 프로그램 도메인의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4b624-103">Gets the name of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b624-104">구문</span><span class="sxs-lookup"><span data-stu-id="4b624-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b624-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4b624-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="4b624-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="4b624-106">[in] The size of the `szName` array.</span></span> <span data-ttu-id="4b624-107">쿼리 모드에서이 메서드를 삽입할 0으로이 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b624-107">Set this value to zero to put this method in query mode.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="4b624-108">[out] 이름 또는에 실제로 반환 된 문자 수의 크기에 대 한 포인터 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="4b624-108">[out] A pointer to the size of the name or the number of characters actually returned in `szName`.</span></span> <span data-ttu-id="4b624-109">이 값을 버퍼의 크기를 알고 있어야 호출자에 게 사용 하면 쿼리 모드에서 이름에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b624-109">In query mode, this value lets the caller know how large a buffer to allocate for the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="4b624-110">[out] 응용 프로그램 도메인의 이름을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="4b624-110">[out] An array that stores the name of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b624-111">설명</span><span class="sxs-lookup"><span data-stu-id="4b624-111">Remarks</span></span>  
 <span data-ttu-id="4b624-112">디버거를 호출 합니다 `GetName` 메서드를 한 번 이름에 필요한 버퍼의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4b624-112">A debugger calls the `GetName` method once to get the size of a buffer needed for the name.</span></span> <span data-ttu-id="4b624-113">디버거는 버퍼를 할당 하 고 메서드를 호출 하는 두 번째 시간에 버퍼를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="4b624-113">The debugger allocates the buffer, and then calls the method a second time to fill the buffer.</span></span> <span data-ttu-id="4b624-114">이름, 크기를 가져오는 첫 번째 호출 이라고 *쿼리 모드*합니다.</span><span class="sxs-lookup"><span data-stu-id="4b624-114">The first call, to get the size of the name, is referred to as *query mode*.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b624-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4b624-115">Requirements</span></span>  
 <span data-ttu-id="4b624-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4b624-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b624-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b624-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b624-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b624-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b624-119">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b624-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
