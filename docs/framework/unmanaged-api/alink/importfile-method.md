---
title: ImportFile 메서드
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 116ed60dab3365cac052d3b13ce7b056caca0452
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619680"
---
# <a name="importfile-method"></a><span data-ttu-id="10201-102">ImportFile 메서드</span><span class="sxs-lookup"><span data-stu-id="10201-102">ImportFile Method</span></span>
<span data-ttu-id="10201-103">어셈블리 및 바인딩되지 않은 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="10201-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10201-104">구문</span><span class="sxs-lookup"><span data-stu-id="10201-104">Syntax</span></span>  
  
```  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10201-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="10201-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="10201-106">가져올 파일의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="10201-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="10201-107">어셈블리에 링크 되어 파일의 이름을 사용할 수 있는 선택적 출력 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="10201-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="10201-108">TRUE 이면 ImportTypes 되, 그렇지 않으면 가져오기는 수동으로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10201-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="10201-109">고유한 파일 ID를 저장할 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="10201-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="10201-110">어셈블리 또는 파일의 파일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10201-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="10201-111">에 대 한 포인터를 받는 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="10201-111">Receives pointer to [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="10201-112">파일 어셈블리가 아닌 경우 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10201-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="10201-113">파일 및/또는 가져온 범위 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="10201-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10201-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="10201-114">Return Value</span></span>  
 <span data-ttu-id="10201-115">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="10201-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10201-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="10201-116">Requirements</span></span>  
 <span data-ttu-id="10201-117">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="10201-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10201-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="10201-118">See also</span></span>
- [<span data-ttu-id="10201-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10201-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="10201-120">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10201-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="10201-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="10201-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
