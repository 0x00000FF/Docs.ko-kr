---
title: CorDebugRecordFormat 열거형
ms.date: 03/30/2017
api_name:
- CorDebugRecordFormat
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45278b116ce1ea1a910d806df408c8692338d9a9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634378"
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="b94f8-102">CorDebugRecordFormat 열거형</span><span class="sxs-lookup"><span data-stu-id="b94f8-102">CorDebugRecordFormat Enumeration</span></span>
<span data-ttu-id="b94f8-103">네이티브 예외 디버그 이벤트에 대한 정보가 포함된 바이트 배열의 데이터 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b94f8-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b94f8-104">구문</span><span class="sxs-lookup"><span data-stu-id="b94f8-104">Syntax</span></span>  
  
```  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="b94f8-105">멤버</span><span class="sxs-lookup"><span data-stu-id="b94f8-105">Members</span></span>  
  
|<span data-ttu-id="b94f8-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b94f8-106">Member</span></span>|<span data-ttu-id="b94f8-107">설명</span><span class="sxs-lookup"><span data-stu-id="b94f8-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="b94f8-108">데이터가 32비트 Windows 예외 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b94f8-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="b94f8-109">데이터가 64비트 Windows 예외 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b94f8-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b94f8-110">설명</span><span class="sxs-lookup"><span data-stu-id="b94f8-110">Remarks</span></span>  
 <span data-ttu-id="b94f8-111">멤버는 `CorDebugRecordFormat` 열거형에 전달 되는 [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) 메서드를 나타내는 바이트 배열 형식의 해당 `pRecord` 인수.</span><span class="sxs-lookup"><span data-stu-id="b94f8-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b94f8-112">이 열거형은 .NET 네이티브 디버깅 시나리오에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b94f8-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b94f8-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b94f8-113">Requirements</span></span>  
 <span data-ttu-id="b94f8-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b94f8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b94f8-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b94f8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b94f8-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b94f8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b94f8-117">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b94f8-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b94f8-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="b94f8-118">See also</span></span>
- [<span data-ttu-id="b94f8-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="b94f8-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
