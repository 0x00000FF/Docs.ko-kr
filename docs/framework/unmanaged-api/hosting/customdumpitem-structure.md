---
title: CustomDumpItem 구조체
ms.date: 03/30/2017
api_name:
- CustomDumpItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CustomDumpItem
helpviewer_keywords:
- CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9000f35e9a8f7ecc6c40cf0ef9c220fc9f4f9c10
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985688"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="da3ae-102">CustomDumpItem 구조체</span><span class="sxs-lookup"><span data-stu-id="da3ae-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="da3ae-103">오류 보고에 사용자 지정 덤프에 추가할 항목을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="da3ae-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da3ae-104">구문</span><span class="sxs-lookup"><span data-stu-id="da3ae-104">Syntax</span></span>  
  
```  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="da3ae-105">멤버</span><span class="sxs-lookup"><span data-stu-id="da3ae-105">Members</span></span>  
  
|<span data-ttu-id="da3ae-106">멤버</span><span class="sxs-lookup"><span data-stu-id="da3ae-106">Member</span></span>|<span data-ttu-id="da3ae-107">설명</span><span class="sxs-lookup"><span data-stu-id="da3ae-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="da3ae-108">[ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) 추가할 항목의 종류를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="da3ae-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="da3ae-109">현재 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da3ae-109">Not currently used.</span></span> <span data-ttu-id="da3ae-110">공용 구조체에 추가 된 모든 항목 포인터 크기 보다 더 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da3ae-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="da3ae-111">경우는 `struct` 는 필요한 별도로 할당 하며 가리키도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="da3ae-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da3ae-112">설명</span><span class="sxs-lookup"><span data-stu-id="da3ae-112">Remarks</span></span>  
 <span data-ttu-id="da3ae-113">[Iclrerrorreportingmanager:: Begincustomdump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) 형식의 매개 변수 `CustomDumpItem`합니다.</span><span class="sxs-lookup"><span data-stu-id="da3ae-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da3ae-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="da3ae-114">Requirements</span></span>  
 <span data-ttu-id="da3ae-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="da3ae-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da3ae-116">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="da3ae-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="da3ae-117">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="da3ae-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da3ae-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da3ae-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da3ae-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="da3ae-119">See also</span></span>

- [<span data-ttu-id="da3ae-120">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="da3ae-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
