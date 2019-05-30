---
title: '방법: 기존 서비스 계약을 사용하는 워크플로 서비스 만들기'
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: 82c9ccc21600ae0b9ff8c514a51ec9b97f8f1d37
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66378126"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a><span data-ttu-id="df78b-102">방법: 기존 서비스 계약을 사용하는 워크플로 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="df78b-102">How to: Create a workflow service that consumes an existing service contract</span></span>
<span data-ttu-id="df78b-103">.NET framework 4.5 기능에는 웹 서비스 및 계약 중심 워크플로 개발의 형태로 워크플로 간의 통합 향상.</span><span class="sxs-lookup"><span data-stu-id="df78b-103">.NET Framework 4.5 features better integration between web services and workflows in the form of contract-first workflow development.</span></span> <span data-ttu-id="df78b-104">계약 중심 워크플로 개발 도구를 사용하면 코드에서 계약을 먼저 디자인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-104">The contract-first workflow development tool allows you to design the contract in code first.</span></span> <span data-ttu-id="df78b-105">그러면 이 도구는 계약의 작업을 위해 도구 상자에 활동 템플릿을 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-105">The tool then automatically generates an activity template in the toolbox for the operations in the contract.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df78b-106">이 항목에서는 계약 중심 워크플로 서비스를 만들기 위한 단계별 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-106">This topic provides step-by-step guidance on creating a contract-first workflow service.</span></span> <span data-ttu-id="df78b-107">계약 중심 워크플로 서비스 개발에 대 한 자세한 내용은 참조 하세요. [계약 중심 워크플로 서비스 개발](contract-first-workflow-service-development.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-107">For more information about contract-first workflow service development, see [Contract First Workflow Service Development](contract-first-workflow-service-development.md).</span></span>  
  
### <a name="creating-the-workflow-project"></a><span data-ttu-id="df78b-108">워크플로 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="df78b-108">Creating the workflow project</span></span>  
  
1. <span data-ttu-id="df78b-109">Visual Studio에서 선택 **파일**하십시오 **새 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-109">In Visual Studio, select **File**, **New Project**.</span></span> <span data-ttu-id="df78b-110">선택 합니다 **WCF** 노드에서 **C#** 에서 노드를 **템플릿** 트리에서 선택한를 **WCF 워크플로 서비스 응용 프로그램** 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-110">Select the **WCF** node under the **C#** node in the **Templates** tree, and select the **WCF Workflow Service Application** template.</span></span>  
  
2. <span data-ttu-id="df78b-111">새 프로젝트의 이름을 `ContractFirst` 누릅니다 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-111">Name the new project `ContractFirst` and click **Ok**.</span></span>  
  
### <a name="creating-the-service-contract"></a><span data-ttu-id="df78b-112">서비스 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="df78b-112">Creating the service contract</span></span>  
  
1. <span data-ttu-id="df78b-113">프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **추가**, **새 항목...** .</span><span class="sxs-lookup"><span data-stu-id="df78b-113">Right-click the project in **Solution Explorer** and select **Add**, **New Item…**.</span></span> <span data-ttu-id="df78b-114">선택 된 **코드** 왼쪽의 노드 및 **클래스** 오른쪽에서 템플릿.</span><span class="sxs-lookup"><span data-stu-id="df78b-114">Select the **Code** node on the left, and the **Class** template on the right.</span></span> <span data-ttu-id="df78b-115">새 클래스 이름을 `IBookService` 누릅니다 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-115">Name the new class `IBookService` and click **Ok**.</span></span>  
  
2. <span data-ttu-id="df78b-116">표시되는 코드 창의 맨 위에서 `System.Servicemodel`에 Using 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-116">In the top of the code window that appears, add a Using statement to `System.Servicemodel`.</span></span>  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3. <span data-ttu-id="df78b-117">샘플 클래스 정의를 다음과 같은 인터페이스 정의로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-117">Change the sample class definition to the following interface definition.</span></span>  
  
    ```  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4. <span data-ttu-id="df78b-118">키를 눌러 프로젝트를 빌드할 **Ctrl + Shift + B**합니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-118">Build the project by pressing **Ctrl+Shift+B**.</span></span>  
  
### <a name="importing-the-service-contract"></a><span data-ttu-id="df78b-119">서비스 계약 가져오기</span><span class="sxs-lookup"><span data-stu-id="df78b-119">Importing the service contract</span></span>  
  
1. <span data-ttu-id="df78b-120">프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **서비스 계약 가져오기**합니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-120">Right-click the project in **Solution Explorer** and select **Import Service Contract**.</span></span> <span data-ttu-id="df78b-121">아래  **\<현재 프로젝트 >** , 모든 하위 노드를 열고 선택한 **IBookService**합니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-121">Under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="df78b-122">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-122">Click **OK**.</span></span>  
  
2. <span data-ttu-id="df78b-123">작업이 성공적으로 완료되었음을 알리는 대화 상자가 열리고 프로젝트가 빌드된 후 생성된 활동이 도구 상자에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-123">A dialog will open, alerting you that the operation completed successfully, and that the generated activities will appear in the toolbox after you build the project.</span></span> <span data-ttu-id="df78b-124">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-124">Click **OK**.</span></span>  
  
3. <span data-ttu-id="df78b-125">키를 눌러 프로젝트를 빌드할 **Ctrl + Shift + B**, 가져온된 활동이 도구 상자에 표시 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-125">Build the project by pressing **Ctrl+Shift+B**, so that the imported activities will appear in the toolbox.</span></span>  
  
4. <span data-ttu-id="df78b-126">**솔루션 탐색기**에서 Service1.xamlx를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-126">In **Solution Explorer**, open Service1.xamlx.</span></span> <span data-ttu-id="df78b-127">워크플로 서비스가 디자이너에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-127">The workflow service will appear in the designer.</span></span>  
  
5. <span data-ttu-id="df78b-128">선택 된 **시퀀스** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-128">Select the **Sequence** activity.</span></span> <span data-ttu-id="df78b-129">속성 창에서 클릭 된 **...**</span><span class="sxs-lookup"><span data-stu-id="df78b-129">In the Properties window, click the **…**</span></span> <span data-ttu-id="df78b-130">단추는 **ImplementedContract** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-130">button in the **ImplementedContract** property.</span></span> <span data-ttu-id="df78b-131">에 **형식 컬렉션 편집기** 창이 나타나면 클릭 합니다 **형식** 드롭다운에서 선택한를 **형식 찾아보기...**</span><span class="sxs-lookup"><span data-stu-id="df78b-131">In the **Type Collection Editor** window that appears, click the **Type** dropdown, and select the **Browse for Types…**</span></span> <span data-ttu-id="df78b-132">항목입니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-132">entry.</span></span> <span data-ttu-id="df78b-133">에 **.NET 유형 선택** 대화 상자 아래에 있는  **\<현재 프로젝트 >** 을 모든 하위 노드를 열고 선택 **IBookService**합니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-133">In the **Browse and Select a .NET Type** dialog, under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="df78b-134">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-134">Click **OK**.</span></span> <span data-ttu-id="df78b-135">에 **형식 컬렉션 편집기** 대화 상자에서 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-135">In the **Type Collection Editor** dialog, click **OK**.</span></span>  
  
6. <span data-ttu-id="df78b-136">선택 하 고 삭제 합니다 **ReceiveRequest** 하 고 **SendResponse** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-136">Select and delete the **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
7. <span data-ttu-id="df78b-137">도구 상자에서 끌어를 **Buy_ReceiveAndSendReply** 및 **Checkout_Receive** 활동을 놓으면 합니다 **순차 서비스** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="df78b-137">From the toolbox, drag a **Buy_ReceiveAndSendReply** and a **Checkout_Receive** activity onto the **Sequential Service** activity.</span></span>
