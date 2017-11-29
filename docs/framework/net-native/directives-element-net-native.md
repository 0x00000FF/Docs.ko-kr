---
title: "&lt;지시문&gt; 요소(.NET 네이티브)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a55048ea5b2889da82b10ac2a51865d945635143
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltdirectivesgt-element-net-native"></a><span data-ttu-id="d99c1-102">&lt;지시문&gt; 요소(.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="d99c1-102">&lt;Directives&gt; Element (.NET Native)</span></span>
<span data-ttu-id="d99c1-103">[!INCLUDE[net_native](../../../includes/net-native-md.md)]용 모든 런타임 지시문의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d99c1-103">The root element in every runtime directives file for [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="d99c1-104">**\<Directives xmlns=“http://schemas.microsoft.com/netfx/2013/01/metadata”>**</span><span class="sxs-lookup"><span data-stu-id="d99c1-104">**\<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d99c1-105">구문</span><span class="sxs-lookup"><span data-stu-id="d99c1-105">Syntax</span></span>  
  
```xml  
      <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="d99c1-106">특성</span><span class="sxs-lookup"><span data-stu-id="d99c1-106">Attributes</span></span>  
  
|<span data-ttu-id="d99c1-107">특성</span><span class="sxs-lookup"><span data-stu-id="d99c1-107">Attribute</span></span>|<span data-ttu-id="d99c1-108">설명</span><span class="sxs-lookup"><span data-stu-id="d99c1-108">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="d99c1-109">XML 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d99c1-109">The XML namespace.</span></span> <span data-ttu-id="d99c1-110">해당 값은 항상 **“http://schemas.microsoft.com/netfx/2013/01/metadata”**입니다.</span><span class="sxs-lookup"><span data-stu-id="d99c1-110">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="d99c1-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d99c1-111">Child elements</span></span>  
  
|<span data-ttu-id="d99c1-112">요소</span><span class="sxs-lookup"><span data-stu-id="d99c1-112">Element</span></span>|<span data-ttu-id="d99c1-113">설명</span><span class="sxs-lookup"><span data-stu-id="d99c1-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d99c1-114">\<Application></span><span class="sxs-lookup"><span data-stu-id="d99c1-114">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="d99c1-115">해당 메타데이터를 리플렉션에 사용할 수 있는 응용 프로그램 수준 형식 및 형식 멤버의 컨테이너로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d99c1-115">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="d99c1-116">\<Library></span><span class="sxs-lookup"><span data-stu-id="d99c1-116">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="d99c1-117">런타임에 자식 형식 및 형식 멤버에 메타데이터가 필요한 어셈블리를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d99c1-117">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d99c1-118">설명</span><span class="sxs-lookup"><span data-stu-id="d99c1-118">Remarks</span></span>  
 <span data-ttu-id="d99c1-119">각 런타임 지시문 파일은 `<Directives>` 요소를 하나만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d99c1-119">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="d99c1-120">`<Directives>` 요소는 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 요소를 포함하지 않거나 하나 포함할 수 있으며 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) 요소를 포함하지 않거나 하나 이상 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d99c1-120">The `<Directives>` element can contain zero or one [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element, and zero, one, or more [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d99c1-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d99c1-121">See Also</span></span>  
 [<span data-ttu-id="d99c1-122">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="d99c1-122">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="d99c1-123">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="d99c1-123">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
