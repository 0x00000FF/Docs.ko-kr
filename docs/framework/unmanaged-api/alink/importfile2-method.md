---
title: ImportFile2 메서드
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c6279c790e9b28e5f3bac93d5d0fdd411dd8c0d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127272"
---
# <a name="importfile2-method"></a><span data-ttu-id="3061b-102">ImportFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="3061b-102">ImportFile2 Method</span></span>
<span data-ttu-id="3061b-103">어셈블리 및 바인딩되지 않은 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3061b-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="3061b-104">이 메서드는 [ImportFile 메서드](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), 되지만 가져올 파일 디스크에 없는 경우 경우에 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3061b-104">This method is like [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3061b-105">구문</span><span class="sxs-lookup"><span data-stu-id="3061b-105">Syntax</span></span>  
  
```  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3061b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3061b-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="3061b-107">가져올 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3061b-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="3061b-108">어셈블리에 링크 되어 파일의 이름을 사용할 수 있는 선택적 출력 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3061b-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="3061b-109">선택적 범위 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3061b-109">Optional scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="3061b-110">TRUE 이면 ImportTypes 되, 그렇지 않으면 가져오기는 수동으로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3061b-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="3061b-111">파일 또는 어셈블리에 대 한 ID를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3061b-111">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="3061b-112">수신 된 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3061b-112">Receives the [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="3061b-113">파일 어셈블리가 아닌 경우 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="3061b-113">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="3061b-114">파일 및/또는 가져온 범위 발견을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3061b-114">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3061b-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="3061b-115">Return Value</span></span>  
 <span data-ttu-id="3061b-116">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3061b-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3061b-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3061b-117">Requirements</span></span>  
 <span data-ttu-id="3061b-118">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3061b-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3061b-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="3061b-119">See also</span></span>

- [<span data-ttu-id="3061b-120">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3061b-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3061b-121">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3061b-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="3061b-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="3061b-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
