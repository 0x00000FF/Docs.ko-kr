---
title: "Dotnet 테스트 및 xUnit을 사용하여 .NET Core에서 단위 테스트"
description: "dotnet test 및 xUnit을 사용하여 샘플 솔루션을 단계별로 빌드하는 대화형 환경을 통해 .NET Core의 단위 테스트 개념을 알아봅니다."
author: ardalis
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net-core
ms.translationtype: HT
ms.sourcegitcommit: 867f9eb286fa7ff5ef3e9167c1ab944c81161216
ms.openlocfilehash: d989ee731d7ffd0439bac69afe1458e2aa10733a
ms.contentlocale: ko-kr
ms.lasthandoff: 08/17/2017

---
# <a name="unit-testing-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="fe0ee-103">Dotnet 테스트 및 xUnit을 사용하여 .NET Core에서 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="fe0ee-103">Unit testing in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="fe0ee-104">이 자습서에서는 샘플 솔루션을 단계별로 빌드하는 대화형 환경을 통해 단위 테스트 개념을 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="fe0ee-105">미리 빌드된 솔루션을 사용하여 이 자습서를 진행하려는 경우 시작하기 전에 [샘플 코드를 보거나 다운로드](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/).</span><span class="sxs-lookup"><span data-stu-id="fe0ee-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/) before you begin.</span></span> <span data-ttu-id="fe0ee-106">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="fe0ee-107">소스 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="fe0ee-107">Creating the source project</span></span>

<span data-ttu-id="fe0ee-108">셸 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-108">Open a shell window.</span></span> <span data-ttu-id="fe0ee-109">솔루션을 저장하기 위한 *unit-testing-using-dotnet-test*라는 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-109">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span> <span data-ttu-id="fe0ee-110">이 새로운 디렉터리 내에 *PrimeService* 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-110">Inside this new directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="fe0ee-111">따라서 지금까지의 디렉터리 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-111">The directory structure thus far is shown below:</span></span>

```
/unit-testing-using-dotnet-test
    /PrimeService
```

<span data-ttu-id="fe0ee-112">*PrimeService*를 현재 디렉터리로 만들고 [`dotnet new classlib`](../tools/dotnet-new.md)를 실행하여 소스 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-112">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="fe0ee-113">*Class1.cs*의 이름을 *PrimeService.cs*로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-113">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="fe0ee-114">TDD(테스트 기반 개발)를 사용하기 위해 `PrimeService` 클래스의 실패 구현을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-114">To use test-driven development (TDD), you'll create a failing implementation of the `PrimeService` class:</span></span>

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate) 
        {
            throw new NotImplementedException("Please create a test first");
        } 
    }
}
```

## <a name="creating-the-test-project"></a><span data-ttu-id="fe0ee-115">테스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="fe0ee-115">Creating the test project</span></span>

<span data-ttu-id="fe0ee-116">디렉터리를 다시 *unit-testing-using-dotnet-test* 디렉터리로 변경하고 *PrimeService.Tests* 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-116">Change the directory back to the *unit-testing-using-dotnet-test* directory and create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="fe0ee-117">디렉터리 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-117">The directory structure is shown below:</span></span>

```
/unit-testing-using-dotnet-test
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="fe0ee-118">*PrimeService.Tests* 디렉터리를 현재 디렉터리로 만들고 [`dotnet new xunit`](../tools/dotnet-new.md)를 사용하여 새 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-118">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new xunit`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="fe0ee-119">xUnit을 테스트 라이브러리로 사용하는 테스트 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-119">This creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="fe0ee-120">생성된 템플릿이 *PrimeServiceTests.csproj*에 Test Runner를 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-120">The generated template configures the test runner in the *PrimeServiceTests.csproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="fe0ee-121">테스트 프로제트는 다른 패키지에 단위 테스트를 만들고 실행하도록 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-121">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="fe0ee-122">이전 단계의 `dotnet new`는 xUnit 및 xUnit runner를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-122">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="fe0ee-123">이제 `PrimeService` 클래스 라이브러리를 프로젝트에 다른 종속성으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-123">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="fe0ee-124">[`dotnet add reference`](../tools/dotnet-add-reference.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-124">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="fe0ee-125">또 다른 옵션은 *PrimeService.Tests.csproj* 파일을 편집하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-125">Another option is to edit the *PrimeService.Tests.csproj* file.</span></span> <span data-ttu-id="fe0ee-126">첫 번째 `<ItemGroup>` 노드 바로 아래에서 참조와 함께 다른 `<ItemGroup>` 노드를 라이브러리 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-126">Directly under the first `<ItemGroup>` node, add another `<ItemGroup>` node with a reference to the library project:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
</ItemGroup>
```

<span data-ttu-id="fe0ee-127">GitHub의 [샘플 리포지토리](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj)에서 전체 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-127">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="fe0ee-128">최종 솔루션 레이아웃은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-128">The final solution layout is shown below:</span></span>

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService
        PrimeServiceTests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="fe0ee-129">첫 번째 테스트 만들기</span><span class="sxs-lookup"><span data-stu-id="fe0ee-129">Creating the first test</span></span>

<span data-ttu-id="fe0ee-130">라이브러리 또는 테스트를 빌드하기 전에 *PrimeService.Tests* 디렉터리에서 [`dotnet restore`](../tools/dotnet-restore.md)을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-130">Before building the library or the tests, execute [`dotnet restore`](../tools/dotnet-restore.md) in the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="fe0ee-131">이 명령은 각 프로젝트에 대해 필요한 모든 NuGet 패키지를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-131">This command restores all the necessary NuGet packages for each project.</span></span>

<span data-ttu-id="fe0ee-132">TDD 접근 방식에서는 하나의 실패 테스트를 작성하고, 통과시키고, 이 프로세스를 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-132">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="fe0ee-133">*PrimeService.Tests* 디렉터리에서 *UnitTest1.cs*를 제거하고 다음과 같은 내용으로 새 C# 파일 *PrimeService_IsPrimeShould.cs*를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-133">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

```csharp
using Xunit;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Fact]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, $"1 should not be prime");
        }
    }
}
```

<span data-ttu-id="fe0ee-134">`[Fact]` 특성은 메서드를 단일 테스트로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-134">The `[Fact]` attribute denotes a method as a single test.</span></span> <span data-ttu-id="fe0ee-135">[`dotnet test`](../tools/dotnet-test.md)를 실행하여 테스트 및 클래스 라이브러리를 빌드한 다음 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-135">Execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="fe0ee-136">xUnit Test Runner에는 테스트를 실행할 프로그램 진입점이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-136">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="fe0ee-137">`dotnet test`는 Test Runner를 시작하고, 테스트가 포함된 어셈블리를 나타내는 Test Runner에 명령줄 인수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-137">`dotnet test` starts the test runner and provides a command-line argument to the test runner indicating the assembly that contains your tests.</span></span>

<span data-ttu-id="fe0ee-138">테스트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-138">Your test fails.</span></span> <span data-ttu-id="fe0ee-139">구현은 아직 만들지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-139">You haven't created the implementation yet.</span></span> <span data-ttu-id="fe0ee-140">이 테스트를 통과시킬 가장 간단한 코드를 `PrimeService` 클래스에 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-140">Write the simplest code in the `PrimeService` class to make this test pass:</span></span>

```csharp
public bool IsPrime(int candidate) 
{
    if (candidate == 1) 
    { 
        return false;
    } 
    throw new NotImplementedException("Please create a test first");
} 
```

<span data-ttu-id="fe0ee-141">*PrimeService.Tests* 디렉터리에서 `dotnet test`를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-141">In the *PrimeService.Tests* directory, run `dotnet test` again.</span></span> <span data-ttu-id="fe0ee-142">`dotnet test` 명령은 `PrimeService` 프로젝트에 대한 빌드를 실행한 다음 `PrimeService.Tests` 프로젝트에 대한 빌드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-142">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="fe0ee-143">두 프로젝트를 모두 빌드한 후 이 단일 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-143">After building both projects, it runs this single test.</span></span> <span data-ttu-id="fe0ee-144">전달합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-144">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="fe0ee-145">더 많은 기능 추가</span><span class="sxs-lookup"><span data-stu-id="fe0ee-145">Adding more features</span></span>

<span data-ttu-id="fe0ee-146">이제 하나의 테스트를 통과했으므로 더 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-146">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="fe0ee-147">소수에 대한 몇 가지 다른 간단한 사례가 있습니다(0, -1).</span><span class="sxs-lookup"><span data-stu-id="fe0ee-147">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="fe0ee-148">이들을 `[Fact]` 특성과 함께 새 테스트로 추가할 수도 있지만, 이렇게 하면 금방 지루해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-148">You could add those as new tests with the `[Fact]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="fe0ee-149">비슷한 테스트 모음을 작성하는 데 사용할 수 있는 다른 xUnit 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-149">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="fe0ee-150">`[Theory]` 특성은 같은 코드를 실행하는 테스트 모음을 나타내지만, 서로 다른 입력 인수를 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-150">A `[Theory]` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="fe0ee-151">`[InlineData]` 특성을 사용하여 그러한 입력의 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-151">You can use the `[InlineData]` attribute to specify values for those inputs.</span></span> 
 
<span data-ttu-id="fe0ee-152">새 테스트를 만드는 대신 이 두 가지 특성을 사용하여 2보다 작은 일부 값(가장 낮은 소수)을 테스트하는 단일 이론을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-152">Instead of creating new tests, leverage these two attributes to create a single theory that tests several values less than two, which is the lowest prime number:</span></span>

<span data-ttu-id="fe0ee-153">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span><span class="sxs-lookup"><span data-stu-id="fe0ee-153">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span></span>

<span data-ttu-id="fe0ee-154">`dotnet test`를 실행합니다. 그러면 이러한 테스트 중 2개가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-154">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="fe0ee-155">모든 테스트가 통과하도록 하려면 메서드의 시작 부분에서 `if` 절을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-155">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="fe0ee-156">기본 라이브러리에서 더 많은 테스트, 더 많은 이론, 더 많은 코드를 추가하여 계속 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-156">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="fe0ee-157">[테스트의 완료된 버전](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) 및 [라이브러리의 완전한 구현](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs)으로 종료하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-157">You'll end up with the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="fe0ee-158">작은 라이브러리 및 이 라이브러리에 대한 단위 테스트 집합을 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-158">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="fe0ee-159">새 패키지 및 테스트가 원활하게 진행되도록 솔루션을 구성했으므로 응용 프로그램의 목표를 해결하는 데 시간과 노력을 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0ee-159">You've structured the solution so that adding new packages and tests is seamless, and you can concentrate most of your time and effort on solving the goals of the applicaiton.</span></span>

