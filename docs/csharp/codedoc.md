---
title: XML 주석을 사용하여 코드 문서화
description: XML 문서 주석을 사용하여 코드를 문서화하고 컴파일 시간에 XML 문서 파일을 생성하는 방법을 알아봅니다.
ms.date: 02/14/2017
ms.assetid: 8e75e317-4a55-45f2-a866-e76124171838
ms.openlocfilehash: 15bdd65b96159b4c9b6eb45016f8bdde58c1efe3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576202"
---
# <a name="documenting-your-code-with-xml-comments"></a><span data-ttu-id="68a5e-103">XML 주석을 사용하여 코드 문서화</span><span class="sxs-lookup"><span data-stu-id="68a5e-103">Documenting your code with XML comments</span></span>

<span data-ttu-id="68a5e-104">XML 문서 주석은 사용자 정의 형식이나 멤버의 정의 위에 추가되는 특수 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-104">XML documentation comments are a special kind of comment, added above the definition of any user-defined type or member.</span></span>
<span data-ttu-id="68a5e-105">컴파일 시간에 XML 문서 파일을 생성하기 위해 컴파일러에서 처리될 수 있으므로 특별합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-105">They are special because they can be processed by the compiler to generate an XML documentation file at compile time.</span></span>
<span data-ttu-id="68a5e-106">Visual Studio 및 기타 IDE가 IntelliSense를 사용하여 형식이나 멤버에 대한 빠른 정보를 표시할 수 있도록 컴파일러에서 생성된 XML 파일은 .NET 어셈블리와 함께 배포될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-106">The compiler generated XML file can be distributed alongside your .NET assembly so that Visual Studio and other IDEs can use IntelliSense to show quick information about types or members.</span></span> <span data-ttu-id="68a5e-107">또한 [DocFX](https://dotnet.github.io/docfx/) 및 [Sandcastle](https://github.com/EWSoftware/SHFB) 같은 도구를 통해 XML 파일을 실행하여 API 참조 웹 사이트를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-107">Additionally, the XML file can be run through tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to generate API reference websites.</span></span>

<span data-ttu-id="68a5e-108">XML 문서 주석은 모든 다른 주석처럼 컴파일러에서 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-108">XML documentation comments, like all other comments, are ignored by the compiler.</span></span>

<span data-ttu-id="68a5e-109">다음 중 하나를 수행하여 컴파일 시간에 XML 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-109">You can generate the XML file at compile time by doing one of the following:</span></span>

- <span data-ttu-id="68a5e-110">명령줄에서 .NET Core를 사용하여 애플리케이션을 개발할 경우 .csproj 프로젝트 파일의 `<PropertyGroup>` 섹션에 [DocumentationFile 요소](/visualstudio/msbuild/common-msbuild-project-properties)를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-110">If you are developing an application with .NET Core from the command line, you can add a [DocumentationFile element](/visualstudio/msbuild/common-msbuild-project-properties) to the `<PropertyGroup>` section of your .csproj project file.</span></span> <span data-ttu-id="68a5e-111">다음 예제에서는 프로젝트 디렉터리에 어셈블리와 같은 루트 파일 이름을 가진 XML 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-111">The following example generates an XML file in the project directory with the same root filename as the assembly:</span></span>

   ```xml
   <DocumentationFile>bin\$(Configuration)\$(TargetFramework)\$(AssemblyName).xml</DocumentationFile>
   ```

   <span data-ttu-id="68a5e-112">XML 파일의 정확한 절대 또는 상대 경로를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-112">You can also specify the exact absolute or relative path and name of the XML file.</span></span> <span data-ttu-id="68a5e-113">다음 예제에서는 애플리케이션의 디버그 버전과 같은 디렉터리에 XML 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-113">The following example generates the XML file in the same directory as the debug version of an application:</span></span>

   ```xml
   <DocumentationFile>bin\Debug\netcoreapp2.1\App.xml</DocumentationFile>
   ```

- <span data-ttu-id="68a5e-114">Visual Studio를 사용하여 애플리케이션을 개발할 경우 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-114">If you are developing an application using Visual Studio, right-click on the project and select **Properties**.</span></span> <span data-ttu-id="68a5e-115">[속성] 대화 상자에서 **빌드** 탭을 선택하고 **XML 문서 파일**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-115">In the properties dialog, select the **Build** tab, and check **XML documentation file**.</span></span> <span data-ttu-id="68a5e-116">컴파일러가 파일을 쓰는 위치를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-116">You can also change the location to which the compiler writes the file.</span></span>

- <span data-ttu-id="68a5e-117">명령줄에서 .NET Framework 애플리케이션을 컴파일할 경우 컴파일 시 [/doc 컴파일러 옵션](language-reference/compiler-options/doc-compiler-option.md)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-117">If you are compiling a .NET Framework application from the command line, add the [/doc compiler option](language-reference/compiler-options/doc-compiler-option.md) when compiling.</span></span>  

<span data-ttu-id="68a5e-118">XML 문서 주석에는 삼중 슬래시(`///`) 및 XML 형식의 주석 본문이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-118">XML documentation comments use triple forward slashes (`///`) and an XML formatted comment body.</span></span> <span data-ttu-id="68a5e-119">예:</span><span class="sxs-lookup"><span data-stu-id="68a5e-119">For example:</span></span>

[!code-csharp[XML Documentation Comment](../../samples/snippets/csharp/concepts/codedoc/xml-comment.cs)]

## <a name="walkthrough"></a><span data-ttu-id="68a5e-120">연습</span><span class="sxs-lookup"><span data-stu-id="68a5e-120">Walkthrough</span></span>

<span data-ttu-id="68a5e-121">새로운 개발자가 이해/사용하고 타사 개발자가 사용하기 쉬운 매우 기본적인 수학 라이브러리를 문서화하는 방법을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-121">Let's walk through documenting a very basic math library to make it easy for new developers to understand/contribute and for third party developers to use.</span></span>

<span data-ttu-id="68a5e-122">다음은 간단한 수학 라이브러리에 대한 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-122">Here's code for the simple math library:</span></span>

[!code-csharp[Sample Library](../../samples/snippets/csharp/concepts/codedoc/sample-library.cs)]

<span data-ttu-id="68a5e-123">샘플 라이브러리는 `int` 및 `double` 데이터 형식에서 네 가지 주요 산술 연산인 `add`, `subtract`, `multiply` 및 `divide`를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-123">The sample library supports four major arithmetic operations `add`, `subtract`, `multiply` and `divide` on `int` and `double` data types.</span></span>

<span data-ttu-id="68a5e-124">이제 라이브러리를 사용하지만 소스 코드에 대한 액세스 권한이 없는 타사 개발자를 위해 코드에서 API 참조 문서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-124">Now you want to be able to create an API reference document from your code for third party developers who use your library but don't have access to the source code.</span></span>
<span data-ttu-id="68a5e-125">앞에서 언급한 대로 XML 문서 태그를 사용하여 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-125">As mentioned earlier XML documentation tags can be used to achieve this.</span></span> <span data-ttu-id="68a5e-126">이제 C# 컴파일러가 지원하는 표준 XML 태그를 소개하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-126">You will now be introduced to the standard XML tags the C# compiler supports.</span></span>

### <a name="ltsummarygt"></a><span data-ttu-id="68a5e-127">&lt;요약&gt;</span><span class="sxs-lookup"><span data-stu-id="68a5e-127">&lt;summary&gt;</span></span>

<span data-ttu-id="68a5e-128">`<summary>` 태그는 형식 또는 멤버에 대한 간단한 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-128">The `<summary>` tag adds brief information about a type or member.</span></span>
<span data-ttu-id="68a5e-129">`Math` 클래스 정의 및 첫 번째 `Add` 메서드에 태그를 추가하여 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-129">I'll demonstrate its use by adding it to the `Math` class definition and the first `Add` method.</span></span> <span data-ttu-id="68a5e-130">나머지 코드에 자유롭게 적용하세요.</span><span class="sxs-lookup"><span data-stu-id="68a5e-130">Feel free to apply it to the rest of your code.</span></span>

[!code-csharp[Summary Tag](../../samples/snippets/csharp/concepts/codedoc/summary-tag.cs)]

<span data-ttu-id="68a5e-131">`<summary>` 태그는 매우 중요하고 태그 내용은 IntelliSense 또는 API 참조 문서에서 형식 또는 멤버 정보의 기본 소스이므로 포함하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-131">The `<summary>` tag is very important, and we recommend that you include it because its content is the primary source of type or member information in IntelliSense or an API reference document.</span></span>

### <a name="ltremarksgt"></a><span data-ttu-id="68a5e-132">&lt;설명&gt;</span><span class="sxs-lookup"><span data-stu-id="68a5e-132">&lt;remarks&gt;</span></span>

<span data-ttu-id="68a5e-133">`<remarks>` 태그는 `<summary>` 태그가 제공하는 형식 또는 멤버에 대한 정보를 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-133">The `<remarks>` tag supplements the information about types or members that the `<summary>` tag provides.</span></span> <span data-ttu-id="68a5e-134">이 예제에서는 클래스에 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-134">In this example, you'll just add it to the class.</span></span>

[!code-csharp[Remarks Tag](../../samples/snippets/csharp/concepts/codedoc/remarks-tag.cs)]

### <a name="ltreturnsgt"></a><span data-ttu-id="68a5e-135">&lt;returns&gt;</span><span class="sxs-lookup"><span data-stu-id="68a5e-135">&lt;returns&gt;</span></span>

<span data-ttu-id="68a5e-136">`<returns>` 태그는 메서드 선언의 반환 값을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-136">The `<returns>` tag describes the return value of a method declaration.</span></span>
<span data-ttu-id="68a5e-137">이전과 같이 다음 예제에서는 첫 번째 `Add` 메서드에 대한 `<returns>` 태그를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-137">As before, the following example illustrates the `<returns>` tag on the first `Add` method.</span></span> <span data-ttu-id="68a5e-138">다른 메서드에 대해 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-138">You can do the same on other methods.</span></span>

[!code-csharp[Returns Tag](../../samples/snippets/csharp/concepts/codedoc/returns-tag.cs)]

### <a name="ltvaluegt"></a><span data-ttu-id="68a5e-139">&lt;value&gt;</span><span class="sxs-lookup"><span data-stu-id="68a5e-139">&lt;value&gt;</span></span>

<span data-ttu-id="68a5e-140">`<value>` 태그는 속성에 사용한다는 점을 제외하고 `<returns>` 태그와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-140">The `<value>` tag is similar to the `<returns>` tag, except that you use it for properties.</span></span>
<span data-ttu-id="68a5e-141">`Math` 라이브러리에 `PI`라는 정적 속성이 있다고 가정할 경우 이 태그를 사용하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-141">Assuming your `Math` library had a static property called `PI`, here's how you'd use this tag:</span></span>

[!code-csharp[Value Tag](../../samples/snippets/csharp/concepts/codedoc/value-tag.cs)]

### <a name="ltexamplegt"></a><span data-ttu-id="68a5e-142">&lt;example&gt;</span><span class="sxs-lookup"><span data-stu-id="68a5e-142">&lt;example&gt;</span></span>

<span data-ttu-id="68a5e-143">`<example>` 태그를 사용하여 XML 문서에 예제를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-143">You use the `<example>` tag to include an example in your XML documentation.</span></span>
<span data-ttu-id="68a5e-144">이 과정에는 자식 `<code>` 태그 사용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-144">This involves using the child `<code>` tag.</span></span>

[!code-csharp[Example Tag](../../samples/snippets/csharp/concepts/codedoc/example-tag.cs)]

<span data-ttu-id="68a5e-145">`code` 태그는 더 긴 예제에 대한 줄 바꿈 및 들여쓰기를 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-145">The `code` tag preserves line breaks and indentation for longer examples.</span></span>

### <a name="ltparagt"></a><span data-ttu-id="68a5e-146">&lt;para&gt;</span><span class="sxs-lookup"><span data-stu-id="68a5e-146">&lt;para&gt;</span></span>

<span data-ttu-id="68a5e-147">`<para>` 태그를 사용하여 부모 태그 내에서 내용의 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-147">You use the `<para>` tag to format the content within its parent tag.</span></span> <span data-ttu-id="68a5e-148">`<para>`는 대개 `<remarks>` 또는 `<returns>`와 같은 태그 내부에서 텍스트를 단락으로 나누는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-148">`<para>` is usually used inside a tag, such as `<remarks>` or `<returns>`, to divide text into paragraphs.</span></span>
<span data-ttu-id="68a5e-149">클래스 정의에 대한 `<remarks>` 태그의 내용에 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-149">You can format the contents of the `<remarks>` tag for your class definition.</span></span>

[!code-csharp[Para Tag](../../samples/snippets/csharp/concepts/codedoc/para-tag.cs)]

### <a name="ltcgt"></a><span data-ttu-id="68a5e-150">&lt;c&gt;</span><span class="sxs-lookup"><span data-stu-id="68a5e-150">&lt;c&gt;</span></span>

<span data-ttu-id="68a5e-151">서식 지정 항목에서 텍스트 부분을 코드로 표시하는 데 `<c>` 태그를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-151">Still on the topic of formatting, you use the `<c>` tag for marking part of text as code.</span></span>
<span data-ttu-id="68a5e-152">`<code>` 태그와 비슷하지만 인라인입니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-152">It's like the `<code>` tag but inline.</span></span> <span data-ttu-id="68a5e-153">태그 내용의 일부로 빠른 코드 예제를 표시하려는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-153">It's useful when you want to show a quick code example as part of a tag's content.</span></span>
<span data-ttu-id="68a5e-154">`Math` 클래스에 대한 문서를 업데이트해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-154">Let's update the documentation for the `Math` class.</span></span>

[!code-csharp[C Tag](../../samples/snippets/csharp/concepts/codedoc/c-tag.cs)]

### <a name="ltexceptiongt"></a><span data-ttu-id="68a5e-155">&lt;exception&gt;</span><span class="sxs-lookup"><span data-stu-id="68a5e-155">&lt;exception&gt;</span></span>

<span data-ttu-id="68a5e-156">`<exception>` 태그를 사용하여 메서드가 특정 예외를 throw할 수 있음을 개발자에게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-156">By using the `<exception>` tag, you let your developers know that a method can throw specific exceptions.</span></span>
<span data-ttu-id="68a5e-157">`Math` 라이브러리를 살펴보면 특정 조건에 해당할 경우 두 `Add` 메서드가 모두 예외를 throw함을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-157">Looking at your `Math` library, you can see that both `Add` methods throw an exception if a certain condition is met.</span></span> <span data-ttu-id="68a5e-158">`b` 매개 변수가 0인 경우 정수 `Divide` 메서드도 throw하는지는 분명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-158">Not so obvious, though, is that integer `Divide` method throws as well if the `b` parameter is zero.</span></span> <span data-ttu-id="68a5e-159">이제 이 메서드에 예외 문서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-159">Now add exception documentation to this method.</span></span>

[!code-csharp[Exception Tag](../../samples/snippets/csharp/concepts/codedoc/exception-tag.cs)]

<span data-ttu-id="68a5e-160">`cref` 특성은 현재 컴파일 환경에서 사용할 수 있는 예외에 대한 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-160">The `cref` attribute represents a reference to an exception that is available from the current compilation environment.</span></span>
<span data-ttu-id="68a5e-161">이 특성은 프로젝트 또는 참조된 어셈블리에서 정의된 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-161">This can be any type defined in the project or a referenced assembly.</span></span> <span data-ttu-id="68a5e-162">해당 값을 확인할 수 없는 경우 컴파일러에서 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-162">The compiler will issue a warning if its value cannot be resolved.</span></span>

### <a name="ltseegt"></a><span data-ttu-id="68a5e-163">&lt;see&gt;</span><span class="sxs-lookup"><span data-stu-id="68a5e-163">&lt;see&gt;</span></span>

<span data-ttu-id="68a5e-164">`<see>` 태그를 사용하여 다른 코드 요소에 대한 문서 페이지의 클릭 가능한 링크를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-164">The `<see>` tag lets you create a clickable link to a documentation page for another code element.</span></span> <span data-ttu-id="68a5e-165">다음 예제에서는 두 `Add` 메서드 간의 클릭 가능한 링크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-165">In our next example, we'll create a clickable link between the two `Add` methods.</span></span>

[!code-csharp[See Tag](../../samples/snippets/csharp/concepts/codedoc/see-tag.cs)]

<span data-ttu-id="68a5e-166">`cref`는 현재 컴파일 환경에서 사용할 수 있는 형식 또는 멤버에 대한 참조를 나타내는 **required** 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-166">The `cref` is a **required** attribute that represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="68a5e-167">이 특성은 프로젝트 또는 참조된 어셈블리에서 정의된 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-167">This can be any type defined in the project or a referenced assembly.</span></span>

### <a name="ltseealsogt"></a><span data-ttu-id="68a5e-168">&lt;seealso&gt;</span><span class="sxs-lookup"><span data-stu-id="68a5e-168">&lt;seealso&gt;</span></span>

<span data-ttu-id="68a5e-169">`<seealso>` 태그는 `<see>` 태그와 같은 방법으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-169">You use the `<seealso>` tag in the same way you do the `<see>` tag.</span></span> <span data-ttu-id="68a5e-170">유일한 차이점은 내용이 일반적으로 "참고 항목" 섹션에 배치된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-170">The only difference is that its content is typically placed in a "See Also" section.</span></span> <span data-ttu-id="68a5e-171">이제 정수 `Add` 메서드에 대해 `seealso` 태그를 추가하여 클래스에서 정수 매개 변수를 허용하는 다른 메서드를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-171">Here we'll add a `seealso` tag on the integer `Add` method to reference other methods in the class that accept integer parameters:</span></span>

[!code-csharp[Seealso Tag](../../samples/snippets/csharp/concepts/codedoc/seealso-tag.cs)]

<span data-ttu-id="68a5e-172">`cref`는 현재 컴파일 환경에서 사용할 수 있는 형식 또는 멤버에 대한 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-172">The `cref` attribute represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="68a5e-173">이 특성은 프로젝트 또는 참조된 어셈블리에서 정의된 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-173">This can be any type defined in the project or a referenced assembly.</span></span>

### <a name="ltparamgt"></a><span data-ttu-id="68a5e-174">&lt;param&gt;</span><span class="sxs-lookup"><span data-stu-id="68a5e-174">&lt;param&gt;</span></span>

<span data-ttu-id="68a5e-175">`<param>` 태그를 사용하여 메서드의 매개 변수를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-175">You use the `<param>` tag to describe a method's parameters.</span></span> <span data-ttu-id="68a5e-176">다음은 double `Add` 메서드에 대한 예제입니다. 태그가 설명하는 매개 변수는 **required** `name` 특성에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-176">Here's an example on the double `Add` method: The parameter the tag describes is specified in the **required** `name` attribute.</span></span>

[!code-csharp[Param Tag](../../samples/snippets/csharp/concepts/codedoc/param-tag.cs)]

### <a name="lttypeparamgt"></a><span data-ttu-id="68a5e-177">&lt;typeparam&gt;</span><span class="sxs-lookup"><span data-stu-id="68a5e-177">&lt;typeparam&gt;</span></span>

<span data-ttu-id="68a5e-178">`<typeparam>` 태그는 `<param>` 태그처럼 사용하지만 제네릭 매개 변수를 설명하는 제네릭 형식 또는 메서드 선언에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-178">You use `<typeparam>` tag just like the `<param>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="68a5e-179">`Math` 클래스에 빠른 제네릭 메서드를 추가하여 한 수량이 다른 수량보다 큰지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-179">Add a quick generic method to your `Math` class to check if one quantity is greater than another.</span></span>

[!code-csharp[Typeparam Tag](../../samples/snippets/csharp/concepts/codedoc/typeparam-tag.cs)]

### <a name="ltparamrefgt"></a><span data-ttu-id="68a5e-180">&lt;paramref&gt;</span><span class="sxs-lookup"><span data-stu-id="68a5e-180">&lt;paramref&gt;</span></span>

<span data-ttu-id="68a5e-181">`<summary>` 태그와 같은 태그에서 메서드가 수행하는 작업을 설명하는 동안 매개 변수에 대한 참조를 만들려는 경우</span><span class="sxs-lookup"><span data-stu-id="68a5e-181">Sometimes you might be in the middle of describing what a method does in what could be a `<summary>` tag, and you might want to make a reference to a parameter.</span></span> <span data-ttu-id="68a5e-182">`<paramref>` 태그를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-182">The `<paramref>` tag is great for just this.</span></span> <span data-ttu-id="68a5e-183">double 기반 `Add` 메서드의 요약을 업데이트해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-183">Let's update the summary of our double based `Add` method.</span></span> <span data-ttu-id="68a5e-184">`<param>` 태그처럼 매개 변수 이름은 **required** `name` 특성에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-184">Like the `<param>` tag the parameter name is specified in the **required** `name` attribute.</span></span>

[!code-csharp[Paramref Tag](../../samples/snippets/csharp/concepts/codedoc/paramref-tag.cs)]

### <a name="lttypeparamrefgt"></a><span data-ttu-id="68a5e-185">&lt;typeparamref&gt;</span><span class="sxs-lookup"><span data-stu-id="68a5e-185">&lt;typeparamref&gt;</span></span>

<span data-ttu-id="68a5e-186">`<typeparamref>` 태그는 `<paramref>` 태그처럼 사용하지만 제네릭 매개 변수를 설명하는 제네릭 형식 또는 메서드 선언에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-186">You use `<typeparamref>` tag just like the `<paramref>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="68a5e-187">이전에 만든 것과 같은 제네릭 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-187">You can use the same generic method you previously created.</span></span>

[!code-csharp[Typeparamref Tag](../../samples/snippets/csharp/concepts/codedoc/typeparamref-tag.cs)]

### <a name="ltlistgt"></a><span data-ttu-id="68a5e-188">&lt;list&gt;</span><span class="sxs-lookup"><span data-stu-id="68a5e-188">&lt;list&gt;</span></span>

<span data-ttu-id="68a5e-189">`<list>` 태그를 사용하여 문서 정보의 서식을 순서가 지정된 목록, 순서가 지정되지 않은 목록 또는 표로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-189">You use the `<list>` tag to format documentation information as an ordered list, unordered list or table.</span></span>
<span data-ttu-id="68a5e-190">`Math` 라이브러리에서 지원하는 모든 수학 연산의 순서가 지정되지 않은 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-190">Make an unordered list of every math operation your `Math` library supports.</span></span>

[!code-csharp[List Tag](../../samples/snippets/csharp/concepts/codedoc/list-tag.cs)]

<span data-ttu-id="68a5e-191">`type` 특성을 각각 `number` 또는 `table`로 변경하여 순서가 지정된 목록 또는 표를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-191">You can make an ordered list or table by changing the `type` attribute to `number` or `table`, respectively.</span></span>

### <a name="putting-it-all-together"></a><span data-ttu-id="68a5e-192">전체 과정</span><span class="sxs-lookup"><span data-stu-id="68a5e-192">Putting it all together</span></span>

<span data-ttu-id="68a5e-193">이 자습서에 따라 필요한 경우 코드에 태그를 적용했습니다. 이제 코드는 다음과 같이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-193">If you've followed this tutorial and applied the tags to your code where necessary, your code should now look similar to the following:</span></span>

[!code-csharp[Tagged Library](../../samples/snippets/csharp/concepts/codedoc/tagged-library.cs)]

<span data-ttu-id="68a5e-194">코드에서 클릭 가능한 상호 참조가 포함된 자세한 문서 웹 사이트를 생성할 수 있지만</span><span class="sxs-lookup"><span data-stu-id="68a5e-194">From your code, you can generate a detailed documentation website complete with clickable cross-references.</span></span> <span data-ttu-id="68a5e-195">코드를 읽기 어렵게 되는 다른 문제에 직면할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-195">But you're faced with another problem: your code has become hard to read.</span></span>
<span data-ttu-id="68a5e-196">자세히 살펴볼 정보가 너무 많으므로 이 코드에 참여하려는 개발자에게는 큰 문제일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-196">There's so much information to sift through that this is going to be a nightmare for any developer who wants to contribute to this code.</span></span>
<span data-ttu-id="68a5e-197">다행히도 이 문제를 처리할 수 있는 XML 태그가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-197">Thankfully there's an XML tag that can help you deal with this:</span></span>

### <a name="ltincludegt"></a><span data-ttu-id="68a5e-198">&lt;include&gt;</span><span class="sxs-lookup"><span data-stu-id="68a5e-198">&lt;include&gt;</span></span>

<span data-ttu-id="68a5e-199">소스 코드 파일에 직접 문서 주석을 배치하는 것과 달리 `<include>` 태그를 사용하면 소스 코드에서 형식과 멤버를 설명하는 주석을 개별 XML 파일에서 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-199">The `<include>` tag lets you refer to comments in a separate XML file that describe the types and members in your source code, as opposed to placing documentation comments directly in your source code file.</span></span>

<span data-ttu-id="68a5e-200">이제 모든 XML 태그를 `docs.xml`이라는 개별 XML 파일로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-200">Now you're going to move all your XML tags into a separate XML file named `docs.xml`.</span></span> <span data-ttu-id="68a5e-201">원하는 대로 파일 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-201">Feel free to name the file whatever you want.</span></span>

[!code-xml[Sample XML](../../samples/snippets/csharp/concepts/codedoc/include.xml)]

<span data-ttu-id="68a5e-202">위 XML에서 각 멤버의 문서 주석은 멤버가 수행하는 작업과 같은 이름이 지정된 태그 내부에 직접 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-202">In the above XML, each member's documentation comments appear directly inside a tag named after what they do.</span></span> <span data-ttu-id="68a5e-203">자신만의 전략을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-203">You can choose your own strategy.</span></span>
<span data-ttu-id="68a5e-204">이제 XML 주석이 개별 파일에 있으므로 `<include>` 태그를 사용하여 코드를 더 읽기 좋게 만드는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-204">Now that you have your XML comments in a separate file, let's see how your code can be made more readable by using the `<include>` tag:</span></span>

[!code-csharp[Include Tag](../../samples/snippets/csharp/concepts/codedoc/include-tag.cs)]

<span data-ttu-id="68a5e-205">해냈습니다. 코드를 다시 읽을 수 있고 문서 정보가 손실되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-205">And there you have it: our code is back to being readable, and no documentation information has been lost.</span></span>

<span data-ttu-id="68a5e-206">`filename` 특성은 문서가 포함된 XML 파일의 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-206">The `filename` attribute represents the name of the XML file containing the documentation.</span></span>

<span data-ttu-id="68a5e-207">`path` 특성은 지정된 `filename`에 있는 `tag name`에 대한 [XPath](../standard/data/xml/xpath-queries-and-namespaces.md) 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-207">The `path` attribute represents an [XPath](../standard/data/xml/xpath-queries-and-namespaces.md) query to the `tag name` present in the specified `filename`.</span></span>

<span data-ttu-id="68a5e-208">`name` 특성은 주석 앞에 오는 태그의 이름 지정자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-208">The `name` attribute represents the name specifier in the tag that precedes the comments.</span></span>

<span data-ttu-id="68a5e-209">`name` 대신 사용할 수 있는 `id` 특성은 주석 앞에 오는 태그의 ID를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-209">The `id` attribute which can be used in place of `name` represents the ID for the tag that precedes the comments.</span></span>

### <a name="user-defined-tags"></a><span data-ttu-id="68a5e-210">사용자 정의 태그</span><span class="sxs-lookup"><span data-stu-id="68a5e-210">User Defined Tags</span></span>

<span data-ttu-id="68a5e-211">위에서 설명한 모든 태그는 C# 컴파일러에서 인식되는 태그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-211">All the tags outlined above represent those that are recognized by the C# compiler.</span></span> <span data-ttu-id="68a5e-212">그러나 사용자가 자유롭게 태그를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-212">However, a user is free to define their own tags.</span></span>
<span data-ttu-id="68a5e-213">Sandcastle 등의 도구는 [`<event>`](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm), [`<note>`](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm) 같은 추가 태그를 지원하고 [네임스페이스 문서화](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm)도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-213">Tools like Sandcastle bring support for extra tags like [`<event>`](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm), [`<note>`](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm) and even support [documenting namespaces](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).</span></span>
<span data-ttu-id="68a5e-214">사용자 지정 또는 사내 문서 생성 도구는 표준 태그와 함께 사용할 수도 있고 HTML에서 PDF까지 다양한 출력 형식을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-214">Custom or in-house documentation generation tools can also be used with the standard tags and multiple output formats from HTML to PDF can be supported.</span></span>

## <a name="recommendations"></a><span data-ttu-id="68a5e-215">권장 사항</span><span class="sxs-lookup"><span data-stu-id="68a5e-215">Recommendations</span></span>

<span data-ttu-id="68a5e-216">여러 가지 이유로 코드를 문서화하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-216">Documenting code is recommended for many reasons.</span></span> <span data-ttu-id="68a5e-217">이어서 일부 모범 사례, 일반적인 사용 사례 시나리오 및 C# 코드에서 XML 문서 태그를 사용할 때 알아야 하는 내용을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-217">What follows are some best practices, general use case scenarios, and things that you should know when using XML documentation tags in your C# code.</span></span>

* <span data-ttu-id="68a5e-218">일관성을 보장하기 위해 모든 공개 형식과 해당 멤버를 문서화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-218">For the sake of consistency, all publicly visible types and their members should be documented.</span></span> <span data-ttu-id="68a5e-219">문서화해야 한다면 모두 문서화하세요.</span><span class="sxs-lookup"><span data-stu-id="68a5e-219">If you must do it, do it all.</span></span>
* <span data-ttu-id="68a5e-220">Private 멤버는 XML 주석을 사용하여 문서화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-220">Private members can also be documented using XML comments.</span></span> <span data-ttu-id="68a5e-221">그러나 이렇게 하면 라이브러리의 내부(잠재적으로 기밀) 작업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-221">However, this exposes the inner (potentially confidential) workings of your library.</span></span>
* <span data-ttu-id="68a5e-222">IntelliSense에는 `<summary>` 태그의 내용이 필요하므로 최소한 형식과 해당 멤버에 이 태그가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-222">At a bare minimum, types and their members should have a `<summary>` tag because its content is needed for IntelliSense.</span></span>
* <span data-ttu-id="68a5e-223">문서 텍스트는 마침표로 끝나는 전체 문장을 사용하여 기록되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-223">Documentation text should be written using complete sentences ending with full stops.</span></span>
* <span data-ttu-id="68a5e-224">Partial 클래스는 완전히 지원되고 문서 정보는 해당 형식의 단일 항목에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-224">Partial classes are fully supported, and documentation information will be concatenated into a single entry for that type.</span></span>
* <span data-ttu-id="68a5e-225">컴파일러에서 `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>` 및 `<typeparam>` 태그의 구문을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-225">The compiler verifies the syntax of the `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>` and `<typeparam>` tags.</span></span>
- <span data-ttu-id="68a5e-226">컴파일러는 파일 경로와 코드의 다른 부분에 대한 참조가 포함된 매개 변수의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="68a5e-226">The compiler validates the parameters that contain file paths and references to other parts of the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="68a5e-227">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68a5e-227">See also</span></span>

- [<span data-ttu-id="68a5e-228">XML 문서 주석(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="68a5e-228">XML Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/xml-documentation-comments.md)
- [<span data-ttu-id="68a5e-229">문서 주석에 대한 권장 태그(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="68a5e-229">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
