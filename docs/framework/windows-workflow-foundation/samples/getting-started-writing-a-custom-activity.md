---
title: "사용자 지정 활동 작성 시작"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3902f5fa-8a43-4048-8a6a-6b15472f90f0
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 495cad6d672fd550024cc872bd3cff586326ccbc
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="getting-started-writing-a-custom-activity"></a><span data-ttu-id="fe75b-102">사용자 지정 활동 작성 시작</span><span class="sxs-lookup"><span data-stu-id="fe75b-102">Getting Started Writing a Custom Activity</span></span>
<span data-ttu-id="fe75b-103">이 샘플에서는 간단한 사용자 지정 활동을 XAML로 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fe75b-103">This sample demonstrates how to define a simple custom activity in XAML.</span></span> <span data-ttu-id="fe75b-104">활동에는 `Rhyme`이라는 이름이 지정되고 활동의 논리는 세 <xref:System.Activities.Statements.WriteLine> 활동으로 구성된 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="fe75b-104">The activity is given the name `Rhyme`, and its logic is a sequence of three <xref:System.Activities.Statements.WriteLine> activities.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fe75b-105">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="fe75b-105">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="fe75b-106">열기는 **Simple.sln** 샘플 솔루션을 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="fe75b-106">Open the **Simple.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="fe75b-107">솔루션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fe75b-107">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fe75b-108">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe75b-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fe75b-109">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="fe75b-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fe75b-110">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="fe75b-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fe75b-111">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe75b-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\GettingStarted`