---
title: "RangeEnumeration 활동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca5b78f4-94fa-4aa7-830d-26039ac422c8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7dc793d57718dbc68f304d3eb5031a9fa96b00cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="rangeenumeration-activity"></a><span data-ttu-id="d7a96-102">RangeEnumeration 활동</span><span class="sxs-lookup"><span data-stu-id="d7a96-102">RangeEnumeration Activity</span></span>
<span data-ttu-id="d7a96-103">이 샘플에서는 숫자 컬렉션을 반복하는 사용자 지정 활동을 만드는 방법을 보여 줍니다. 다음 표에는 이 샘플에 포함된 주요 파일에 대한 세부 사항이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a96-103">This sample demonstrates how to create a custom activity that iterates over a collection of numbers.The following table details the main files included in the sample.</span></span>  
  
|<span data-ttu-id="d7a96-104">파일 이름</span><span class="sxs-lookup"><span data-stu-id="d7a96-104">File name</span></span>|<span data-ttu-id="d7a96-105">설명</span><span class="sxs-lookup"><span data-stu-id="d7a96-105">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d7a96-106">RangeEnumeration.cs</span><span class="sxs-lookup"><span data-stu-id="d7a96-106">RangeEnumeration.cs</span></span>|<span data-ttu-id="d7a96-107">`RangeEnumeration` 클래스를 재정의하고 일련의 숫자를 반복하는 <xref:System.Activities.NativeActivity>이라는 사용자 지정 활동을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a96-107">Defines a custom activity named `RangeEnumeration` that overrides the <xref:System.Activities.NativeActivity> class and loops through a series of numbers.</span></span>|  
|<span data-ttu-id="d7a96-108">RangeEnumerationSample.cs</span><span class="sxs-lookup"><span data-stu-id="d7a96-108">RangeEnumerationSample.cs</span></span>|<span data-ttu-id="d7a96-109">`RangeEnumeration` 활동을 사용하여 숫자 컬렉션을 반복하는 클라이언트 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a96-109">A client application that uses the `RangeEnumeration` activity to iterate over a collection of numbers.</span></span>|  
  
 <span data-ttu-id="d7a96-110">다음 표에는 `RangeEnumeration` 활동의 속성에 대한 자세한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a96-110">The following table details the properties of the `RangeEnumeration` activity.</span></span>  
  
|<span data-ttu-id="d7a96-111">속성</span><span class="sxs-lookup"><span data-stu-id="d7a96-111">Property</span></span>|<span data-ttu-id="d7a96-112">설명</span><span class="sxs-lookup"><span data-stu-id="d7a96-112">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="d7a96-113">시작</span><span class="sxs-lookup"><span data-stu-id="d7a96-113">Start</span></span>|<span data-ttu-id="d7a96-114">루프를 시작할 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a96-114">The integer to start the loop from.</span></span>|  
|<span data-ttu-id="d7a96-115">중지</span><span class="sxs-lookup"><span data-stu-id="d7a96-115">Stop</span></span>|<span data-ttu-id="d7a96-116">루프를 중지할 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a96-116">The integer to stop the loop at.</span></span>|  
|<span data-ttu-id="d7a96-117">단계</span><span class="sxs-lookup"><span data-stu-id="d7a96-117">Step</span></span>|<span data-ttu-id="d7a96-118">반복 과정에서 매번 얼마나 진행할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a96-118">Specifies how much to iterate each time.</span></span>|  
|<span data-ttu-id="d7a96-119">Body</span><span class="sxs-lookup"><span data-stu-id="d7a96-119">Body</span></span>|<span data-ttu-id="d7a96-120">각 반복 과정에서 실행할 코드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a96-120">Specifies the code to execute during each iteration.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="d7a96-121">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="d7a96-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="d7a96-122">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 RangeEnumeration.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d7a96-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RangeEnumeration.sln solution file.</span></span>  
  
2.  <span data-ttu-id="d7a96-123">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a96-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="d7a96-124">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a96-124">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d7a96-125">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a96-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d7a96-126">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d7a96-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d7a96-127">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="d7a96-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d7a96-128">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a96-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\RangeEnumeration`