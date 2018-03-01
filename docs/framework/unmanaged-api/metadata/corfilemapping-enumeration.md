---
title: "CorFileMapping 열거형"
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
- CorFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileMapping
helpviewer_keywords:
- CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5abde0d34baecf12628c9c6c99f04d6d81dd62fa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="52eae-102">CorFileMapping 열거형</span><span class="sxs-lookup"><span data-stu-id="52eae-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="52eae-103">에 대 한 호출에서 반환 되는 파일 매핑의 형식을 설명 하는 값이 포함 되어는 [imetadatainfo:: Getfilemapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="52eae-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52eae-104">구문</span><span class="sxs-lookup"><span data-stu-id="52eae-104">Syntax</span></span>  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="52eae-105">멤버</span><span class="sxs-lookup"><span data-stu-id="52eae-105">Members</span></span>  
  
|<span data-ttu-id="52eae-106">멤버</span><span class="sxs-lookup"><span data-stu-id="52eae-106">Member</span></span>|<span data-ttu-id="52eae-107">설명</span><span class="sxs-lookup"><span data-stu-id="52eae-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="52eae-108">파일은 데이터 파일로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="52eae-108">The file is mapped as a data file.</span></span> <span data-ttu-id="52eae-109">즉,는 `SEC_IMAGE` 플래그는 Microsoft Win32 전달 되지 않으므로 `CreateFileMapping` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="52eae-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="52eae-110">파일 중 하나를 사용 하 여 실행을 위해 매핑된는 `LoadLibrary` 함수 또는 `CreateFileMapping` 작동는 `SEC_IMAGE` 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="52eae-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="52eae-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52eae-111">Requirements</span></span>  
 <span data-ttu-id="52eae-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="52eae-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52eae-113">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="52eae-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="52eae-114">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52eae-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52eae-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52eae-115">See Also</span></span>  
 [<span data-ttu-id="52eae-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="52eae-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="52eae-117">GetFileMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="52eae-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
