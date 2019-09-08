---
title: CreateAssemblyNameObject 함수
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb53014a28fb291b8463535addfb61e62d32d7d6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795359"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="7f4cc-102">CreateAssemblyNameObject 함수</span><span class="sxs-lookup"><span data-stu-id="7f4cc-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="7f4cc-103">지정 된 이름을 사용 하 여 어셈블리의 고유 id를 나타내는 [IAssemblyName](iassemblyname-interface.md) 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7f4cc-103">Gets an interface pointer to an [IAssemblyName](iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f4cc-104">구문</span><span class="sxs-lookup"><span data-stu-id="7f4cc-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f4cc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7f4cc-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="7f4cc-106">제한이 반환 `IAssemblyName`된입니다.</span><span class="sxs-lookup"><span data-stu-id="7f4cc-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="7f4cc-107">진행 새 `IAssemblyName` 인스턴스를 만들 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7f4cc-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7f4cc-108">진행 개체 생성자에 전달할 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="7f4cc-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="7f4cc-109">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4cc-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="7f4cc-110">`pvReserved`는 null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4cc-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f4cc-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f4cc-111">Requirements</span></span>  
 <span data-ttu-id="7f4cc-112">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7f4cc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f4cc-113">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="7f4cc-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7f4cc-114">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f4cc-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7f4cc-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f4cc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f4cc-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="7f4cc-116">See also</span></span>

- [<span data-ttu-id="7f4cc-117">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7f4cc-117">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="7f4cc-118">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="7f4cc-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
