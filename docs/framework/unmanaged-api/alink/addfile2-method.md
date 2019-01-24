---
title: AddFile2 메서드
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 078820649543479e65ec35daa6e1cc2876581ddc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693203"
---
# <a name="addfile2-method"></a><span data-ttu-id="9b7ed-102">AddFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="9b7ed-102">AddFile2 Method</span></span>
<span data-ttu-id="9b7ed-103">어셈블리 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7ed-103">Adds files to the assembly.</span></span> <span data-ttu-id="9b7ed-104">바인딩되지 않은 모듈을 만드는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b7ed-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b7ed-105">구문</span><span class="sxs-lookup"><span data-stu-id="9b7ed-105">Syntax</span></span>  
  
```  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b7ed-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9b7ed-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="9b7ed-107">파일이 추가 되는 어셈블리에 대 한 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7ed-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="9b7ed-108">추가할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7ed-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9b7ed-109">COM + `FileDef` 와 같은 플래그 `ffContainsNoMetaData` 고 `ffWriteable`입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7ed-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="9b7ed-110">`dwFlags` 에 전달 됩니다 [DefineFile 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7ed-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="9b7ed-111">인터페이스 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7ed-111">Interface to [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="9b7ed-112">추가할 파일의 ID를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="9b7ed-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b7ed-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="9b7ed-113">Return Value</span></span>  
 <span data-ttu-id="9b7ed-114">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7ed-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b7ed-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b7ed-115">Requirements</span></span>  
 <span data-ttu-id="9b7ed-116">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7ed-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b7ed-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="9b7ed-117">See also</span></span>
- [<span data-ttu-id="9b7ed-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b7ed-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="9b7ed-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b7ed-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="9b7ed-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="9b7ed-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
