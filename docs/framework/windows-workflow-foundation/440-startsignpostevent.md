---
title: 440 - StartSignpostEvent
ms.date: 03/30/2017
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
ms.openlocfilehash: 4b2b6b0fa9df4725edd4929512eb1d7534d933b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774172"
---
# <a name="440---startsignpostevent1"></a><span data-ttu-id="56a63-102">440 - StartSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="56a63-102">440 - StartSignpostEvent1</span></span>
## <a name="properties"></a><span data-ttu-id="56a63-103">속성</span><span class="sxs-lookup"><span data-stu-id="56a63-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="56a63-104">ID</span><span class="sxs-lookup"><span data-stu-id="56a63-104">ID</span></span>|<span data-ttu-id="56a63-105">440</span><span class="sxs-lookup"><span data-stu-id="56a63-105">440</span></span>|  
|<span data-ttu-id="56a63-106">키워드</span><span class="sxs-lookup"><span data-stu-id="56a63-106">Keywords</span></span>|<span data-ttu-id="56a63-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="56a63-107">Troubleshooting</span></span>|  
|<span data-ttu-id="56a63-108">수준</span><span class="sxs-lookup"><span data-stu-id="56a63-108">Level</span></span>|<span data-ttu-id="56a63-109">정보</span><span class="sxs-lookup"><span data-stu-id="56a63-109">Information</span></span>|  
|<span data-ttu-id="56a63-110">채널</span><span class="sxs-lookup"><span data-stu-id="56a63-110">Channel</span></span>|<span data-ttu-id="56a63-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="56a63-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="56a63-112">설명</span><span class="sxs-lookup"><span data-stu-id="56a63-112">Description</span></span>  
 <span data-ttu-id="56a63-113">동작 추적에서 보내거나 받을 메시지가 동작 경계를 넘기 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="56a63-113">In activity tracing, indicates a message has started crossing an activity boundary in send or receive.</span></span>  
  
## <a name="message"></a><span data-ttu-id="56a63-114">메시지</span><span class="sxs-lookup"><span data-stu-id="56a63-114">Message</span></span>  
 <span data-ttu-id="56a63-115">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="56a63-115">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="56a63-116">설명</span><span class="sxs-lookup"><span data-stu-id="56a63-116">Details</span></span>  
  
|<span data-ttu-id="56a63-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="56a63-117">Data Item Name</span></span>|<span data-ttu-id="56a63-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="56a63-118">Data Item Type</span></span>|<span data-ttu-id="56a63-119">설명</span><span class="sxs-lookup"><span data-stu-id="56a63-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="56a63-120">ExtendedData</span><span class="sxs-lookup"><span data-stu-id="56a63-120">ExtendedData</span></span>|`xs:string`|<span data-ttu-id="56a63-121">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="56a63-121">The name of the activity.</span></span>|  
|<span data-ttu-id="56a63-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="56a63-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="56a63-123">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="56a63-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
