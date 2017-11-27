---
title: "사용자 지정 보정 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 385920da-9284-44bf-9fe9-0d87c7478ec5
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c3a9745c0cdd3a2d7050aed083d2eee5dfd4aaaf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="custom-compensation-sample"></a><span data-ttu-id="b4079-102">사용자 지정 보정 샘플</span><span class="sxs-lookup"><span data-stu-id="b4079-102">Custom Compensation Sample</span></span>
<span data-ttu-id="b4079-103">이 샘플에서는 <xref:System.Activities.Statements.CompensableActivity>와 해당 보정 처리기를 사용하여 사용자 지정 보정 논리를 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-103">This sample shows how to use <xref:System.Activities.Statements.CompensableActivity> and its compensation handler to define custom compensation logic.</span></span> <span data-ttu-id="b4079-104">이 샘플에서 모델링하는 시나리오는 트럭 렌탈 대행사입니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-104">The scenario modeled in this sample is a Truck Rental Agency.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="b4079-105">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="b4079-105">Sample Details</span></span>  
 <span data-ttu-id="b4079-106">시뮬레이션하는 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-106">The steps simulated are:</span></span>  
  
1.  <span data-ttu-id="b4079-107">사용자가 지정된 날짜에 대한 트럭 렌탈 가격 견적을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-107">The user requests truck rental quotes for a given date.</span></span>  
  
2.  <span data-ttu-id="b4079-108">세 개의 트럭 회사에 연락하여 세 개의 견적 가격을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-108">Three truck companies are contacted and the three quotes are provided.</span></span>  
  
3.  <span data-ttu-id="b4079-109">사용자는 하나의 트럭 견적 가격을 선택하고 신용 카드로 주문합니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-109">The user selects one truck quote and proceeds to order by credit card.</span></span>  
  
4.  <span data-ttu-id="b4079-110">응용 프로그램은 나머지 두 개의 트럭 가격 견적을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-110">The application cancels the other two truck quotes.</span></span>  
  
5.  <span data-ttu-id="b4079-111">응용 프로그램은 예약 날짜 10일 전까지 취소할 경우 프리미엄 계좌가 아닌 일반 계좌의 경우 환불되지 않는 서비스 요금을 청구합니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-111">The application charges a service fee that is non-refundable for non-premium accounts if cancelation happens 10 days or less prior to the reservation date.</span></span>  
  
6.  <span data-ttu-id="b4079-112">응용 프로그램은 트럭 렌탈 요금을 청구합니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-112">The application charges the truck rental fee.</span></span>  
  
7.  <span data-ttu-id="b4079-113">응용 프로그램은 예약 날짜와 고객이 예약을 취소하기로 결정한 날짜 중 빠른 날짜까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-113">The application waits until the reservation date or until the customer decided to cancel the reservation, whichever comes first.</span></span>  
  
8.  <span data-ttu-id="b4079-114">고객이 예약을 취소하는 경우 <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> 사용자 지정 보정 논리는 다음 논리에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-114">If the customer cancels the reservation, the <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> custom compensation logic runs according to the following logic:</span></span>  
  
    1.  <span data-ttu-id="b4079-115">고객의 계좌가 프리미엄 계좌가 아니고 현재 시점부터 예약 날짜까지 남은 날짜가 10일 미만인 경우 서비스 요금이 청구되며, 이외의 경우에는 응용 프로그램이 서비스 요금을 환불합니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-115">If the customer has a non-premium account and it is less than 10 days prior to the reservation date, then the service fee is still charged; otherwise, the application refunds the service fee.</span></span>  
  
    2.  <span data-ttu-id="b4079-116">나머지 보정 가능한 활동(트럭 주문 + 트럭 주문 요금)은 실행 순서의 반대로 보정하는 기본 보정 논리에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-116">The rest of the compensable activities (truck order + truck order fee) are run according to the default compensation logic, which is to compensate in reverse order of execution.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b4079-117">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="b4079-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b4079-118">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 CustomCompensation.sln 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-118">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CustomCompensation.sln solution.</span></span> <span data-ttu-id="b4079-119">솔루션은 \WF\Basic\Compensation\CustomCompensation 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-119">It is located in the \WF\Basic\Compensation\CustomCompensation directory.</span></span>  
  
2.  <span data-ttu-id="b4079-120">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-120">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="b4079-121">Ctrl+F5를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-121">Press CTRL + F5 to run the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b4079-122">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b4079-123">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b4079-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b4079-124">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="b4079-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b4079-125">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4079-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CustomCompensation`  
  
## <a name="see-also"></a><span data-ttu-id="b4079-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4079-126">See Also</span></span>
