---
title: "Visual Studio에서 F #으로 시작."
description: "F # Visual Studio와 함께 사용 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 02/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8db75596-19a9-4eda-b20d-a12d517c8cc1
ms.openlocfilehash: 944bbbba6a26634ace269d86cbbdde9ef9de7bcd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="fdc1d-104">Visual Studio에서 F #으로 시작.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-104">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="fdc1d-105">F # 및 Visual F # 도구는 Visual Studio IDE에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-105">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>  <span data-ttu-id="fdc1d-106">를 시작 하려면 [Visual Studio 다운로드](https://www.visualstudio.com/downloads/download-visual-studio-vs)아직 없는 경우, 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-106">To begin, you should [download Visual Studio](https://www.visualstudio.com/downloads/download-visual-studio-vs), if you haven't already.</span></span>  <span data-ttu-id="fdc1d-107">이 문서에서는 Visual Studio 2017 Community Edition을 사용 하지만 사용할 수 있습니다 F # 원하는 버전으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-107">This article uses the Visual Studio 2017 Community Edition, but you can use F# with the version of your choice.</span></span>

## <a name="installing-f"></a><span data-ttu-id="fdc1d-108">F # 설치</span><span class="sxs-lookup"><span data-stu-id="fdc1d-108">Installing F#</span></span> #

<span data-ttu-id="fdc1d-109">처음으로 Visual Studio를 다운로드 하는 경우 Visual Studio 설치 프로그램을 먼저 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-109">If you're downloading Visual Studio for the first time, it will first install the Visual Studio installer.</span></span>  <span data-ttu-id="fdc1d-110">설치 관리자에서 모든 버전의 Visual Studio 2017을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-110">Install any version of Visual Studio 2017 from the installer.</span></span> <span data-ttu-id="fdc1d-111">이미 있는 경우 설치를 클릭 하 여 **수정**합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-111">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="fdc1d-112">다음 작업의 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-112">You'll next see a list of Workloads.</span></span> <span data-ttu-id="fdc1d-113">F #는 다음과 같은 작업 중 하나를 통해 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-113">You can install F# through any of the following workloads:</span></span>

|<span data-ttu-id="fdc1d-114">작업</span><span class="sxs-lookup"><span data-stu-id="fdc1d-114">Workload</span></span>|<span data-ttu-id="fdc1d-115">작업</span><span class="sxs-lookup"><span data-stu-id="fdc1d-115">Action</span></span>|
|--------|------|
| <span data-ttu-id="fdc1d-116">.NET Core 플랫폼 간 개발</span><span class="sxs-lookup"><span data-stu-id="fdc1d-116">.NET Core cross-platform development</span></span> | <span data-ttu-id="fdc1d-117">동작 안 함-F #은 기본적으로 설치</span><span class="sxs-lookup"><span data-stu-id="fdc1d-117">No action - F# is installed by default</span></span> |
| <span data-ttu-id="fdc1d-118">ASP.NET 및 웹 개발</span><span class="sxs-lookup"><span data-stu-id="fdc1d-118">ASP.NET and web development</span></span> | <span data-ttu-id="fdc1d-119">동작 안 함-F #은 기본적으로 설치</span><span class="sxs-lookup"><span data-stu-id="fdc1d-119">No action - F# is installed by default</span></span> |
| <span data-ttu-id="fdc1d-120">Azure 개발</span><span class="sxs-lookup"><span data-stu-id="fdc1d-120">Azure development</span></span> | <span data-ttu-id="fdc1d-121">동작 안 함-F #은 기본적으로 설치</span><span class="sxs-lookup"><span data-stu-id="fdc1d-121">No action - F# is installed by default</span></span> |
| <span data-ttu-id="fdc1d-122">.NET을 사용한 모바일 개발</span><span class="sxs-lookup"><span data-stu-id="fdc1d-122">Mobile development with .NET</span></span> | <span data-ttu-id="fdc1d-123">동작 안 함-F #은 기본적으로 설치</span><span class="sxs-lookup"><span data-stu-id="fdc1d-123">No action - F# is installed by default</span></span> |
| <span data-ttu-id="fdc1d-124">데이터 과학 및 분석 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="fdc1d-124">Data science and analytical applications</span></span> | <span data-ttu-id="fdc1d-125">동작 안 함-F #은 기본적으로 설치</span><span class="sxs-lookup"><span data-stu-id="fdc1d-125">No action - F# is installed by default</span></span> |
| <span data-ttu-id="fdc1d-126">.NET 데스크톱 개발</span><span class="sxs-lookup"><span data-stu-id="fdc1d-126">.NET desktop development</span></span> | <span data-ttu-id="fdc1d-127">선택 **F # 데스크톱 언어 지원** 오른쪽에서</span><span class="sxs-lookup"><span data-stu-id="fdc1d-127">Select **F# desktop language support** from the right-hand side</span></span> |
| <span data-ttu-id="fdc1d-128">데이터 저장소 및 처리</span><span class="sxs-lookup"><span data-stu-id="fdc1d-128">Data storage and processing</span></span> | <span data-ttu-id="fdc1d-129">선택 **F # 데스크톱 언어 지원** 오른쪽에서</span><span class="sxs-lookup"><span data-stu-id="fdc1d-129">Select **F# desktop language support** from the right-hand side</span></span> |

<span data-ttu-id="fdc1d-130">그런 다음 클릭 **수정** 오른쪽 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-130">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="fdc1d-131">그러면 선택한 모든 항목이 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-131">This will install everything you have selected.</span></span>  <span data-ttu-id="fdc1d-132">클릭 하 여 F # 언어 지원과 함께 Visual Studio 2017을 열고 다음 **시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-132">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="fdc1d-133">콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="fdc1d-133">Creating a console application</span></span>

<span data-ttu-id="fdc1d-134">Visual Studio에서 가장 기본적인 프로젝트 중 하나는 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-134">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="fdc1d-135">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-135">Here's how to do it.</span></span>  <span data-ttu-id="fdc1d-136">Visual Studio를 열면:</span><span class="sxs-lookup"><span data-stu-id="fdc1d-136">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="fdc1d-137">에 **파일** 메뉴에서 **새로**를 선택한 후 **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-137">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2.  <span data-ttu-id="fdc1d-138">새로 만들기 대화 상자에서를 아래에서 프로젝트 **템플릿**, 나타납니다 **Visual F #**합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-138">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="fdc1d-139">F # 서식 파일을 표시 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-139">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="fdc1d-140">선택 **.NET Core 콘솔 앱** 또는 **콘솔 응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-140">Select either **.NET Core Console app** or **Console app**.</span></span>

3. <span data-ttu-id="fdc1d-141">선택 된 **알겠습니다** F # 프로젝트를 만드는 단추!</span><span class="sxs-lookup"><span data-stu-id="fdc1d-141">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="fdc1d-142">이제 F # 프로젝트를 솔루션 탐색기에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-142">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="fdc1d-143">코드 작성</span><span class="sxs-lookup"><span data-stu-id="fdc1d-143">Writing your code</span></span>

<span data-ttu-id="fdc1d-144">이제 시작 하겠습니다 먼저 일부 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-144">Let's get started by writing some code first.</span></span>  <span data-ttu-id="fdc1d-145">다음 사항을 확인는 `Program.fs` 파일을 연 상태 및 다음 내용에 다음을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-145">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="fdc1d-146">이전 코드 예제에서 함수 `square` 라는 입력을 가져와서는 정의 된 `x` 여 스스로 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-146">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="fdc1d-147">F #에서 사용 하기 때문에 [형식 유추](../language-reference/type-inference.md), 유형의 `x` 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-147">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="fdc1d-148">F # 컴파일러 곱하기 올바른지 종류를 이해 하 고에 형식을 할당 합니다 `x` 정도에 따라 `square` 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-148">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="fdc1d-149">위로 가져가면 `square`, 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-149">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="fdc1d-150">이 함수의 형식 서명이 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-150">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="fdc1d-151">다음과 같이 읽을 수 있습니다: "사각형 이라는 정수를 사용 하는 함수는 x는 정수를 생성 하 고"입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-151">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="fdc1d-152">지정 하는 컴파일러는 `square` 는 `int` 형식 곱하기에서 제네릭 없기 때문에 이것이 지금은- *모든* 형식, 하지만 대신는 제네릭 형식의 폐쇄형 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-152">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="fdc1d-153">선택 하는 F # 컴파일러 `int` 이 지점 하지만 메이커가 형식 시그니처 호출 하는 경우 `square` 가 다른 입력 형식, 같은 `float`합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-153">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="fdc1d-154">다른 함수 `main`, 정의 된으로 데코레이팅되 어는 `EntryPoint` 해당 프로그램 실행 F # 컴파일러에 지시 하는 특성 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-154">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="fdc1d-155">다른 동일한 규칙에 따라 [C 스타일 프로그래밍 언어](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), 여기서이 함수에 전달할 수 있는 명령줄 인수 및 정수 코드가 반환 됩니다 (일반적으로 `0`).</span><span class="sxs-lookup"><span data-stu-id="fdc1d-155">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="fdc1d-156">이라고 하는이 함수에는 `square` 의 인수와 함께 함수가 `12`합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-156">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="fdc1d-157">F # 컴파일러에는 다음 형식의 할당 `square` 되도록 `int -> int` (사용 되는 함수, 즉는 `int` 하 고 생성 한 `int`).</span><span class="sxs-lookup"><span data-stu-id="fdc1d-157">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="fdc1d-158">에 대 한 호출 `printfn` 은 형식 문자열에 지정 하는 것에 해당 하는 매개 변수를 C 스타일 프로그래밍 언어와 유사한 형식 문자열을 사용 하 여 형식이 지정 된 인쇄 기능 한 다음 결과 새 줄을 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-158">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="fdc1d-159">코드 실행</span><span class="sxs-lookup"><span data-stu-id="fdc1d-159">Running your code</span></span>

<span data-ttu-id="fdc1d-160">코드를 실행 하 고 키를 눌러 결과 확인할 수 있습니다 **ctrl + f 5**합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-160">You can run the code and see results by pressing **ctrl-f5**.</span></span>  <span data-ttu-id="fdc1d-161">디버깅 하지 않고 프로그램 실행 되 고 결과 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-161">This will run the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="fdc1d-162">선택할 수 있습니다는 **디버그** 최상위 메뉴는 Visual Studio에서 항목을 선택 **디버깅 하지 않고 시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-162">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="fdc1d-163">이제 Visual Studio가 팝업를 콘솔 창에 출력할지 다음을 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-163">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="fdc1d-164">지금까지</span><span class="sxs-lookup"><span data-stu-id="fdc1d-164">Congratulations!</span></span>  <span data-ttu-id="fdc1d-165">첫 번째 F # 프로젝트를 Visual Studio에서 만든 하 고, F # 함수는 해당 함수 호출의 결과 인쇄를 작성 하 고, 몇 가지 결과 보려면 프로젝트를 실행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-165">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="fdc1d-166">F # Interactive를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="fdc1d-166">Using F# Interactive</span></span>

<span data-ttu-id="fdc1d-167">Visual F # 도구 Visual Studio에서 가장 유용한 기능 중 하나에 F # Interactive 창입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-167">One of the best features of the Visual F# tooling in Visual Studio is the F# Interactive Window.</span></span>  <span data-ttu-id="fdc1d-168">해당 코드를 호출 하 고 결과 대화형으로 확인할 수 있는 프로세스에 코드를 통해 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-168">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="fdc1d-169">사용을 시작 하려면 강조 표시는 `square` 코드에 정의 된 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-169">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="fdc1d-170">다음으로 저장 된 **Alt** 키를 누릅니다 **Enter**합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-170">Next, hold the **Alt** key and press **Enter**.</span></span>  <span data-ttu-id="fdc1d-171">F # 대화형 창에서 코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-171">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="fdc1d-172">F # 대화형 표시 되는 창에 다음과 같이 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-172">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="fdc1d-173">에 대 한 동일한 함수 시그니처 표시는 `square` 함수 위로 가져갈 때 앞에서 본 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-173">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="fdc1d-174">때문에 `square` 은 F # Interactive 프로세스에 정의 된, 이제 서로 다른 값으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-174">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="fdc1d-175">이 함수를 실행, 결과 새 이름 바인딩합니다 `it`, 유형 및 값을 표시 하 고 `it`합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-175">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="fdc1d-176">각 줄을 종료 해야 참고 `;;`합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-176">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="fdc1d-177">이 어떻게 F # Interactive 알고 함수 호출이 완료 되 면입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-177">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="fdc1d-178">또한 F # Interactive에서 새로운 함수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-178">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="fdc1d-179">위의 정의 새 함수로 `isOdd`,이 `int` 홀수 인지를 확인 하 고!</span><span class="sxs-lookup"><span data-stu-id="fdc1d-179">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span> <span data-ttu-id="fdc1d-180">반환 서로 다른 입력을 확인 하려면이 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-180">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="fdc1d-181">함수 호출 내에서 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-181">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="fdc1d-182">사용할 수도 있습니다는 [정방향 파이프 연산자](../language-reference/symbol-and-operator-reference/index.md) 값 두 함수에 파이프라인 할:</span><span class="sxs-lookup"><span data-stu-id="fdc1d-182">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="fdc1d-183">정방향 파이프 연산자 등은 이후 자습서에서 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-183">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="fdc1d-184">이것은 F # 대화형으로 수행할 수 있는에 간략만 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-184">This is only a glimpse into what you can do with F# Interactive.</span></span> <span data-ttu-id="fdc1d-185">자세한 내용을 보려면 체크 아웃 [F #을 사용한 대화형 프로그래밍](../tutorials/fsharp-interactive/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-185">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="fdc1d-186">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fdc1d-186">Next steps</span></span>

<span data-ttu-id="fdc1d-187">아직 하지 않는 경우 체크 아웃의 [둘러보기의 F #](../tour.md)는 F # 언어의 핵심 기능 중 일부에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-187">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="fdc1d-188">F #의 기능 중 일부에 대 한 개요를 제공 하 고 Visual Studio로 복사 하 고 실행할 수 있는 충분 한 코드 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-188">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="fdc1d-189">사용할 수는 몇 가지 외부 리소스는 또한에서 보여 줍니다는 [F # 가이드](../index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc1d-189">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fdc1d-190">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fdc1d-190">See also</span></span>
 [<span data-ttu-id="fdc1d-191">Visual F#</span><span class="sxs-lookup"><span data-stu-id="fdc1d-191">Visual F#</span></span>](index.md)  
 [<span data-ttu-id="fdc1d-192">F# 둘러보기</span><span class="sxs-lookup"><span data-stu-id="fdc1d-192">Tour of F#</span></span>](../tour.md)  
 [<span data-ttu-id="fdc1d-193">F # 언어 참조</span><span class="sxs-lookup"><span data-stu-id="fdc1d-193">F# language reference</span></span>](../language-reference/index.md)  
 [<span data-ttu-id="fdc1d-194">형식 유추</span><span class="sxs-lookup"><span data-stu-id="fdc1d-194">Type inference</span></span>](../language-reference/type-inference.md)  
 [<span data-ttu-id="fdc1d-195">기호 및 연산자 참조</span><span class="sxs-lookup"><span data-stu-id="fdc1d-195">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)  
