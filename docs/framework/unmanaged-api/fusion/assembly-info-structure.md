---
title: ASSEMBLY_INFO 구조체
ms.date: 03/30/2017
api_name:
- ASSEMBLY_INFO
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASSEMBLY_INFO
helpviewer_keywords:
- ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ed65181abab58117d539d23fcfeffe71ac19388
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430572"
---
# <a name="assemblyinfo-structure"></a><span data-ttu-id="b5132-102">ASSEMBLY_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="b5132-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="b5132-103">전역 어셈블리 캐시에 등록 되어 있는 어셈블리에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5132-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5132-104">구문</span><span class="sxs-lookup"><span data-stu-id="b5132-104">Syntax</span></span>  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="b5132-105">멤버</span><span class="sxs-lookup"><span data-stu-id="b5132-105">Members</span></span>  
  
|<span data-ttu-id="b5132-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b5132-106">Member</span></span>|<span data-ttu-id="b5132-107">설명</span><span class="sxs-lookup"><span data-stu-id="b5132-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="b5132-108">구조체의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="b5132-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="b5132-109">이 필드는 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5132-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="b5132-110">어셈블리에 대 한 설치 세부 정보를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="b5132-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="b5132-111">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5132-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="b5132-112">-ASSEMBLYINFO_FLAG_INSTALLED 나타내는 값을 어셈블리가 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5132-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="b5132-113">현재 버전의.NET Framework 항상 설정 `dwAssemblyFlags` 이 값으로.</span><span class="sxs-lookup"><span data-stu-id="b5132-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="b5132-114">-ASSEMBLYINFO_FLAG_PAYLOADRESIDENT 값, 상주 페이로드 어셈블리 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b5132-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="b5132-115">현재 버전의.NET Framework를 설정 하지 `dwAssemblyFlags` 이 값으로.</span><span class="sxs-lookup"><span data-stu-id="b5132-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="b5132-116">(킬로바이트) 어셈블리에 포함 되어 있는 파일의 총 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="b5132-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="b5132-117">매니페스트 파일에는 현재 경로 보유 하는 문자열 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b5132-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="b5132-118">경로 null 문자로 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5132-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="b5132-119">Null 종결자를 포함 하는 와이드 문자의 수를 `pszCurrentAssemblyPathBuf` 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5132-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5132-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b5132-120">Requirements</span></span>  
 <span data-ttu-id="b5132-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b5132-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5132-122">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b5132-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b5132-123">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5132-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5132-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5132-124">See Also</span></span>  
 [<span data-ttu-id="b5132-125">Fusion 구조체</span><span class="sxs-lookup"><span data-stu-id="b5132-125">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [<span data-ttu-id="b5132-126">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="b5132-126">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
