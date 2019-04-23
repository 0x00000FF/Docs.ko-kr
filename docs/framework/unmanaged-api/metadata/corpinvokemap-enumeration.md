---
title: CorPinvokeMap 열거형
ms.date: 03/30/2017
api_name:
- CorPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPinvokeMap
helpviewer_keywords:
- CorPinvokeMap enumeration [.NET Framework metadata]
ms.assetid: f14f986e-f6ce-42bc-aa23-18150c46d28c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 951941092f67f66c5b17c8ae592569c2a8e6a675
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079632"
---
# <a name="corpinvokemap-enumeration"></a><span data-ttu-id="3913b-102">CorPinvokeMap 열거형</span><span class="sxs-lookup"><span data-stu-id="3913b-102">CorPinvokeMap Enumeration</span></span>
<span data-ttu-id="3913b-103">PInvoke 호출에 대 한 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-103">Specifies options for a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3913b-104">구문</span><span class="sxs-lookup"><span data-stu-id="3913b-104">Syntax</span></span>  
  
```  
typedef enum  CorPinvokeMap {  
  
    pmNoMangle          = 0x0001,  
  
    pmCharSetMask       = 0x0006,  
    pmCharSetNotSpec    = 0x0000,  
    pmCharSetAnsi       = 0x0002,  
    pmCharSetUnicode    = 0x0004,  
    pmCharSetAuto       = 0x0006,  
  
    pmBestFitUseAssem   = 0x0000,  
    pmBestFitEnabled    = 0x0010,  
    pmBestFitDisabled   = 0x0020,  
    pmBestFitMask       = 0x0030,  
  
    pmThrowOnUnmappableCharUseAssem   = 0x0000,  
    pmThrowOnUnmappableCharEnabled    = 0x1000,  
    pmThrowOnUnmappableCharDisabled   = 0x2000,  
    pmThrowOnUnmappableCharMask       = 0x3000,  
  
    pmSupportsLastError = 0x0040,   
  
    pmCallConvMask      = 0x0700,  
    pmCallConvWinapi    = 0x0100,  
    pmCallConvCdecl     = 0x0200,  
    pmCallConvStdcall   = 0x0300,  
    pmCallConvThiscall  = 0x0400,  
    pmCallConvFastcall  = 0x0500,  
  
    pmMaxValue          = 0xFFFF  
  
} CorPinvokeMap;  
```  
  
## <a name="members"></a><span data-ttu-id="3913b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="3913b-105">Members</span></span>  
  
|<span data-ttu-id="3913b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="3913b-106">Member</span></span>|<span data-ttu-id="3913b-107">설명</span><span class="sxs-lookup"><span data-stu-id="3913b-107">Description</span></span>|  
|------------|-----------------|  
|`pmNoMangle`|<span data-ttu-id="3913b-108">각 멤버 이름은 지정 된 대로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-108">Use each member name as specified.</span></span>|  
|`pmCharSetMask`|<span data-ttu-id="3913b-109">예약됨.</span><span class="sxs-lookup"><span data-stu-id="3913b-109">Reserved.</span></span>|  
|`pmCharSetNotSpec`|<span data-ttu-id="3913b-110">예약됨.</span><span class="sxs-lookup"><span data-stu-id="3913b-110">Reserved.</span></span>|  
|`pmCharSetAnsi`|<span data-ttu-id="3913b-111">문자열을 다중 바이트 문자열로 마샬링하십시오.</span><span class="sxs-lookup"><span data-stu-id="3913b-111">Marshal strings as multiple-byte character strings.</span></span>|  
|`pmCharSetUnicode`|<span data-ttu-id="3913b-112">문자열을 유니코드 2 바이트 문자로 마샬링하십시오.</span><span class="sxs-lookup"><span data-stu-id="3913b-112">Marshal strings as Unicode 2-byte characters.</span></span>|  
|`pmCharSetAuto`|<span data-ttu-id="3913b-113">대상 운영 체제에 맞게 문자열을 자동으로 마샬링하십시오.</span><span class="sxs-lookup"><span data-stu-id="3913b-113">Automatically marshal strings appropriately for the target operating system.</span></span> <span data-ttu-id="3913b-114">기본값은 Windows NT, Windows 2000, Windows XP 및 Windows Server 2003 제품군;의 유니코드 기본값은 Windows 98 및 me. Windows ANSI</span><span class="sxs-lookup"><span data-stu-id="3913b-114">The default is Unicode on Windows NT, Windows 2000, Windows XP, and the Windows Server 2003 family; the default is ANSI on Windows 98 and Windows Me.</span></span>|  
|`pmBestFitUseAssem`|<span data-ttu-id="3913b-115">예약됨.</span><span class="sxs-lookup"><span data-stu-id="3913b-115">Reserved.</span></span>|  
|`pmBestFitEnabled`|<span data-ttu-id="3913b-116">ANSI 문자 집합에는 정확한 일치 항목이 없는 유니코드 문자의 최적된 매핑을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-116">Perform best-fit mapping of Unicode characters that lack an exact match in the ANSI character set.</span></span>|  
|`pmBestFitDisabled`|<span data-ttu-id="3913b-117">유니코드 문자의 최적된 매핑을 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-117">Do not perform best-fit mapping of Unicode characters.</span></span> <span data-ttu-id="3913b-118">매핑할 수 없는 모든 문자는 대체 하는 경우에 '?'입니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-118">In this case, all unmappable characters will be replaced by a ‘?’.</span></span>|  
|`pmBestFitMask`|<span data-ttu-id="3913b-119">예약됨.</span><span class="sxs-lookup"><span data-stu-id="3913b-119">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharUseAssem`|<span data-ttu-id="3913b-120">예약됨.</span><span class="sxs-lookup"><span data-stu-id="3913b-120">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharEnabled`|<span data-ttu-id="3913b-121">Interop 마샬러를 매핑할 수 없는 문자를 발견 한 경우 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-121">Throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharDisabled`|<span data-ttu-id="3913b-122">Interop 마샬러를 매핑할 수 없는 문자를 발견 한 경우에 예외를 throw 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-122">Do not throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharMask`|<span data-ttu-id="3913b-123">예약됨</span><span class="sxs-lookup"><span data-stu-id="3913b-123">Reserved</span></span>|  
|`pmSupportsLastError`|<span data-ttu-id="3913b-124">호출 수신자는 Win32 호출을 허용 `SetLastError` 특성 사용 메서드에서 반환 하기 전에 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-124">Allow the callee to call the Win32 `SetLastError` function before returning from the attributed method.</span></span>|  
|`pmCallConvMask`|<span data-ttu-id="3913b-125">예약됨</span><span class="sxs-lookup"><span data-stu-id="3913b-125">Reserved</span></span>|  
|`pmCallConvWinapi`|<span data-ttu-id="3913b-126">기본 플랫폼 호출 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-126">Use the default platform calling convention.</span></span> <span data-ttu-id="3913b-127">예를 들어 Windows에서 기본값인 `StdCall` 한 것이 Windows CE.NET `Cdecl`합니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-127">For example, on Windows the default is `StdCall` and on Windows CE .NET it is `Cdecl`.</span></span>|  
|`pmCallConvCdecl`|<span data-ttu-id="3913b-128">사용 된 `Cdecl` 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-128">Use the `Cdecl` calling convention.</span></span> <span data-ttu-id="3913b-129">이 경우 호출자가 스택을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-129">In this case, the caller cleans the stack.</span></span> <span data-ttu-id="3913b-130">이렇게 하면 사용 하 여 함수를 호출할 수 있습니다. `varargs` (즉, 가변 개수의 매개 변수를 허용 하는 함수).</span><span class="sxs-lookup"><span data-stu-id="3913b-130">This enables calling functions with `varargs` (that is, functions that accept a variable number of parameters).</span></span>|  
|`pmCallConvStdcall`|<span data-ttu-id="3913b-131">사용 된 `StdCall` 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-131">Use the `StdCall` calling convention.</span></span> <span data-ttu-id="3913b-132">이 경우 호출 수신자가 스택을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-132">In this case, the callee cleans the stack.</span></span> <span data-ttu-id="3913b-133">이 플랫폼을 사용 하 여 관리 되지 않는 함수를 호출할 호출에 대 한 기본 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-133">This is the default convention for calling unmanaged functions with platform invoke.</span></span>|  
|`pmCallConvThiscall`|<span data-ttu-id="3913b-134">사용 된 `ThisCall` 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-134">Use the `ThisCall` calling convention.</span></span> <span data-ttu-id="3913b-135">첫 번째 매개 변수는이 경우에 `this` 포인터 레지스터 ECX에에서 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-135">In this case, the first parameter is the `this` pointer and is stored in register ECX.</span></span> <span data-ttu-id="3913b-136">다른 매개 변수는 스택에 푸시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-136">Other parameters are pushed on the stack.</span></span> <span data-ttu-id="3913b-137">`ThisCall` 관리 되지 않는 DLL에서 내보낸 클래스의 메서드를 호출할 호출 규칙이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3913b-137">The `ThisCall` calling convention is used to call methods on classes exported from an unmanaged DLL.</span></span>|  
|`pmCallConvFastcall`|<span data-ttu-id="3913b-138">예약됨.</span><span class="sxs-lookup"><span data-stu-id="3913b-138">Reserved.</span></span>|  
|`pmMaxValue`|<span data-ttu-id="3913b-139">예약됨.</span><span class="sxs-lookup"><span data-stu-id="3913b-139">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3913b-140">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3913b-140">Requirements</span></span>  
 <span data-ttu-id="3913b-141">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3913b-141">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3913b-142">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="3913b-142">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3913b-143">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3913b-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3913b-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="3913b-144">See also</span></span>

- [<span data-ttu-id="3913b-145">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="3913b-145">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
