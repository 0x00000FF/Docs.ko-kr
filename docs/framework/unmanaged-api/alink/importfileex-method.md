---
title: ImportFileEx 메서드
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd138d0418bb9667a86419d719bf0b95a4bb1b12
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777123"
---
# <a name="importfileex-method"></a><span data-ttu-id="86bc7-102">ImportFileEx 메서드</span><span class="sxs-lookup"><span data-stu-id="86bc7-102">ImportFileEx Method</span></span>
<span data-ttu-id="86bc7-103">표시 된 어셈블리 또는 바인딩되지 않은 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="86bc7-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86bc7-104">구문</span><span class="sxs-lookup"><span data-stu-id="86bc7-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="86bc7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="86bc7-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="86bc7-106">가져올 파일의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="86bc7-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="86bc7-107">대상 파일의 선택적 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="86bc7-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="86bc7-108">TRUE 이면 ImportTypes를 사용 합니다. 그렇지 않으면 가져오기는 수동으로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86bc7-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="86bc7-109">[Openscope 메서드에](../metadata/imetadatadispenser-openscope-method.md)따라 전달할 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="86bc7-109">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="86bc7-110">가져올 파일의 ID를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="86bc7-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="86bc7-111">어셈블리 가져오기 범위 [IMetaDataAssemblyImport interface](../metadata/imetadataassemblyimport-interface.md) 인터페이스를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="86bc7-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="86bc7-112">파일이 어셈블리가 아닌 경우 NULL로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86bc7-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="86bc7-113">가져온 파일 및/또는 범위의 수를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="86bc7-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86bc7-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="86bc7-114">Return Value</span></span>  
 <span data-ttu-id="86bc7-115">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="86bc7-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86bc7-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="86bc7-116">Requirements</span></span>  
 <span data-ttu-id="86bc7-117">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="86bc7-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86bc7-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="86bc7-118">See also</span></span>

- [<span data-ttu-id="86bc7-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86bc7-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="86bc7-120">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86bc7-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="86bc7-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="86bc7-121">ALink API</span></span>](index.md)
