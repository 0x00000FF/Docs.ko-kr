---
title: Bookmarks2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 035fadb2-49fa-4ac7-b398-daf138f66e87
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d3a1e0a966fcd5d89cc30456b46a11ae7d54731e
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="bookmarks"></a><span data-ttu-id="42ddc-102">책갈피</span><span class="sxs-lookup"><span data-stu-id="42ddc-102">Bookmarks</span></span>
<span data-ttu-id="42ddc-103">이 샘플에서는 책갈피를 만들어 외부 입력을 받는 사용자 지정 활동을 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="42ddc-103">This sample demonstrates how to write a custom activity that creates a bookmark to receive external input.</span></span> <span data-ttu-id="42ddc-104">이 샘플에는 워크플로에서 사용자 지정 활동을 사용하며 실행 중인 워크플로 인스턴스와 연결된 책갈피를 검색하고 다시 시작하는 방법을 보여 주는 기본적인 콘솔 응용 프로그램도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ddc-104">The sample also includes a basic console application that uses the custom activity in a workflow and shows how to discover and resume bookmarks associated with a running workflow instance.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="42ddc-105">책갈피, 참조 [책갈피](../../../../docs/framework/windows-workflow-foundation/bookmarks.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="42ddc-105"> bookmarks, see [Bookmarks](../../../../docs/framework/windows-workflow-foundation/bookmarks.md).</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="42ddc-106">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="42ddc-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="42ddc-107">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 Bookmarks.sln 샘플 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="42ddc-107">Open the Bookmarks.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="42ddc-108">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="42ddc-108">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="42ddc-109">Ctrl+F5를 눌러 샘플을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="42ddc-109">To run the sample, press CTRLl + F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="42ddc-110">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ddc-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="42ddc-111">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="42ddc-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="42ddc-112">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="42ddc-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="42ddc-113">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ddc-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CodeBodied\Bookmarks`