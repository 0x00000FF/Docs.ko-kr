---
title: '&lt;transactionFlow&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8c40b3a79567ccc1ca5a83631253d3ff6ead0f84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="lttransactionflowgt"></a><span data-ttu-id="c1ab6-102">&lt;transactionFlow&gt;</span><span class="sxs-lookup"><span data-stu-id="c1ab6-102">&lt;transactionFlow&gt;</span></span>
<span data-ttu-id="c1ab6-103">사용자 지정 바인딩에 대한 트랜잭션 흐름 지원을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ab6-103">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="c1ab6-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="c1ab6-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c1ab6-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="c1ab6-105">\<bindings></span></span>  
<span data-ttu-id="c1ab6-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="c1ab6-106">\<customBinding></span></span>  
<span data-ttu-id="c1ab6-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="c1ab6-107">\<binding></span></span>  
<span data-ttu-id="c1ab6-108">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="c1ab6-108">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ab6-109">구문</span><span class="sxs-lookup"><span data-stu-id="c1ab6-109">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1ab6-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c1ab6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c1ab6-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ab6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1ab6-112">특성</span><span class="sxs-lookup"><span data-stu-id="c1ab6-112">Attributes</span></span>  
  
|<span data-ttu-id="c1ab6-113">특성</span><span class="sxs-lookup"><span data-stu-id="c1ab6-113">Attribute</span></span>|<span data-ttu-id="c1ab6-114">설명</span><span class="sxs-lookup"><span data-stu-id="c1ab6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c1ab6-115">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="c1ab6-115">transactionProtocol</span></span>|<span data-ttu-id="c1ab6-116">사용할 트랜잭션 프로토콜을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ab6-116">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="c1ab6-117">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ab6-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c1ab6-118">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="c1ab6-118">-   OleTransactions</span></span><br /><span data-ttu-id="c1ab6-119">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="c1ab6-119">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="c1ab6-120">기본값은 OleTransactions입니다.</span><span class="sxs-lookup"><span data-stu-id="c1ab6-120">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="c1ab6-121">이 특성은 <xref:System.ServiceModel.TransactionProtocol> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c1ab6-121">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1ab6-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c1ab6-122">Child Elements</span></span>  
 <span data-ttu-id="c1ab6-123">없음</span><span class="sxs-lookup"><span data-stu-id="c1ab6-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1ab6-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c1ab6-124">Parent Elements</span></span>  
  
|<span data-ttu-id="c1ab6-125">요소</span><span class="sxs-lookup"><span data-stu-id="c1ab6-125">Element</span></span>|<span data-ttu-id="c1ab6-126">설명</span><span class="sxs-lookup"><span data-stu-id="c1ab6-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1ab6-127">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="c1ab6-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="c1ab6-128">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ab6-128">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1ab6-129">설명</span><span class="sxs-lookup"><span data-stu-id="c1ab6-129">Remarks</span></span>  
 <span data-ttu-id="c1ab6-130">이 요소를 사용하면 끝점의 바인딩 설정에 들어오는 트랜잭션 흐름을 사용하거나 사용하지 않도록 설정할 수 있을 뿐 아니라 들어오는 트랜잭션에 대해 원하는 프로토콜 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ab6-130">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="c1ab6-131">이 구성 요소를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [ServiceModel 트랜잭션 구성](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) 및 [트랜잭션 흐름을 사용 하도록 설정](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ab6-131">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="c1ab6-132">`OleTransactions` 프로토콜을 사용하여 끝점 간에 트랜잭션을 전달할 경우 대상 끝점에서 `OleTransactions` 이외의 프로토콜을 사용하여 트랜잭션을 다시 전달하려고 하면 트랜잭션 시간 제한이 상실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ab6-132">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="c1ab6-133">따라서 OleTransactions 홉 뒤의 모든 하위 수준 노드가 예상보다 늦게 시간이 초과될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ab6-133">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ab6-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1ab6-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransactionFlowElement>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="c1ab6-135">ServiceModel 트랜잭션 구성</span><span class="sxs-lookup"><span data-stu-id="c1ab6-135">ServiceModel Transaction Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)  
 [<span data-ttu-id="c1ab6-136">트랜잭션 흐름 사용</span><span class="sxs-lookup"><span data-stu-id="c1ab6-136">Enabling Transaction Flow</span></span>](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)  
 [<span data-ttu-id="c1ab6-137">바인딩</span><span class="sxs-lookup"><span data-stu-id="c1ab6-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c1ab6-138">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="c1ab6-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="c1ab6-139">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="c1ab6-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="c1ab6-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="c1ab6-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
