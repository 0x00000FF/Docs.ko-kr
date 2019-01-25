---
title: CorNativeLinkType 열거형
ms.date: 03/30/2017
api_name:
- CorNativeLinkType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkType
helpviewer_keywords:
- CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f946179fc31adebc8e8fc67c394e0b55a876f49
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641332"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="3e326-102">CorNativeLinkType 열거형</span><span class="sxs-lookup"><span data-stu-id="3e326-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="3e326-103">네이티브 코드에서 연결된 형식을 나타내는 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e326-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e326-104">구문</span><span class="sxs-lookup"><span data-stu-id="3e326-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a><span data-ttu-id="3e326-105">멤버</span><span class="sxs-lookup"><span data-stu-id="3e326-105">Members</span></span>  
  
|<span data-ttu-id="3e326-106">멤버</span><span class="sxs-lookup"><span data-stu-id="3e326-106">Member</span></span>|<span data-ttu-id="3e326-107">설명</span><span class="sxs-lookup"><span data-stu-id="3e326-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="3e326-108">키워드 하나도 지정 되어 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3e326-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="3e326-109">ANSI 키워드가 지정 되어 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3e326-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="3e326-110">Unicode 키워드 지정 되어 있는지 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3e326-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="3e326-111">Auto 키워드는 지정 되어 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3e326-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="3e326-112">OLE 키워드가 지정 되어 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3e326-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="3e326-113">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e326-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3e326-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e326-114">Requirements</span></span>  
 <span data-ttu-id="3e326-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3e326-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e326-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3e326-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3e326-117">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3e326-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3e326-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e326-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e326-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="3e326-119">See also</span></span>
- [<span data-ttu-id="3e326-120">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="3e326-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
