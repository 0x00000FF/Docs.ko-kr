---
title: '&lt;namespaceTable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 470dd2dcc2e8554bb89eec159c6b96b24795c5d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltnamespacetablegt"></a><span data-ttu-id="f1ba1-102">&lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="f1ba1-102">&lt;namespaceTable&gt;</span></span>

<span data-ttu-id="f1ba1-103">매핑을 앞에 붙인 다음 XPath 필터에서 라우팅에 사용할 수 있는 네임스페이스를 포함하는 요소 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-103">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="f1ba1-104">**\<system.serviceModel >** </span><span class="sxs-lookup"><span data-stu-id="f1ba1-104">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="f1ba1-105">&nbsp;&nbsp;**\<라우팅 >** </span><span class="sxs-lookup"><span data-stu-id="f1ba1-105">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="f1ba1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="f1ba1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f1ba1-107">구문</span><span class="sxs-lookup"><span data-stu-id="f1ba1-107">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String" prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
``` 

## <a name="attributes-and-elements"></a><span data-ttu-id="f1ba1-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f1ba1-108">Attributes and elements</span></span>

<span data-ttu-id="f1ba1-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f1ba1-110">특성</span><span class="sxs-lookup"><span data-stu-id="f1ba1-110">Attributes</span></span>

<span data-ttu-id="f1ba1-111">없음</span><span class="sxs-lookup"><span data-stu-id="f1ba1-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="f1ba1-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f1ba1-112">Child elements</span></span>

|     | <span data-ttu-id="f1ba1-113">설명</span><span class="sxs-lookup"><span data-stu-id="f1ba1-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f1ba1-114">**\<필터 >**</span><span class="sxs-lookup"><span data-stu-id="f1ba1-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="f1ba1-115">XPath 식에 사용되는 네임스페이스 접두사 매핑을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="f1ba1-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f1ba1-116">Parent elements</span></span>

|     | <span data-ttu-id="f1ba1-117">설명</span><span class="sxs-lookup"><span data-stu-id="f1ba1-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f1ba1-118">**\<라우팅 >**</span><span class="sxs-lookup"><span data-stu-id="f1ba1-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="f1ba1-119">들어오는 메시지 및 필터가 일치할 때 메시지를 보낼 대상 끝점을 정의하는 라우팅 테이블을 평가할 때 사용되는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> 형식을 결정하는 라우팅 필터 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-119">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f1ba1-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1ba1-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
