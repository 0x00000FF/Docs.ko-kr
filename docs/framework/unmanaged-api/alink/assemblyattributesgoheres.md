---
title: AssemblyAttributesGoHereS
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereS
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereS
helpviewer_keywords:
- AssemblyAttributesGoHereS type
- Alink API, AssemblyAttributesGoHereS type
ms.assetid: 4e817f35-a2bc-4403-9e6f-f731e6b9fe23
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 74447f52c75ae22e513c6f07950630d37bad191a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969832"
---
# <a name="assemblyattributesgoheres"></a><span data-ttu-id="9a1b7-102">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="9a1b7-102">AssemblyAttributesGoHereS</span></span>

<span data-ttu-id="9a1b7-103">ALink에서 사용자 지정 특성 정보를 저장하는 자리 표시자로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a1b7-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="9a1b7-104">구문</span><span class="sxs-lookup"><span data-stu-id="9a1b7-104">Syntax</span></span>

```
internal sealed class AssemblyAttributesGoHereS
```

## <a name="remarks"></a><span data-ttu-id="9a1b7-105">설명</span><span class="sxs-lookup"><span data-stu-id="9a1b7-105">Remarks</span></span>

<span data-ttu-id="9a1b7-106">이 형식에 대한 참조는 소스에 어셈블리 사용자 지정 특성이 들어 있는 netmodule 내부에 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a1b7-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="9a1b7-107">이러한 유형에 대한 참조가 포함된 netmodule 하나 이상에서 어셈블리 매니페스트를 빌드할 때 ALink에서는 이들 참조에 연결된 정보를 사용하여 실제 사용자 지정 특성을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a1b7-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="9a1b7-108">따라서 이 형식은 인스턴스화되지 않으며, 이에 대한 참조는 빌드 프로세스 부분으로만 사용되고 최종 어셈블리에서 도움이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a1b7-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="9a1b7-109">이 형식에 대한 참조는 보안과 관련이 있고 다양한 용도로 사용되지 않는 사용자 지정 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a1b7-109">References to this type indicate custom attributes that are security related and are not multiple-use.</span></span>

<span data-ttu-id="9a1b7-110">이러한 형식은 "내부".NET Framework 내에서 표시 되 고에 위치한는 <xref:System.Runtime.CompilerServices> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9a1b7-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="9a1b7-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a1b7-111">Requirements</span></span>

<span data-ttu-id="9a1b7-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="9a1b7-112">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="9a1b7-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="9a1b7-113">See also</span></span>

- [<span data-ttu-id="9a1b7-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="9a1b7-114">AssemblyAttributesGoHere</span></span>](assemblyattributesgohere.md)
- [<span data-ttu-id="9a1b7-115">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="9a1b7-115">AssemblyAttributesGoHereM</span></span>](assemblyattributesgoherem.md)
- [<span data-ttu-id="9a1b7-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="9a1b7-116">AssemblyAttributesGoHereSM</span></span>](assemblyattributesgoheresm.md)
