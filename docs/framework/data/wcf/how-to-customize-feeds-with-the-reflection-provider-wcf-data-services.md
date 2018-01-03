---
title: "방법: 리플렉션 공급자를 사용한 피드 사용자 지정(WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: 00c23dcf-9bb8-459a-a012-6c4d9bcad7e9
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0989436b3315f69727aeaca03d51d7fbd3cbb6fb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="8d87a-102">방법: 리플렉션 공급자를 사용한 피드 사용자 지정(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="8d87a-102">How to: Customize Feeds with the Reflection Provider (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="8d87a-103">를 사용하면 엔터티의 속성이 AtomPub 프로토콜에 정의된 사용하지 않은 요소에 매핑될 수 있도록 데이터 서비스 응답의 Atom serialization을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d87a-103"> enables you to customize the Atom serialization in a data service response so that properties of an entity may be mapped to unused elements that are defined in the AtomPub protocol.</span></span> <span data-ttu-id="8d87a-104">이 항목에서는 리플렉션 공급자를 사용하여 정의된 데이터 모델의 엔터티 형식에 대한 매핑 특성을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d87a-104">This topic shows how to define mapping attributes for the entity types in a data model that is defined by using the reflection provider.</span></span> <span data-ttu-id="8d87a-105">자세한 내용은 참조 [피드 사용자 지정](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8d87a-105">For more information, see [Feed Customization](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="8d87a-106">이 예제에 대 한 데이터 모델 항목에 정의 된 [하는 방법: 리플렉션 공급자를 사용 하 여 데이터 서비스 만들기](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="8d87a-106">The data model for this example is defined in the topic [How to: Create a Data Service Using the Reflection Provider](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d87a-107">예</span><span class="sxs-lookup"><span data-stu-id="8d87a-107">Example</span></span>  
 <span data-ttu-id="8d87a-108">다음 예제에서는 `Order` 형식의 두 속성이 모두 기존 Atom 요소에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d87a-108">In the following example, both properties of the `Order` type are mapped to existing Atom elements.</span></span> <span data-ttu-id="8d87a-109">`Product` 형식의 `Item` 속성은 별도 네임스페이스에 있는 사용자 지정 피드 특성에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d87a-109">The `Product` property of the `Item` type is mapped to a custom feed attribute in a separate namespace.</span></span>  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria custom feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria custom feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a><span data-ttu-id="8d87a-110">예</span><span class="sxs-lookup"><span data-stu-id="8d87a-110">Example</span></span>  
 <span data-ttu-id="8d87a-111">위 예제에서는 URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`에 대해 다음 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8d87a-111">The previous example returns the following result for the URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.</span></span>  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a><span data-ttu-id="8d87a-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d87a-112">See Also</span></span>  
 [<span data-ttu-id="8d87a-113">리플렉션 공급자</span><span class="sxs-lookup"><span data-stu-id="8d87a-113">Reflection Provider</span></span>](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
