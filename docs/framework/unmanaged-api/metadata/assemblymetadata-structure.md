---
title: ASSEMBLYMETADATA 구조체
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f988f95c28e6d2248882fb033b8d8c4d3c629229
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744195"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="87bd4-102">ASSEMBLYMETADATA 구조체</span><span class="sxs-lookup"><span data-stu-id="87bd4-102">ASSEMBLYMETADATA Structure</span></span>
<span data-ttu-id="87bd4-103">해당 버전 및 해당 수준의 로캘, 프로세서 및 운영 체제에 대 한 지원 포함 한 참조 된 어셈블리에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87bd4-104">구문</span><span class="sxs-lookup"><span data-stu-id="87bd4-104">Syntax</span></span>  
  
```  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a><span data-ttu-id="87bd4-105">멤버</span><span class="sxs-lookup"><span data-stu-id="87bd4-105">Members</span></span>  
  
|<span data-ttu-id="87bd4-106">멤버</span><span class="sxs-lookup"><span data-stu-id="87bd4-106">Member</span></span>|<span data-ttu-id="87bd4-107">설명</span><span class="sxs-lookup"><span data-stu-id="87bd4-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="87bd4-108">참조 된 어셈블리의 주 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="87bd4-109">이 값은 0 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-109">This value cannot be zero.</span></span> <span data-ttu-id="87bd4-110">하는 경우의 모든 비트가 `usMajorVersion` 주요 버전을 지정 하지 않으면 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="87bd4-111">참조 된 어셈블리의 부 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="87bd4-112">이 값은 0 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-112">This value cannot be zero.</span></span> <span data-ttu-id="87bd4-113">하는 경우의 모든 비트가 `usMinorVersion` 부 버전을 지정 하지 않으면 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="87bd4-114">참조 된 어셈블리의 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="87bd4-115">이 값은 0 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-115">This value cannot be zero.</span></span> <span data-ttu-id="87bd4-116">하는 경우의 모든 비트가 `usBuildNumber` 빌드 번호를 지정 하지 않으면 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="87bd4-117">참조 된 어셈블리의 수정 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="87bd4-118">이 값은 0 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-118">This value cannot be zero.</span></span> <span data-ttu-id="87bd4-119">하는 경우의 모든 비트가 `usRevisionNumber` 수정 번호를 지정 하지 않으면 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="87bd4-120">목록에 참조 된 어셈블리에서 지원 되는 로캘을 지정 세미콜론으로 구분 된 RFC1766 사양에 맞는 로캘 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="87bd4-121">Null 값에는 로캘과 관련이 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-121">A null value indicates locale independence.</span></span> <span data-ttu-id="87bd4-122">**참고:**  .NET framework 버전 1.0 둘 이상의 로캘을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="87bd4-123">와이드 문자에서 크기 `szLocale`합니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="87bd4-124">참조 된 어셈블리에서 지원 되는 프로세서 유형에 대 한 Winnt.h에 정의 된 식별자의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="87bd4-125">NULL 값에는 프로세서 관련이 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="87bd4-126">`rdwProcessor` 배열의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="87bd4-127">배열을 [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) 참조 된 어셈블리에서 지원 되는 운영 체제를 지정 하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="87bd4-127">An array of [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="87bd4-128">NULL 값에는 운영 체제 관련이 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="87bd4-129">`rOS` 배열의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="87bd4-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="87bd4-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="87bd4-130">Requirements</span></span>  
 <span data-ttu-id="87bd4-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="87bd4-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87bd4-132">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="87bd4-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="87bd4-133">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="87bd4-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="87bd4-134">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87bd4-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87bd4-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="87bd4-135">See also</span></span>
- [<span data-ttu-id="87bd4-136">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="87bd4-136">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="87bd4-137">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87bd4-137">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="87bd4-138">OSINFO 구조체</span><span class="sxs-lookup"><span data-stu-id="87bd4-138">OSINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
