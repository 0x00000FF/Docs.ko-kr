---
title: EnumCustomAttributes 메서드
ms.date: 03/30/2017
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5d8827f46a12bd090fa27e71072d833607d34677
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777355"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="c1cc7-102">EnumCustomAttributes 메서드</span><span class="sxs-lookup"><span data-stu-id="c1cc7-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="c1cc7-103">어셈블리 수준 사용자 지정 특성을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1cc7-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1cc7-104">구문</span><span class="sxs-lookup"><span data-stu-id="c1cc7-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1cc7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c1cc7-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="c1cc7-106">열거자의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="c1cc7-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="c1cc7-107">열거할 특성의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c1cc7-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="c1cc7-108">모든 `mdTokenNill` 특성에 대해를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1cc7-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="c1cc7-109">사용자 지정 특성 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="c1cc7-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c1cc7-110">`rCustomValues` 배열의 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1cc7-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="c1cc7-111">필요에 따라 토큰 값의 개수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="c1cc7-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1cc7-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="c1cc7-112">Return Value</span></span>  
 <span data-ttu-id="c1cc7-113">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1cc7-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1cc7-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1cc7-114">Requirements</span></span>  
 <span data-ttu-id="c1cc7-115">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="c1cc7-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1cc7-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="c1cc7-116">See also</span></span>

- [<span data-ttu-id="c1cc7-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1cc7-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c1cc7-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1cc7-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c1cc7-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="c1cc7-119">ALink API</span></span>](index.md)
