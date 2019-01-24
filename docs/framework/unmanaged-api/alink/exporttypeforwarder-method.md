---
title: ExportTypeForwarder 메서드
ms.date: 03/30/2017
api_name:
- IALink.ExportTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportTypeForwarder
helpviewer_keywords:
- ExportTypeForwarder method
ms.assetid: 55989fa9-ab43-4f08-8eb6-2eb56fa7ca76
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 03949fb52d23e3b0f107f9f1d5208208369c3960
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574615"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="6ec03-102">ExportTypeForwarder 메서드</span><span class="sxs-lookup"><span data-stu-id="6ec03-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="6ec03-103">형식 전달 자가 지정된 된 어셈블리의 type 테이블에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec03-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ec03-104">구문</span><span class="sxs-lookup"><span data-stu-id="6ec03-104">Syntax</span></span>  
  
```  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ec03-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ec03-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="6ec03-106">형식 전달 자가 참조 하는 어셈블리에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="6ec03-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="6ec03-107">내보낼 정규화 된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6ec03-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6ec03-108">`ComType` 와 같은 플래그 `tdPublic` 또는 `tdNested`합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec03-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="6ec03-109">이 값을 전달할 수 있습니다 [DefineExportedType 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec03-109">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="6ec03-110">내보낸 형식의 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="6ec03-110">Receives the token of the exported type.</span></span> <span data-ttu-id="6ec03-111">이 중첩 된 형식을 내보내는에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec03-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ec03-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="6ec03-112">Return Value</span></span>  
 <span data-ttu-id="6ec03-113">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec03-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ec03-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ec03-114">Requirements</span></span>  
 <span data-ttu-id="6ec03-115">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="6ec03-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ec03-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="6ec03-116">See also</span></span>
- [<span data-ttu-id="6ec03-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ec03-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="6ec03-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ec03-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="6ec03-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="6ec03-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
