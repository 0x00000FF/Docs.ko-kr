---
title: IXCLRDataProcess 인터페이스
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ff74a7acb5cc84c177f083c19402cd78977aeab5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680376"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="73344-102">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73344-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="73344-103">프로세스에 대 한 정보를 쿼리 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="73344-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="73344-104">메서드</span><span class="sxs-lookup"><span data-stu-id="73344-104">Methods</span></span>

| <span data-ttu-id="73344-105">메서드</span><span class="sxs-lookup"><span data-stu-id="73344-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="73344-106">설명</span><span class="sxs-lookup"><span data-stu-id="73344-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="73344-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="73344-107">GetAppDomainByUniqueId</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="73344-108">가져옵니다는 `AppDomain` 자체 고유 id로 프로세스에서입니다.</span><span class="sxs-lookup"><span data-stu-id="73344-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="73344-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="73344-109">StartEnumModules</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="73344-110">프로세스의 모듈을 열거에 대 한 핸들을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="73344-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="73344-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="73344-111">EnumModule</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="73344-112">이 프로세스의 모듈을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="73344-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="73344-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="73344-113">EndEnumModules</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="73344-114">모듈 열거 하는 동안 사용 되는 내부 반복기 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="73344-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="73344-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="73344-115">StartEnumMethodInstancesByAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="73344-116">메서드 인스턴스를 열거 핸들을 제공 `AppDomain` 지정된 된 주소에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="73344-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="73344-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="73344-117">EnumMethodInstanceByAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="73344-118">메서드 인스턴스의 주소 오프셋에서 시작 하는이 프로세스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="73344-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="73344-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="73344-119">EndEnumMethodInstancesByAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="73344-120">인스턴스 열거 하는 동안 사용 되는 내부 반복기 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="73344-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="73344-121">설명</span><span class="sxs-lookup"><span data-stu-id="73344-121">Remarks</span></span>

<span data-ttu-id="73344-122">이 인터페이스는 런타임 내에서 있으며 모든 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73344-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="73344-123">그러나 COM 인터페이스에서 파생 되는 것 `IUnknown` GUID를 사용 하 여 `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` 일반적인 COM 메커니즘을 통해 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73344-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="73344-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="73344-124">Requirements</span></span>

<span data-ttu-id="73344-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="73344-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="73344-126">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="73344-126">**Header:** None</span></span>  
<span data-ttu-id="73344-127">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="73344-127">**Library:** None</span></span>  
<span data-ttu-id="73344-128">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="73344-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="73344-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="73344-129">See also</span></span>

- [<span data-ttu-id="73344-130">디버깅</span><span class="sxs-lookup"><span data-stu-id="73344-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="73344-131">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73344-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
