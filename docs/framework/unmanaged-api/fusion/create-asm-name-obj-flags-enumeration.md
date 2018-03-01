---
title: "CREATE_ASM_NAME_OBJ_FLAGS 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CREATE_ASM_NAME_OBJ_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 61e9bea623e38b1416721773d8739bc6e6748909
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="createasmnameobjflags-enumeration"></a><span data-ttu-id="10d99-102">CREATE_ASM_NAME_OBJ_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="10d99-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="10d99-103">특성을 지정 하는 [IAssemblyName 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 하 여 생성 될 때 개체는 [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="10d99-103">Specifies the attributes of an [IAssemblyName Interface](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10d99-104">구문</span><span class="sxs-lookup"><span data-stu-id="10d99-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="10d99-105">멤버</span><span class="sxs-lookup"><span data-stu-id="10d99-105">Members</span></span>  
  
|<span data-ttu-id="10d99-106">멤버</span><span class="sxs-lookup"><span data-stu-id="10d99-106">Member</span></span>|<span data-ttu-id="10d99-107">설명</span><span class="sxs-lookup"><span data-stu-id="10d99-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="10d99-108">전달 된 매개 변수 텍스트 id 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="10d99-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="10d99-109">몇 개의 기본값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="10d99-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="10d99-110">Friend 어셈블리 규칙 (이름 및 공개 키)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="10d99-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="10d99-111">이 멤버는 내부적 으로만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="10d99-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="10d99-112">조합 된 `CANOF_PARSE_DISPLAY_NAME` 및 `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="10d99-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="10d99-113">이 멤버는 내부적 으로만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="10d99-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10d99-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="10d99-114">Requirements</span></span>  
 <span data-ttu-id="10d99-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="10d99-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10d99-116">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="10d99-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="10d99-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10d99-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10d99-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10d99-118">See Also</span></span>  
 [<span data-ttu-id="10d99-119">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10d99-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="10d99-120">CreateAssemblyNameObject 함수</span><span class="sxs-lookup"><span data-stu-id="10d99-120">CreateAssemblyNameObject Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)  
 [<span data-ttu-id="10d99-121">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="10d99-121">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
