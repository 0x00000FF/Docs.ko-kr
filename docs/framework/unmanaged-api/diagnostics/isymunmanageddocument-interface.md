---
title: ISymUnmanagedDocument 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b14333235882efb6da1ce011c109c67a1d149bf3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584521"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="7d524-102">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d524-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="7d524-103">기호 저장소가 참조하는 문서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d524-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="7d524-104">문서는 uniform resource locator (URL) 및 문서 형식 GUID에 따라 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d524-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="7d524-105">URL을 사용 하 여 저장 하는 방법에 관계 없이 문서를 찾을 수 있으며 문서 유형 GUID 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d524-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="7d524-106">문서 소스를 기호 저장소에 저장 하 고이 인터페이스를 통해 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d524-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7d524-107">메서드</span><span class="sxs-lookup"><span data-stu-id="7d524-107">Methods</span></span>  
  
|<span data-ttu-id="7d524-108">메서드</span><span class="sxs-lookup"><span data-stu-id="7d524-108">Method</span></span>|<span data-ttu-id="7d524-109">설명</span><span class="sxs-lookup"><span data-stu-id="7d524-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7d524-110">FindClosestLine 메서드</span><span class="sxs-lookup"><span data-stu-id="7d524-110">FindClosestLine Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="7d524-111">줄 시퀀스 위치가 될 수 있고이 문서에 지정 된 시퀀스 위치가 되는 가장 가까운 줄을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d524-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="7d524-112">GetCheckSum 메서드</span><span class="sxs-lookup"><span data-stu-id="7d524-112">GetCheckSum Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="7d524-113">체크섬을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7d524-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="7d524-114">GetCheckSumAlgorithmId 메서드</span><span class="sxs-lookup"><span data-stu-id="7d524-114">GetCheckSumAlgorithmId Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="7d524-115">체크섬 알고리즘 식별자를 가져오거나 체크섬이 없는 경우에 모두 0으로 GUID를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d524-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="7d524-116">GetDocumentType 메서드</span><span class="sxs-lookup"><span data-stu-id="7d524-116">GetDocumentType Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="7d524-117">이 문서의 문서 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7d524-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="7d524-118">GetLanguage 메서드</span><span class="sxs-lookup"><span data-stu-id="7d524-118">GetLanguage Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="7d524-119">이 문서의 언어 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7d524-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="7d524-120">GetLanguageVendor 메서드</span><span class="sxs-lookup"><span data-stu-id="7d524-120">GetLanguageVendor Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="7d524-121">이 문서의 언어 공급 업체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7d524-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="7d524-122">GetSourceLength 메서드</span><span class="sxs-lookup"><span data-stu-id="7d524-122">GetSourceLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="7d524-123">포함 소스의 길이(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7d524-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="7d524-124">GetSourceRange 메서드</span><span class="sxs-lookup"><span data-stu-id="7d524-124">GetSourceRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="7d524-125">지정 된 버퍼에 지정된 된 포함된 된 소스 범위를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7d524-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="7d524-126">GetURL 메서드</span><span class="sxs-lookup"><span data-stu-id="7d524-126">GetURL Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|<span data-ttu-id="7d524-127">이 문서에 대 한 URL을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7d524-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="7d524-128">HasEmbeddedSource 메서드</span><span class="sxs-lookup"><span data-stu-id="7d524-128">HasEmbeddedSource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="7d524-129">반환 `true` 문서에 소스가 디버깅 기호;에 포함 되어 있으면 반환이 고, 그렇지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="7d524-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d524-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="7d524-130">See also</span></span>
- [<span data-ttu-id="7d524-131">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d524-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
