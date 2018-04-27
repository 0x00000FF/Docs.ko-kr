---
title: 외부 데이터 교환과 함께 Interop 사용
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96f6fe26-5305-494f-9119-7748e0c4b3fa
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4acec4209ddadd181774ae754cb1d6b94a21685e
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="using-interop-with-external-data-exchange"></a><span data-ttu-id="1d96a-102">외부 데이터 교환과 함께 Interop 사용</span><span class="sxs-lookup"><span data-stu-id="1d96a-102">Using Interop with External Data Exchange</span></span>
<span data-ttu-id="1d96a-103"><xref:System.Activities.Statements.Interop> 활동에서 Windows WF (Workflow Foundation)에서 실행할 작업을 사용할 수 있습니다 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 및 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3) 및 Windows Workflow Foundation의 내의 워크플로 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4).</span><span class="sxs-lookup"><span data-stu-id="1d96a-103">The <xref:System.Activities.Statements.Interop> activity can be used to execute activities from Windows Workflow Foundation (WF) in [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] and [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3), and workflows within Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4).</span></span> <span data-ttu-id="1d96a-104">이 샘플에서는 WF4 워크플로 서비스의 <xref:System.Workflow.Activities.ExternalDataExchangeService> 활동을 사용하여 <xref:System.Activities.Statements.Interop> 및 메서드 호출과 이벤트 처리를 위한 해당 사용자 지정 활동을 사용하는 WF3 워크플로를 구성하고 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d96a-104">This sample shows how to configure and run a WF3 workflow that uses <xref:System.Workflow.Activities.ExternalDataExchangeService> (and corresponding custom activities for calling methods and handling events) by using the <xref:System.Activities.Statements.Interop> activity in a WF4 workflow service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1d96a-105">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d96a-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1d96a-106">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1d96a-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1d96a-107">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="1d96a-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1d96a-108">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d96a-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\ExternalDataExchange`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="1d96a-109">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="1d96a-109">To use this sample</span></span>  
  
1.  <span data-ttu-id="1d96a-110">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 ExternalDataExchange.sln 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1d96a-110">Open the ExternalDataExchange.sln file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="1d96a-111">Ctrl+Shift+B를 눌러 샘플을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1d96a-111">To build the sample, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="1d96a-112">F5 키를 눌러 샘플을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1d96a-112">To run the sample, press F5.</span></span>
