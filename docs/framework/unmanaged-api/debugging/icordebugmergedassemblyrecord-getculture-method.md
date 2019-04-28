---
title: ICorDebugMergedAssemblyRecord::GetCulture 메서드
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 093b21a439b96c9fe2f971300f314d1b75527f1f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796002"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="5d834-102">ICorDebugMergedAssemblyRecord::GetCulture 메서드</span><span class="sxs-lookup"><span data-stu-id="5d834-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="5d834-103">어셈블리의 문화권 이름 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5d834-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d834-104">구문</span><span class="sxs-lookup"><span data-stu-id="5d834-104">Syntax</span></span>  
  
```  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,   
   [out] ULONG32 *pcchCulture,   
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d834-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5d834-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="5d834-106">[in] `szCulture` 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5d834-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="5d834-107">[out] 실제로 `szCulture` 버퍼에 기록되는 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5d834-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="5d834-108">[out] 문화권 이름을 포함하는 문자 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5d834-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d834-109">설명</span><span class="sxs-lookup"><span data-stu-id="5d834-109">Remarks</span></span>  
 <span data-ttu-id="5d834-110">문화권 이름은 문화권을 식별하는 고유 문자열입니다(예: 영어(미국) 문화권 "en-US" 또는 중립 문화권 "neutral").</span><span class="sxs-lookup"><span data-stu-id="5d834-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d834-111">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d834-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d834-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d834-112">Requirements</span></span>  
 <span data-ttu-id="5d834-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5d834-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d834-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d834-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d834-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d834-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d834-116">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d834-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d834-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="5d834-117">See also</span></span>

- [<span data-ttu-id="5d834-118">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d834-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="5d834-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d834-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
