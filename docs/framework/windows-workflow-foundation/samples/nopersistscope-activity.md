---
title: NoPersistScope 활동
ms.date: 03/30/2017
ms.assetid: 9a0baeb7-a05c-4fac-b905-252758cb71bb
ms.openlocfilehash: 6543756594b6734aec39bf22c5ab6215605341b1
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2018
ms.locfileid: "45649551"
---
# <a name="nopersistscope-activity"></a><span data-ttu-id="ab370-102">NoPersistScope 활동</span><span class="sxs-lookup"><span data-stu-id="ab370-102">NoPersistScope Activity</span></span>
<span data-ttu-id="ab370-103">이 샘플에서는 워크플로 내의 serialize할 수 없고 삭제 가능한 상태를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab370-103">This sample shows how to manipulate a non-serializable and disposable state within a workflow.</span></span> <span data-ttu-id="ab370-104">이때 워크플로에서 serialize 불가능 상태를 지속하려고 시도하지 않는다는 점이 중요하며 삭제 가능한 개체를 워크플로에 사용하고 나면 이를 정리해야 한다는 점도 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="ab370-104">It is important that workflows do not attempt to persist non-serializable state and it is also important for disposable objects to be cleaned up after they are used in workflow.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="ab370-105">세부 항목</span><span class="sxs-lookup"><span data-stu-id="ab370-105">Demonstrates</span></span>  
 <span data-ttu-id="ab370-106">`NoPersistScope` 사용자 지정 활동 및 디자이너</span><span class="sxs-lookup"><span data-stu-id="ab370-106">`NoPersistScope` custom activity and designer.</span></span>  
  
## <a name="using-the-nopersistzone-activity"></a><span data-ttu-id="ab370-107">NoPersistZone 활동 사용</span><span class="sxs-lookup"><span data-stu-id="ab370-107">Using the NoPersistZone activity</span></span>  
 <span data-ttu-id="ab370-108">샘플 워크플로를 실행하면 `CreateTextWriter`라는 사용자 지정 활동을 통해 <xref:System.IO.TextWriter> 형식의 개체가 만들어지고 이 개체가 워크플로 변수에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab370-108">When the sample workflow runs, a custom activity called `CreateTextWriter` creates an object of type <xref:System.IO.TextWriter> and saves it into a workflow variable.</span></span> <span data-ttu-id="ab370-109"><xref:System.IO.TextWriter>가 <xref:System.IDisposable> 개체인 경우.</span><span class="sxs-lookup"><span data-stu-id="ab370-109"><xref:System.IO.TextWriter> is an <xref:System.IDisposable> object.</span></span> <span data-ttu-id="ab370-110">샘플이 실행되는 디렉터리의 'out.txt'라는 파일에 텍스트를 쓰도록 구성되어 있는 이 <xref:System.IO.TextWriter>는 <xref:System.Activities.Statements.WriteLine> 활동에 사용되며 사용자가 콘솔에 입력하는 모든 텍스트를 그대로 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ab370-110">This <xref:System.IO.TextWriter>, which is configured to write to a file named ‘out.txt’ in the directory in which the sample runs, is used by a <xref:System.Activities.Statements.WriteLine> activity as it echoes any text you type in at the console.</span></span>  
  
 <span data-ttu-id="ab370-111">이 echo 논리는 워크플로가 지속되지 않도록 하는 `NoPersistScope` 활동 내에서 실행됩니다. 이 활동의 코드도 이 샘플에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab370-111">The echo logic runs within a `NoPersistScope` activity (the code for which is also part of this sample), which prevents the workflow from being persisted.</span></span> <span data-ttu-id="ab370-112">입력 한 경우 `unload` 콘솔에서 호스트는 워크플로 인스턴스를 유지 하려고 하지만 워크플로 내에서 그대로 유지 되므로이 작업이 시간 초과 `NoPersistScope`입니다.</span><span class="sxs-lookup"><span data-stu-id="ab370-112">If you type in `unload` at the console, the host attempts to persist the workflow instance but this operation times out because the workflow remains within a `NoPersistScope`.</span></span> <span data-ttu-id="ab370-113">또한 이 워크플로에서는 `Dispose` 개체 사용을 마쳤을 때 <xref:System.IO.TextWriter>라는 사용자 지정 활동을 사용하여 이 개체를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="ab370-113">The workflow also utilizes a custom activity called `Dispose` to dispose the <xref:System.IO.TextWriter> object when the workflow is finished using it.</span></span> <span data-ttu-id="ab370-114">`Dispose` 활동은 Try 블록을 실행하는 동안 예외가 발생하더라도 문제 없이 실행되도록 하기 위해 <xref:System.Activities.Statements.TryCatch.Finally%2A> 변수가 선언된 <xref:System.Activities.Statements.TryCatch> 활동의 <xref:System.IO.TextWriter> 블록 내에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab370-114">The `Dispose` activity is placed within the <xref:System.Activities.Statements.TryCatch.Finally%2A> block of the <xref:System.Activities.Statements.TryCatch> activity in which the <xref:System.IO.TextWriter> variable is declared, to ensure that it runs even if an exception should occur during execution of the Try block.</span></span>  
  
 <span data-ttu-id="ab370-115">입력할 수 있습니다 `exit` 워크플로 인스턴스를 완료 하 고 프로그램을 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="ab370-115">You can type in `exit` to complete the workflow instance and exit the program.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="ab370-116">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="ab370-116">To run the sample</span></span>  
  
1.  <span data-ttu-id="ab370-117">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 NoPersistZone.sln 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ab370-117">Open the NoPersistZone.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="ab370-118">솔루션을 빌드하려면 CTRL + SHIFT + b 또는 선택 **솔루션 빌드** 에서 합니다 **빌드** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="ab370-118">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="ab370-119">빌드가 성공 되 면 f5 키를 누르거나 **디버깅 시작** 에서 합니다 **디버그** 메뉴 또는 CTRL + F5 키를 눌러 수도 있고 선택할 **디버깅 하지 않고 시작** 에서 **디버그** 메뉴 디버깅 하지 않고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab370-119">Once the build has succeeded, press F5 or select **Start Debugging** from the **Debug** menu alternatively, you can press CTRL+F5 or select **Start Without Debugging** from the **Debug** menu to run without debugging.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="ab370-120">정리하려면(옵션)</span><span class="sxs-lookup"><span data-stu-id="ab370-120">To cleanup (optional)</span></span>  
  
1.  <span data-ttu-id="ab370-121">SQL 인스턴스 저장소를 제거하려면 Cleanup.cmd를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab370-121">To remove the SQL Instance Store, run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ab370-122">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab370-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ab370-123">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ab370-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ab370-124">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="ab370-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ab370-125">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab370-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NoPersistScope`