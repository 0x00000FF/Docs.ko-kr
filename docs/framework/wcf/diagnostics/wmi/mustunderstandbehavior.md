---
title: MustUnderstandBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dca98f1d8d5f868285ecf11c01122f795ee6cfd8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="35813-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="35813-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="35813-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="35813-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35813-104">구문</span><span class="sxs-lookup"><span data-stu-id="35813-104">Syntax</span></span>  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="35813-105">메서드</span><span class="sxs-lookup"><span data-stu-id="35813-105">Methods</span></span>  
 <span data-ttu-id="35813-106">MustUnderstandBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35813-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="35813-107">속성</span><span class="sxs-lookup"><span data-stu-id="35813-107">Properties</span></span>  
 <span data-ttu-id="35813-108">MustUnderstandBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35813-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="35813-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="35813-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="35813-110">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="35813-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="35813-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="35813-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="35813-112">이 속성이 `true`인 경우 처리되지 않은 `MustUnderstand` 특성이 있는 모든 SOAP 헤더로 인해 예외를 throw하는 동작이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="35813-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35813-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="35813-113">Requirements</span></span>  
  
|<span data-ttu-id="35813-114">MOF</span><span class="sxs-lookup"><span data-stu-id="35813-114">MOF</span></span>|<span data-ttu-id="35813-115">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35813-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="35813-116">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="35813-116">Namespace</span></span>|<span data-ttu-id="35813-117">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35813-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35813-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35813-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>
