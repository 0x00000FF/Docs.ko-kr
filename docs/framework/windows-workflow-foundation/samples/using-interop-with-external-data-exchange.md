---
title: 외부 데이터 교환과 함께 Interop 사용
ms.date: 03/30/2017
ms.assetid: 96f6fe26-5305-494f-9119-7748e0c4b3fa
ms.openlocfilehash: 534321e5b5568e0dd0988333dc98ccc18ff33df8
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2018
ms.locfileid: "45616314"
---
# <a name="using-interop-with-external-data-exchange"></a><span data-ttu-id="efaa0-102">외부 데이터 교환과 함께 Interop 사용</span><span class="sxs-lookup"><span data-stu-id="efaa0-102">Using Interop with External Data Exchange</span></span>
<span data-ttu-id="efaa0-103">합니다 <xref:System.Activities.Statements.Interop> 에서 Windows WF (Workflow Foundation)에서 작업을 실행 하려면 작업을 사용할 수 있습니다 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 하 고 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3)에서 Windows Workflow Foundation 워크플로 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4).</span><span class="sxs-lookup"><span data-stu-id="efaa0-103">The <xref:System.Activities.Statements.Interop> activity can be used to execute activities from Windows Workflow Foundation (WF) in [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] and [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3), and workflows within Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4).</span></span> <span data-ttu-id="efaa0-104">이 샘플에서는 WF4 워크플로 서비스의 <xref:System.Workflow.Activities.ExternalDataExchangeService> 활동을 사용하여 <xref:System.Activities.Statements.Interop> 및 메서드 호출과 이벤트 처리를 위한 해당 사용자 지정 활동을 사용하는 WF3 워크플로를 구성하고 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="efaa0-104">This sample shows how to configure and run a WF3 workflow that uses <xref:System.Workflow.Activities.ExternalDataExchangeService> (and corresponding custom activities for calling methods and handling events) by using the <xref:System.Activities.Statements.Interop> activity in a WF4 workflow service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="efaa0-105">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efaa0-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="efaa0-106">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="efaa0-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="efaa0-107">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="efaa0-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="efaa0-108">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efaa0-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\ExternalDataExchange`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="efaa0-109">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="efaa0-109">To use this sample</span></span>  
  
1.  <span data-ttu-id="efaa0-110">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 ExternalDataExchange.sln 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="efaa0-110">Open the ExternalDataExchange.sln file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="efaa0-111">Ctrl+Shift+B를 눌러 샘플을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="efaa0-111">To build the sample, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="efaa0-112">F5 키를 눌러 샘플을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="efaa0-112">To run the sample, press F5.</span></span>
