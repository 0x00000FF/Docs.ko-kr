---
title: 209 - MessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
ms.openlocfilehash: 24184c24b9affdf3a56d7968c02cf5354d690749
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781885"
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="d6e5d-102">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="d6e5d-102">209 - MessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="d6e5d-103">속성</span><span class="sxs-lookup"><span data-stu-id="d6e5d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6e5d-104">ID</span><span class="sxs-lookup"><span data-stu-id="d6e5d-104">ID</span></span>|<span data-ttu-id="d6e5d-105">209</span><span class="sxs-lookup"><span data-stu-id="d6e5d-105">209</span></span>|  
|<span data-ttu-id="d6e5d-106">키워드</span><span class="sxs-lookup"><span data-stu-id="d6e5d-106">Keywords</span></span>|<span data-ttu-id="d6e5d-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d6e5d-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="d6e5d-108">수준</span><span class="sxs-lookup"><span data-stu-id="d6e5d-108">Level</span></span>|<span data-ttu-id="d6e5d-109">정보</span><span class="sxs-lookup"><span data-stu-id="d6e5d-109">Information</span></span>|  
|<span data-ttu-id="d6e5d-110">채널</span><span class="sxs-lookup"><span data-stu-id="d6e5d-110">Channel</span></span>|<span data-ttu-id="d6e5d-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="d6e5d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d6e5d-112">설명</span><span class="sxs-lookup"><span data-stu-id="d6e5d-112">Description</span></span>  
 <span data-ttu-id="d6e5d-113">이 이벤트는 서비스 모델이 메시지 검사자에 대해 `BeforeSend` 메서드를 호출한 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d6e5d-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d6e5d-114">메시지</span><span class="sxs-lookup"><span data-stu-id="d6e5d-114">Message</span></span>  
 <span data-ttu-id="d6e5d-115">디스패처가 '%1' 형식의 MessageInspector에 대해 'BeforeSendRequest'를 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e5d-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d6e5d-116">설명</span><span class="sxs-lookup"><span data-stu-id="d6e5d-116">Details</span></span>  
  
|<span data-ttu-id="d6e5d-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="d6e5d-117">Data Item Name</span></span>|<span data-ttu-id="d6e5d-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="d6e5d-118">Data Item Type</span></span>|<span data-ttu-id="d6e5d-119">설명</span><span class="sxs-lookup"><span data-stu-id="d6e5d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d6e5d-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="d6e5d-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="d6e5d-121">호출된 `MessageInspector` 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e5d-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="d6e5d-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="d6e5d-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="d6e5d-123">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e5d-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="d6e5d-124">해당 형식으로 정의 됩니다 ' Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="d6e5d-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="d6e5d-125">예제: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="d6e5d-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="d6e5d-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d6e5d-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d6e5d-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e5d-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
