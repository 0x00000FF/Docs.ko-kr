---
title: LINQ 메시지 쿼리 상관 관계
ms.date: 03/30/2017
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
ms.openlocfilehash: 7881140f2926bc27073a0be425a63566f313b50c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43393750"
---
# <a name="linq-message-query-correlation"></a><span data-ttu-id="8c0f3-102">LINQ 메시지 쿼리 상관 관계</span><span class="sxs-lookup"><span data-stu-id="8c0f3-102">LINQ Message Query Correlation</span></span>
<span data-ttu-id="8c0f3-103">이 샘플에서는 시스템에서 제공하는 <xref:System.ServiceModel.Dispatcher.MessageQuery> 대신 사용자 지정 <xref:System.ServiceModel.XPathMessageQuery> 구현을 사용하여 내용 기반 상관 관계를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c0f3-103">This sample demonstrates how to do content-based correlation using a custom <xref:System.ServiceModel.Dispatcher.MessageQuery> implementation as opposed to the system-provided <xref:System.ServiceModel.XPathMessageQuery>.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="8c0f3-104">세부 항목</span><span class="sxs-lookup"><span data-stu-id="8c0f3-104">Demonstrates</span></span>  
 <span data-ttu-id="8c0f3-105">사용자 지정 <xref:System.ServiceModel.Dispatcher.MessageQuery>, 내용 기반 상관 관계</span><span class="sxs-lookup"><span data-stu-id="8c0f3-105">Custom <xref:System.ServiceModel.Dispatcher.MessageQuery>, Content-Based Correlation.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="8c0f3-106">토론</span><span class="sxs-lookup"><span data-stu-id="8c0f3-106">Discussion</span></span>  
 <span data-ttu-id="8c0f3-107">이 샘플에서는 상관 관계를 만들기 위해 <xref:System.ServiceModel.Dispatcher.MessageQuery> 기본 클래스를 확장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c0f3-107">This sample shows how to extend from the <xref:System.ServiceModel.Dispatcher.MessageQuery> base class for the purposes of correlation.</span></span> <span data-ttu-id="8c0f3-108">사용자 지정 `LinqMessageQuery`를 구현하면 XLinq를 사용하여 메시지 내에서 XName을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0f3-108">The custom implementation, `LinqMessageQuery`, allows users to provide an XName to find within the message using XLinq.</span></span> <span data-ttu-id="8c0f3-109">쿼리를 통해 검색한 데이터는 메시지를 적절한 워크플로 인스턴스로 디스패치하기 위한 상관 관계 키를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0f3-109">The data retrieved by the query is used to form the correlation key to dispatch messages to the appropriate workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8c0f3-110">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="8c0f3-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8c0f3-111">이 샘플에서는 HTTP 엔드포인트를 사용하여 워크플로 서비스를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0f3-111">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="8c0f3-112">이 샘플을 적절 한 URL Acl을 실행 하려면 추가 되어야 합니다 (참조 [HTTP 및 HTTPS 구성](https://go.microsoft.com/fwlink/?LinkId=70353) 세부 정보에 대 한), 관리자 권한으로 Visual Studio를 실행 하거나 적절 한 Acl을 추가 하려면 관리자 권한 프롬프트에서 다음 명령을 실행 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0f3-112">To run this sample, proper URL ACLs must be added (see [Configuring HTTP and HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) for details), either by running Visual Studio as Administrator or by executing the following command at an elevated prompt to add the appropriate ACLs.</span></span> <span data-ttu-id="8c0f3-113">도메인과 사용자 이름이 대체되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0f3-113">Ensure that your Domain and Username are substituted.</span></span>  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2.  <span data-ttu-id="8c0f3-114">URL ACL이 추가되었으면 다음 단계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0f3-114">Once the URL ACLs are added, use the following steps.</span></span>  
  
    1.  <span data-ttu-id="8c0f3-115">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0f3-115">Build the solution.</span></span>  
  
    2.  <span data-ttu-id="8c0f3-116">솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 여러 개의 시작 프로젝트 설정 **시작 프로젝트 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0f3-116">Set multiple start-up projects by right-clicking the solution and selecting **Set Startup Projects**.</span></span> <span data-ttu-id="8c0f3-117">추가 **서비스** 하 고 **클라이언트** (해당 순서) 대로 여러 시작 프로젝트로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0f3-117">Add **Service** and **Client** (in that order) as multiple start-up projects.</span></span>  
  
    3.  <span data-ttu-id="8c0f3-118">응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0f3-118">Run the application.</span></span> <span data-ttu-id="8c0f3-119">주문서를 보내고 구매 주문서 ID를 받은 다음 주문을 확인하는 워크플로가 클라이언트 콘솔에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0f3-119">The client console shows a workflow  sending an order and receiving the purchase order id and then subsequently confirming the order.</span></span> <span data-ttu-id="8c0f3-120">처리 중인 요청이 서비스 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0f3-120">The Service window will show the requests being processed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8c0f3-121">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0f3-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8c0f3-122">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="8c0f3-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8c0f3-123">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="8c0f3-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8c0f3-124">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0f3-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
