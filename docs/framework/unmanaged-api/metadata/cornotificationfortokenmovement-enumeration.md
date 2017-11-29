---
title: "CorNotificationForTokenMovement 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNotificationForTokenMovement
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNotificationForTokenMovement
helpviewer_keywords: CorNotificationForTokenMovement enumeration [.NET Framework metadata]
ms.assetid: 1edd1670-976a-4fc8-bef7-7c41e60ad989
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 60d6c56394952fca84b45ba042f7d45a1dec6b1c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="cornotificationfortokenmovement-enumeration"></a><span data-ttu-id="13573-102">CorNotificationForTokenMovement 열거형</span><span class="sxs-lookup"><span data-stu-id="13573-102">CorNotificationForTokenMovement Enumeration</span></span>
<span data-ttu-id="13573-103">알림을 토큰 다시 매핑 발생할 때 메타 데이터 API 클라이언트에 보낼 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-103">Specifies the notifications that will be sent to the metadata API client when a token remap occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13573-104">구문</span><span class="sxs-lookup"><span data-stu-id="13573-104">Syntax</span></span>  
  
```  
typedef enum CorNotificationForTokenMovement {  
  
    MDNotifyDefault             = 0x0000000f,  
    MDNotifyAll                 = 0xffffffff,  
    MDNotifyNone                = 0x00000000,  
    MDNotifyMethodDef           = 0x00000001,  
    MDNotifyMemberRef           = 0x00000002,  
    MDNotifyFieldDef            = 0x00000004,  
    MDNotifyTypeRef             = 0x00000008,  
  
    MDNotifyTypeDef             = 0x00000010,  
    MDNotifyParamDef            = 0x00000020,  
    MDNotifyInterfaceImpl       = 0x00000040,  
    MDNotifyProperty            = 0x00000080,  
    MDNotifyEvent               = 0x00000100,  
    MDNotifySignature           = 0x00000200,  
    MDNotifyTypeSpec            = 0x00000400,  
    MDNotifyCustomAttribute     = 0x00000800,  
    MDNotifySecurityValue       = 0x00001000,  
    MDNotifyPermission          = 0x00002000,  
    MDNotifyModuleRef           = 0x00004000,  
  
    MDNotifyNameSpace           = 0x00008000,  
  
    MDNotifyAssemblyRef         = 0x01000000,  
    MDNotifyFile                = 0x02000000,  
    MDNotifyExportedType        = 0x04000000,  
    MDNotifyResource            = 0x08000000  
  
} CorNotificationForTokenMovement;  
```  
  
## <a name="members"></a><span data-ttu-id="13573-105">멤버</span><span class="sxs-lookup"><span data-stu-id="13573-105">Members</span></span>  
  
|<span data-ttu-id="13573-106">멤버</span><span class="sxs-lookup"><span data-stu-id="13573-106">Member</span></span>|<span data-ttu-id="13573-107">설명</span><span class="sxs-lookup"><span data-stu-id="13573-107">Description</span></span>|  
|------------|-----------------|  
|`MDNotifyDefault`|<span data-ttu-id="13573-108">될 경우 알림을 `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, 또는 `mdFieldDef` 토큰 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-108">Notify when `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, or `mdFieldDef` tokens move.</span></span>|  
|`MDNotifyAll`|<span data-ttu-id="13573-109">모든 토큰 이동 하면 알립니다.</span><span class="sxs-lookup"><span data-stu-id="13573-109">Notify when any token moves.</span></span>|  
|`MDNotifyNone`|<span data-ttu-id="13573-110">토큰 이동에 알리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13573-110">Do not notify when tokens move.</span></span>|  
|`MDNotifyMethodDef`|<span data-ttu-id="13573-111">될 경우 알림을 `mdMethodDef` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-111">Notify when an `mdMethodDef` token moves.</span></span>|  
|`MDNotifyMemberRef`|<span data-ttu-id="13573-112">될 경우 알림을 `mdMemberRef` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-112">Notify when an `mdMemberRef` token moves.</span></span>|  
|`MDNotifyFieldDef`|<span data-ttu-id="13573-113">될 경우 알림을 `mdFieldDef` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-113">Notify when an `mdFieldDef` token moves.</span></span>|  
|`MDNotifyTypeRef`|<span data-ttu-id="13573-114">될 경우 알림을 `mdTypeRef` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-114">Notify when an `mdTypeRef` token moves.</span></span>|  
|`MDNotifyTypeDef`|<span data-ttu-id="13573-115">될 경우 알림을 `mdTypeDef` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-115">Notify when an `mdTypeDef` token moves.</span></span>|  
|`MDNotifyParamDef`|<span data-ttu-id="13573-116">될 경우 알림을 `mdParamDef` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-116">Notify when an `mdParamDef` token moves.</span></span>|  
|`MDNotifyInterfaceImpl`|<span data-ttu-id="13573-117">될 경우 알림을 `mdInterfaceImpl` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-117">Notify when an `mdInterfaceImpl` token moves.</span></span>|  
|`MDNotifyProperty`|<span data-ttu-id="13573-118">될 경우 알림을 `mdProperty` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-118">Notify when an `mdProperty` token moves.</span></span>|  
|`MDNotifyEvent`|<span data-ttu-id="13573-119">될 경우 알림을 `mdEvent` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-119">Notify when an `mdEvent` token moves.</span></span>|  
|`MDNotifySignature`|<span data-ttu-id="13573-120">될 경우 알림을 `mdSignature` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-120">Notify when an `mdSignature` token moves.</span></span>|  
|`MDNotifyTypeSpec`|<span data-ttu-id="13573-121">될 경우 알림을 `mdTypeSpec` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-121">Notify when an `mdTypeSpec` token moves.</span></span>|  
|`MDNotifyCustomAttribute`|<span data-ttu-id="13573-122">될 경우 알림을 `mdCustomAttribute` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-122">Notify when an `mdCustomAttribute` token moves.</span></span>|  
|`MDNotifySecurityValue`|<span data-ttu-id="13573-123">될 경우 알림을 `mdSecurityValue` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-123">Notify when an `mdSecurityValue` token moves.</span></span>|  
|`MDNotifyPermission`|<span data-ttu-id="13573-124">될 경우 알림을 `mdPermission` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-124">Notify when an `mdPermission` token moves.</span></span>|  
|`MDNotifyModuleRef`|<span data-ttu-id="13573-125">될 경우 알림을 `mdModuleRef` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-125">Notify when an `mdModuleRef` token moves.</span></span>|  
|`MDNotifyNameSpace`|<span data-ttu-id="13573-126">될 경우 알림을 `mdNameSpace` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-126">Notify when an `mdNameSpace` token moves.</span></span>|  
|`MDNotifyAssemblyRef`|<span data-ttu-id="13573-127">될 경우 알림을 `mdAssemblyRef` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-127">Notify when an `mdAssemblyRef` token moves.</span></span>|  
|`MDNotifyFile`|<span data-ttu-id="13573-128">될 경우 알림을 `mdFile` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-128">Notify when an `mdFile` token moves.</span></span>|  
|`MDNotifyExportedType`|<span data-ttu-id="13573-129">될 경우 알림을 `mdExportedType` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-129">Notify when an `mdExportedType` token moves.</span></span>|  
|`MDNotifyResource`|<span data-ttu-id="13573-130">될 경우 알림을 `mdManifestResource` 토큰이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-130">Notify when an `mdManifestResource` token moves.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13573-131">설명</span><span class="sxs-lookup"><span data-stu-id="13573-131">Remarks</span></span>  
 <span data-ttu-id="13573-132">토큰을 다시 매핑할 수 (이동)이 표시 된 메타 데이터를 병합 하는 동안 합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-132">A token may be re-mapped (that is, moved) during a metadata merge.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13573-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="13573-133">Requirements</span></span>  
 <span data-ttu-id="13573-134">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="13573-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13573-135">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="13573-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="13573-136">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13573-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13573-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13573-137">See Also</span></span>  
 [<span data-ttu-id="13573-138">메타 데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="13573-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
