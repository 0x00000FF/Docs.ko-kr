---
title: '방법: 사용자 지정 추적 참가자 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b612c7e-2381-4a7c-b07a-77030415f2a3
ms.openlocfilehash: c4c6a8d17180ee00942c1bfd9ddc7bfa04bb962f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720958"
---
# <a name="how-to-create-a-custom-tracking-participant"></a><span data-ttu-id="16ade-102">방법: 사용자 지정 추적 참가자 만들기</span><span class="sxs-lookup"><span data-stu-id="16ade-102">How to: Create a Custom Tracking Participant</span></span>
<span data-ttu-id="16ade-103">워크플로 추적을 통해 워크플로 실행 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-103">Workflow tracking provides visibility into the status of workflow execution.</span></span> <span data-ttu-id="16ade-104">워크플로 런타임은 워크플로 수명 주기 이벤트, 활동 수명 주기 이벤트, 책갈피 다시 시작 및 오류를 설명하는 추적 레코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-104">The workflow runtime emits tracking records that describe workflow lifecycle events, activity lifecycle events, bookmark resumptions, and faults.</span></span> <span data-ttu-id="16ade-105">이러한 추적 레코드는 추적 참가자에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-105">These tracking records are consumed by tracking participants.</span></span> <span data-ttu-id="16ade-106">Windows WF (Workflow Foundation) 추적 레코드 이벤트 추적에 대 한 Windows (ETW) 이벤트로 기록 하는 표준 추적 참가자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-106">Windows Workflow Foundation (WF) includes a standard tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span> <span data-ttu-id="16ade-107">표준 참가자가 요구 사항에 맞지 않는 경우 사용자 지정 추적 참가자를 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-107">If that does not meet your requirements, you can also write a custom tracking participant.</span></span> <span data-ttu-id="16ade-108">이 자습서 단계에서는 `WriteLine` 활동의 출력을 캡처하여 사용자에게 표시될 수 있도록 하는 추적 프로필 및 사용자 지정 추적 참가자를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-108">This tutorial step describes how to create a custom tracking participant and tracking profile that capture the output of `WriteLine` activities so that they can be displayed to the user.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16ade-109">초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-109">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="16ade-110">이 항목을 진행하려면 먼저 이전 항목을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-110">To complete this topic, you must first complete the previous topics.</span></span> <span data-ttu-id="16ade-111">완료 된 버전을 다운로드 하거나이 자습서의 비디오 연습을 보려면을 참조 하세요 [Windows Workflow Foundation(wf45 ()-초보자를 위한 자습서](https://go.microsoft.com/fwlink/?LinkID=248976)합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-111">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="to-create-the-custom-tracking-participant"></a><span data-ttu-id="16ade-112">사용자 지정 추적 참가자를 만들려면</span><span class="sxs-lookup"><span data-stu-id="16ade-112">To create the custom tracking participant</span></span>  
  
1.  <span data-ttu-id="16ade-113">마우스 오른쪽 단추로 클릭 **NumberGuessWorkflowHost** 에서 **솔루션 탐색기** 선택한 **추가**하십시오 **클래스**합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-113">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Class**.</span></span> <span data-ttu-id="16ade-114">형식 `StatusTrackingParticipant` 에 **이름** 상자를 선택한 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-114">Type `StatusTrackingParticipant` into the **Name** box, and click **Add**.</span></span>  
  
2.  <span data-ttu-id="16ade-115">다음 `using`(또는 `Imports`) 문을 파일의 맨 위에 다른 `using`(또는 `Imports`) 문과 함께 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-115">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Activities.Tracking  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    using System.IO;  
    ```  
  
3.  <span data-ttu-id="16ade-116">`StatusTrackingParticipant`에서 상속하도록 `TrackingParticipant` 클래스를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-116">Modify the `StatusTrackingParticipant` class so that it inherits from `TrackingParticipant`.</span></span>  
  
    ```vb  
    Public Class StatusTrackingParticipant  
        Inherits TrackingParticipant  
  
    End Class  
    ```  
  
    ```csharp  
    class StatusTrackingParticipant : TrackingParticipant  
    {  
    }  
    ```  
  
4.  <span data-ttu-id="16ade-117">다음 `Track` 메서드 재정의를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-117">Add the following `Track` method override.</span></span> <span data-ttu-id="16ade-118">추적 레코드에는 여러 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-118">There are several different types of tracking records.</span></span> <span data-ttu-id="16ade-119">여기서는 활동 추적 레코드에 포함된 `WriteLine` 활동의 출력에 초점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-119">We are interested in the output of `WriteLine` activities, which are contained in activity tracking records.</span></span> <span data-ttu-id="16ade-120">`TrackingRecord`가 `ActivityTrackingRecord` 활동에 대한 `WriteLine`인 경우 `Text`의 `WriteLine`는 워크플로의 `InstanceId`에 따라 이름이 지정된 파일에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-120">If the `TrackingRecord` is an `ActivityTrackingRecord` for a `WriteLine` activity, the `Text` of the `WriteLine` is appended to a file named after the `InstanceId` of the workflow.</span></span> <span data-ttu-id="16ade-121">이 자습서에서는 파일이 호스트 응용 프로그램의 현재 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-121">In this tutorial, the file is saved to the current folder of the host application.</span></span>  
  
    ```vb  
    Protected Overrides Sub Track(record As TrackingRecord, timeout As TimeSpan)  
        Dim asr As ActivityStateRecord = TryCast(record, ActivityStateRecord)  
  
        If Not asr Is Nothing Then  
            If asr.State = ActivityStates.Executing And _  
            asr.Activity.TypeName = "System.Activities.Statements.WriteLine" Then  
  
                'Append the WriteLine output to the tracking  
                'file for this instance.  
                Using writer As StreamWriter = File.AppendText(record.InstanceId.ToString())  
                    writer.WriteLine(asr.Arguments("Text"))  
                    writer.Close()  
                End Using  
            End If  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    protected override void Track(TrackingRecord record, TimeSpan timeout)  
    {  
        ActivityStateRecord asr = record as ActivityStateRecord;  
  
        if (asr != null)  
        {  
            if (asr.State == ActivityStates.Executing &&  
                asr.Activity.TypeName == "System.Activities.Statements.WriteLine")  
            {  
                // Append the WriteLine output to the tracking  
                // file for this instance  
                using (StreamWriter writer = File.AppendText(record.InstanceId.ToString()))  
                {  
                    writer.WriteLine(asr.Arguments["Text"]);  
                    writer.Close();  
                }  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="16ade-122">추적 프로필이 지정되어 있지 않은 경우 기본 추적 프로필이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-122">When no tracking profile is specified, the default tracking profile is used.</span></span> <span data-ttu-id="16ade-123">기본 추적 프로필이 사용될 경우 모든 `ActivityStates`에 대해 추적 레코드가 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-123">When the default tracking profile is used, tracking records are emitted for all `ActivityStates`.</span></span> <span data-ttu-id="16ade-124">여기서는 `WriteLine` 활동의 수명 주기 동안 텍스트를 한 번만 캡처하면 되므로 `ActivityStates.Executing` 상태의 텍스트만 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-124">Because we only need to capture the text one time during the lifecycle of the `WriteLine` activity, we only extract the text from the `ActivityStates.Executing` state.</span></span> <span data-ttu-id="16ade-125">[추적 프로필을 만들고 추적 참가자를 등록 하](#to-create-the-tracking-profile-and-register-the-tracking-participant)를 지정 하는 추적 프로필 생성 됩니다 `WriteLine` `ActivityStates.Executing` 추적 레코드가 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-125">In [To create the tracking profile and register the tracking participant](#to-create-the-tracking-profile-and-register-the-tracking-participant), a tracking profile is created that specifies that only `WriteLine` `ActivityStates.Executing` tracking records are emitted.</span></span>  
  
## <a name="to-create-the-tracking-profile-and-register-the-tracking-participant"></a><span data-ttu-id="16ade-126">추적 프로필을 만들고 추적 참가자를 등록하려면</span><span class="sxs-lookup"><span data-stu-id="16ade-126">To create the tracking profile and register the tracking participant</span></span>  
  
1.  <span data-ttu-id="16ade-127">마우스 오른쪽 단추로 클릭 **WorkflowHostForm** 에 **솔루션 탐색기** 선택한 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-127">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="16ade-128">다음 `using`(또는 `Imports`) 문을 파일의 맨 위에 다른 `using`(또는 `Imports`) 문과 함께 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-128">Add the following `using` (or `Imports`) statement at the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Activities.Tracking  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    ```  
  
3.  <span data-ttu-id="16ade-129">워크플로 확장에 `ConfigureWorkflowApplication`를 추가하는 코드 바로 뒤와 워크플로 수명 주기 처리기 앞의 `StringWriter`에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-129">Add the following code to `ConfigureWorkflowApplication` just after the code that adds the `StringWriter` to the workflow extensions and before the workflow lifecycle handlers.</span></span>  
  
    ```vb  
    'Add the custom tracking participant with a tracking profile  
    'that only emits tracking records for WriteLine activities.  
    Dim query As New ActivityStateQuery()  
    query.ActivityName = "WriteLine"  
    query.States.Add(ActivityStates.Executing)  
    query.Arguments.Add("Text")  
  
    Dim profile As New TrackingProfile()  
    profile.Queries.Add(query)  
  
    Dim stp As New StatusTrackingParticipant()  
    stp.TrackingProfile = profile  
  
    wfApp.Extensions.Add(stp)  
    ```  
  
    ```csharp  
    // Add the custom tracking participant with a tracking profile  
    // that only emits tracking records for WriteLine activities.  
    StatusTrackingParticipant stp = new StatusTrackingParticipant  
    {  
        TrackingProfile = new TrackingProfile  
        {  
            Queries =   
            {  
                new ActivityStateQuery  
                {  
                    ActivityName = "WriteLine",  
                    States = { ActivityStates.Executing },  
                    Arguments = { "Text" }  
                }  
            }  
        }  
    };  
  
    wfApp.Extensions.Add(stp);  
    ```  
  
     <span data-ttu-id="16ade-130">이 추적 프로필은 `WriteLine` 상태의 `Executing` 활동에 대한 활동 상태 레코드만 사용자 지정 추적 참가자로 내보내도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-130">This tracking profile specifies that only activity state records for `WriteLine` activities in the `Executing` state are emitted to the custom tracking participant.</span></span>  
  
     <span data-ttu-id="16ade-131">코드를 추가한 후 `ConfigureWorkflowApplication`의 시작 부분은 다음 예제와 같게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-131">After adding the code, the start of `ConfigureWorkflowApplication` will look like the following example.</span></span>  
  
    ```vb  
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)  
        'Configure the persistence store.  
        wfApp.InstanceStore = store  
  
        'Add a StringWriter to the extensions. This captures the output  
        'from the WriteLine activities so we can display it in the form.  
        Dim sw As New StringWriter()  
        wfApp.Extensions.Add(sw)  
  
        'Add the custom tracking participant with a tracking profile  
        'that only emits tracking records for WriteLine activities.  
        Dim query As New ActivityStateQuery()  
        query.ActivityName = "WriteLine"  
        query.States.Add(ActivityStates.Executing)  
        query.Arguments.Add("Text")  
  
        Dim profile As New TrackingProfile()  
        profile.Queries.Add(query)  
  
        Dim stp As New StatusTrackingParticipant()  
        stp.TrackingProfile = profile  
  
        wfApp.Extensions.Add(stp)  
  
        'Workflow lifecycle handlers...  
    ```  
  
    ```csharp  
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)  
    {  
        // Configure the persistence store.  
        wfApp.InstanceStore = store;  
  
        // Add a StringWriter to the extensions. This captures the output  
        // from the WriteLine activities so we can display it in the form.  
        StringWriter sw = new StringWriter();  
        wfApp.Extensions.Add(sw);  
  
        // Add the custom tracking participant with a tracking profile  
        // that only emits tracking records for WriteLine activities.  
        StatusTrackingParticipant stp = new StatusTrackingParticipant  
        {  
            TrackingProfile = new TrackingProfile  
            {  
                Queries =   
                {  
                    new ActivityStateQuery  
                    {  
                        ActivityName = "WriteLine",  
                        States = { ActivityStates.Executing },  
                        Arguments = { "Text" }  
                    }  
                }  
            }  
        };  
  
        wfApp.Extensions.Add(stp);  
  
        // Workflow lifecycle handlers...  
    ```  
  
## <a name="to-display-the-tracking-information"></a><span data-ttu-id="16ade-132">추적 정보를 표시하려면</span><span class="sxs-lookup"><span data-stu-id="16ade-132">To display the tracking information</span></span>  
  
1.  <span data-ttu-id="16ade-133">마우스 오른쪽 단추로 클릭 **WorkflowHostForm** 에 **솔루션 탐색기** 선택한 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-133">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="16ade-134">`InstanceId_SelectedIndexChanged` 처리기에서 상태 창을 지우는 코드 바로 뒤에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-134">In the `InstanceId_SelectedIndexChanged` handler, add the following code immediately after the code that clears the status window.</span></span>  
  
    ```vb  
    'If there is tracking data for this workflow, display it  
    'in the status window.  
    If File.Exists(WorkflowInstanceId.ToString()) Then  
        Dim status As String = File.ReadAllText(WorkflowInstanceId.ToString())  
        UpdateStatus(status)  
    End If  
    ```  
  
    ```csharp  
    // If there is tracking data for this workflow, display it  
    // in the status window.  
    if (File.Exists(WorkflowInstanceId.ToString()))  
    {  
        string status = File.ReadAllText(WorkflowInstanceId.ToString());  
        UpdateStatus(status);  
    }  
    ```  
  
     <span data-ttu-id="16ade-135">워크플로 목록에 새 워크플로가 선택된 경우 해당 워크플로에 대한 추적 레코드가 로드되어 상태 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-135">When a new workflow is selected in the workflow list, the tracking records for that workflow are loaded and displayed in the status window.</span></span> <span data-ttu-id="16ade-136">다음 예제는 전체 `InstanceId_SelectedIndexChanged` 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-136">The following example is the completed `InstanceId_SelectedIndexChanged` handler.</span></span>  
  
    ```vb  
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged  
        If InstanceId.SelectedIndex = -1 Then  
            Return  
        End If  
  
        'Clear the status window.  
        WorkflowStatus.Clear()  
  
        'If there is tracking data for this workflow, display it  
        'in the status window.  
        If File.Exists(WorkflowInstanceId.ToString()) Then  
            Dim status As String = File.ReadAllText(WorkflowInstanceId.ToString())  
            UpdateStatus(status)  
        End If  
  
        'Get the workflow version and display it.  
        'If the workflow is just starting then this info will not  
        'be available in the persistence store so do not try and retrieve it.  
        If Not WorkflowStarting Then  
            Dim instance As WorkflowApplicationInstance = _  
                WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
            WorkflowVersion.Text = _  
                WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity)  
  
            'Unload the instance.  
            instance.Abandon()  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)  
    {  
        if (InstanceId.SelectedIndex == -1)  
        {  
            return;  
        }  
  
        // Clear the status window.  
        WorkflowStatus.Clear();  
  
        // If there is tracking data for this workflow, display it  
        // in the status window.  
        if (File.Exists(WorkflowInstanceId.ToString()))  
        {  
            string status = File.ReadAllText(WorkflowInstanceId.ToString());  
            UpdateStatus(status);  
        }  
  
        // Get the workflow version and display it.  
        // If the workflow is just starting then this info will not  
        // be available in the persistence store so do not try and retrieve it.  
        if (!WorkflowStarting)  
        {  
            WorkflowApplicationInstance instance =  
                WorkflowApplication.GetInstance(this.WorkflowInstanceId, store);  
  
            WorkflowVersion.Text =  
                WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity);  
  
            // Unload the instance.  
            instance.Abandon();  
        }  
    }  
    ```  
  
## <a name="to-build-and-run-the-application"></a><span data-ttu-id="16ade-137">애플리케이션을 빌드하고 실행하려면</span><span class="sxs-lookup"><span data-stu-id="16ade-137">To build and run the application</span></span>  
  
1.  <span data-ttu-id="16ade-138">Ctrl+Shift+B를 눌러 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-138">Press Ctrl+Shift+B to build the application.</span></span>  
  
2.  <span data-ttu-id="16ade-139">Ctrl+F5를 눌러 응용 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-139">Press Ctrl+F5 to start the application.</span></span>  
  
3.  <span data-ttu-id="16ade-140">추측 게임 및 시작을 클릭 하는 워크플로 유형에 대 한 범위를 선택할 **New Game**합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-140">Select a range for the guessing game and the type of workflow to start, and click **New Game**.</span></span> <span data-ttu-id="16ade-141">추측 값을 입력 합니다 **추측** 상자 하 고 클릭 **이동** 에 추측을 제출 하려면.</span><span class="sxs-lookup"><span data-stu-id="16ade-141">Enter a guess in the **Guess** box and click **Go** to submit your guess.</span></span> <span data-ttu-id="16ade-142">워크플로의 상태가 상태 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-142">Note that the status of the workflow is displayed in the status window.</span></span> <span data-ttu-id="16ade-143">이 출력은 `WriteLine` 활동에서 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-143">This output is captured from the `WriteLine` activities.</span></span> <span data-ttu-id="16ade-144">하나를 선택 하 여 다른 워크플로로 전환 합니다 **워크플로 인스턴스 Id** 콤보 상자 및 현재 워크플로의 상태가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-144">Switch to a different workflow by selecting one from the **Workflow Instance Id** combo box and note that the status of the current workflow is removed.</span></span> <span data-ttu-id="16ade-145">다시 이전 워크플로로 전환하고 상태가 다음 예제와 같이 복원되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-145">Switch back to the previous workflow and note that the status is restored, similar to the following example.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="16ade-146">추적을 사용하도록 설정하기 전에 시작된 워크플로로 전환할 경우에는 상태가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-146">If you switch to a workflow that was started before tracking was enabled no status is displayed.</span></span> <span data-ttu-id="16ade-147">그러나 추가로 숫자를 추측한 경우에는 이제 추적을 사용하도록 설정되었으므로 해당 상태가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-147">However if you make additional guesses, their status is saved because tracking is now enabled.</span></span>  
  
    ```output
    Please enter a number between 1 and 10
    Your guess is too high.
    Please enter a number between 1 and 10
    ```
    
    > [!NOTE]
    > <span data-ttu-id="16ade-148">이 정보는 난수의 범위를 결정하는 데 유용하지만 이전에 추측한 값에 대한 정보는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-148">This information is useful for determining the range of the random number, but it does not contain any information about what guesses have been previously made.</span></span> <span data-ttu-id="16ade-149">이 정보는 다음 단계에서 [방법: 여러 버전을 워크플로-Side-by-side의 호스트](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-149">This information is in the next step, [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

    <span data-ttu-id="16ade-150">워크플로 인스턴스 ID를 적어 두고 게임을 완료될 때까지 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-150">Make a note of the workflow instance id, and play the game through to its completion.</span></span>
  
4.  <span data-ttu-id="16ade-151">Windows 탐색기를 열고로 이동 합니다 **NumberGuessWorkflowHost\bin\debug** 폴더 (또는 **bin\release** 프로젝트 설정에 따라).</span><span class="sxs-lookup"><span data-stu-id="16ade-151">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings).</span></span> <span data-ttu-id="16ade-152">이 폴더에는 프로젝트 실행 파일 뿐만 아니라 GUID 파일 이름을 가진 파일도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-152">Note that in addition to the project executable files there are files with guid filenames.</span></span> <span data-ttu-id="16ade-153">이전 단계에서 완료된 워크플로에서 워크플로 인스턴스 ID에 해당하는 파일을 확인하고 이 파일을 메모장에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-153">Identify the one that corresponds to the workflow instance id from the completed workflow in the previous step and open it in Notepad.</span></span> <span data-ttu-id="16ade-154">추적 정보에는 다음과 유사한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-154">The tracking information contains information similar to the following.</span></span>  
  
    ```output
    Please enter a number between 1 and 10
    Your guess is too high.
    Please enter a number between 1 and 10
    Your guess is too high.
    Please enter a number between 1 and 10
    ```

    <span data-ttu-id="16ade-155">이 추적 데이터에는 사용자의 추측 값이 포함되지 않을 뿐 아니라 워크플로의 최종 추측에 대한 정보도 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-155">In addition to the absence of the user's guesses, this tracking data does not contain information about the final guess of the workflow.</span></span> <span data-ttu-id="16ade-156">추적 정보는 워크플로의 `WriteLine` 출력과 워크플로가 완료된 후 `Completed` 처리기에 의해 표시되는 최종 메시지로만 구성되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-156">That is because the tracking information consists only of the `WriteLine` output from the workflow, and the final message that is displayed is done so from the `Completed` handler after the workflow completes.</span></span> <span data-ttu-id="16ade-157">자습서의 다음 단계에서 [방법: 여러 버전을 워크플로-Side-by-side의 호스트](how-to-host-multiple-versions-of-a-workflow-side-by-side.md), 기존 `WriteLine` 활동을 수정 하 여 사용자의 추측 값을 추가로 표시할 `WriteLine` 최종 결과 표시 하는 작업을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-157">In next step of the tutorial, [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md), the existing `WriteLine` activities are modified to display the user's guesses, and an additional `WriteLine` activity is added that displays the final results.</span></span> <span data-ttu-id="16ade-158">이러한 변경 내용을 통합 된 경우 후 [방법: 여러 버전을 워크플로-Side-by-side의 호스트](how-to-host-multiple-versions-of-a-workflow-side-by-side.md) 동시에 여러 버전의 워크플로 호스트 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ade-158">After these changes are integrated, [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md) demonstrates how to host multiple versions of a workflow at the same time.</span></span>
