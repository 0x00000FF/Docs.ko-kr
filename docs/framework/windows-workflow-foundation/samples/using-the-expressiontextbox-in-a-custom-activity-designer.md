---
title: 사용자 지정 활동 디자이너에서 ExpressionTextBox 사용
ms.date: 03/30/2017
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
ms.openlocfilehash: ee9da26625d772eda6100fc4d0db0469941bdb0d
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48849817"
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a><span data-ttu-id="b87a5-102">사용자 지정 활동 디자이너에서 ExpressionTextBox 사용</span><span class="sxs-lookup"><span data-stu-id="b87a5-102">Using the ExpressionTextBox in a Custom Activity Designer</span></span>
<span data-ttu-id="b87a5-103">이 샘플에서는 사용자 지정 활동 디자이너에서 <xref:System.Activities.Presentation.View.ExpressionTextBox>를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-103">This sample shows how to use the <xref:System.Activities.Presentation.View.ExpressionTextBox> in a custom activity designer.</span></span> <span data-ttu-id="b87a5-104">사용자 지정 활동인 `MultiAssign`은 두 개의 문자열 변수에 두 개의 문자열 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-104">The custom activity, `MultiAssign`, assigns two string values to two string variables.</span></span> <span data-ttu-id="b87a5-105"><xref:System.Activities.Presentation.View.ExpressionTextBox> 컨트롤 중 일부는 <xref:System.Activities.InArgument>에 바인딩되고 또 다른 일부는 <xref:System.Activities.OutArgument>에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-105">Some <xref:System.Activities.Presentation.View.ExpressionTextBox> controls bind to <xref:System.Activities.InArgument>s and some bind to <xref:System.Activities.OutArgument>s.</span></span>

## <a name="sample-details"></a><span data-ttu-id="b87a5-106">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="b87a5-106">Sample details</span></span>
 <span data-ttu-id="b87a5-107">`ArgumentToExpressionConverter`는 식을 인수에 바인딩할 때 사용되는 형식 변환기입니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-107">The `ArgumentToExpressionConverter` is the type converter used when binding expressions to arguments.</span></span> <span data-ttu-id="b87a5-108">`ConverterParameter`는 `In` 또는 `Out`으로 적절히 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-108">The `ConverterParameter` must be set to `In` or `Out` as appropriate.</span></span> <span data-ttu-id="b87a5-109">`InOut`은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-109">`InOut` is not supported.</span></span>

 <span data-ttu-id="b87a5-110">`UseLocationExpression` 특성에는 `OutArgument`식이 l-value ("왼쪽된 값" 또는 "위치 값") 식을 여야 한다고 지정 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-110">The `UseLocationExpression` attribute is used on `OutArgument`s to specify that the expression should be an L-value ("left value" or "location value") expression.</span></span> <span data-ttu-id="b87a5-111">대부분의 경우 L-value 식은 반환되는 `OutArgument`가 변수인지 인수 이름인지를 나타내는 데 사용되는 유효한 Visual Basic 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-111">In most cases, an L-value expression is a valid Visual Basic identifier used to indicate that the `OutArgument` being returned is a variable or argument name.</span></span>

 <span data-ttu-id="b87a5-112">이 예제에서 `MaxLines` 특성은 1로 설정되어 있으며 `MinLines`는 설정되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-112">The `MaxLines` attribute is set to one in this example and `MinLines` is not set.</span></span> <span data-ttu-id="b87a5-113">이는 사용자가 입력하는 테스트 크기에 관계없이 <xref:System.Activities.Presentation.View.ExpressionTextBox>는 한 줄이라는 고정된 크기임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-113">This indicates that the <xref:System.Activities.Presentation.View.ExpressionTextBox> is a fixed size of one line regardless of the amount of text typed by the user.</span></span> <span data-ttu-id="b87a5-114"><xref:System.Activities.Presentation.View.ExpressionTextBox>를 사용자 입력에 맞춰 늘릴 수 있게 하려면 `MaxLines`를 `MinLines`보다 큰 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-114">To allow the <xref:System.Activities.Presentation.View.ExpressionTextBox> to grow to fit user input, set `MaxLines` greater than `MinLines`.</span></span>

 <span data-ttu-id="b87a5-115">ExpressionTextBox는 인수에만 바인딩할 수 있고 CLR 속성에는 바인딩할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-115">An ExpressionTextBox can only be bound to arguments, and cannot be bound to CLR properties.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="b87a5-116">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="b87a5-116">To use this sample</span></span>

1.  <span data-ttu-id="b87a5-117">Expressiontextboxsample.sln 솔루션 파일을 열고 Visual Studio 2010을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-117">Using Visual Studio 2010, open the ExpressionTextBoxSample.sln file.</span></span>

2.  <span data-ttu-id="b87a5-118">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-118">To build the solution, press CTRL+SHIFT+B.</span></span>

#### <a name="to-run-this-sample"></a><span data-ttu-id="b87a5-119">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="b87a5-119">To run this sample</span></span>

1.  <span data-ttu-id="b87a5-120">솔루션에 워크플로 콘솔 응용 프로그램을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-120">Add a new Workflow Console Application to the solution.</span></span>

2.  <span data-ttu-id="b87a5-121">에 대 한 참조를 추가 합니다 **ExpressionTextBoxSample** 새 워크플로 콘솔 응용 프로그램 프로젝트에서 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-121">Add a reference to the **ExpressionTextBoxSample** project from the new Workflow Console Application project.</span></span>

3.  <span data-ttu-id="b87a5-122">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-122">Build the solution.</span></span>

4.  <span data-ttu-id="b87a5-123">끌기 합니다 **MultiAssign** 활동 도구 상자에서 워크플로에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-123">Drag the **MultiAssign** activity from the toolbox and drop it into the workflow.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="b87a5-124">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b87a5-125">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b87a5-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b87a5-126">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="b87a5-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b87a5-127">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b87a5-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a><span data-ttu-id="b87a5-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b87a5-128">See Also</span></span>  
 <xref:System.Activities.Presentation.View.ExpressionTextBox>  
 [<span data-ttu-id="b87a5-129">워크플로 디자이너로 응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="b87a5-129">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
