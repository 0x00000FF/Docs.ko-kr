---
title: 정규식 활동
ms.date: 03/30/2017
ms.assetid: b8f24694-49db-4339-92ec-014e3d4ae63b
ms.openlocfilehash: 50daa5b6d7baab37f372de4c30c2e0d12b4fa943
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2018
ms.locfileid: "45668953"
---
# <a name="regular-expression-activities"></a><span data-ttu-id="c56be-102">정규식 활동</span><span class="sxs-lookup"><span data-stu-id="c56be-102">Regular Expression Activities</span></span>
<span data-ttu-id="c56be-103">이 샘플에서는 <xref:System.Text.RegularExpressions> 네임스페이스의 정규식 기능을 노출하는 활동 집합을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-103">This sample demonstrates how to create a set of activities that expose the regular expression functionality of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="c56be-104">이러한 사용자 지정 활동은 워크플로 응용 프로그램 내에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-104">These custom activities can be used within a workflow application.</span></span> <span data-ttu-id="c56be-105">정규식에 대 한 자세한 내용은 참조 하세요. [N:System.Text.RegularExpressions](https://go.microsoft.com/fwlink/?LinkId=150434) Namespace입니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-105">For more information about regular expressions, see [N:System.Text.RegularExpressions](https://go.microsoft.com/fwlink/?LinkId=150434) Namespace.</span></span>  
  
 <span data-ttu-id="c56be-106">다음 표에는 이 샘플의 사용자 지정 활동에 대한 자세한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-106">The following table details the custom activities in this sample.</span></span>  
  
|<span data-ttu-id="c56be-107">동작</span><span class="sxs-lookup"><span data-stu-id="c56be-107">Activity</span></span>|<span data-ttu-id="c56be-108">설명</span><span class="sxs-lookup"><span data-stu-id="c56be-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="c56be-109">IsMatch</span><span class="sxs-lookup"><span data-stu-id="c56be-109">IsMatch</span></span>|<span data-ttu-id="c56be-110">입력 문자열에서 정규식에 일치하는 항목을 찾았는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-110">Specifies whether the regular expression found a match in the input string.</span></span>|  
|<span data-ttu-id="c56be-111">요청 내용</span><span class="sxs-lookup"><span data-stu-id="c56be-111">Matches</span></span>|<span data-ttu-id="c56be-112">입력 문자열에서 정규식의 모든 항목을 검색하고 일치하는 항목을 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-112">Searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span>|  
|<span data-ttu-id="c56be-113">Replace</span><span class="sxs-lookup"><span data-stu-id="c56be-113">Replace</span></span>|<span data-ttu-id="c56be-114">지정된 입력 문자열 내에서 정규식 패턴에 일치하는 문자열을 지정된 대체 문자열로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-114">Within a specified input string, replaces strings that match a regular expression pattern with a specified replacement string.</span></span>|  
  
## <a name="ismatch"></a><span data-ttu-id="c56be-115">IsMatch</span><span class="sxs-lookup"><span data-stu-id="c56be-115">IsMatch</span></span>  
 <span data-ttu-id="c56be-116">`IsMatch` 사용자 지정 활동은 `true` 문자열 속성에서 `Input` 속성에 지정된 정규식에 일치하는 항목을 찾은 경우 `Pattern`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-116">The `IsMatch` custom activity returns `true` if the `Input` string property finds a match in the regular expression specified in the `Pattern` property.</span></span> <span data-ttu-id="c56be-117">이 활동은 <xref:System.Activities.CodeActivity%601>에서 파생되며 <xref:System.Activities.CodeActivity%601.Execute%2A> 메서드 내에서 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-117">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> method.</span></span>  
  
 <span data-ttu-id="c56be-118">다음 표에서는 `IsMatch` 사용자 지정 활동의 속성과 반환 값을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-118">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="c56be-119">속성 또는 반환 값</span><span class="sxs-lookup"><span data-stu-id="c56be-119">Property or Return Value</span></span>|<span data-ttu-id="c56be-120">설명</span><span class="sxs-lookup"><span data-stu-id="c56be-120">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="c56be-121">Pattern(필수)</span><span class="sxs-lookup"><span data-stu-id="c56be-121">Pattern (required)</span></span>|<span data-ttu-id="c56be-122">검색에 사용할 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-122">The regular expression to search with.</span></span>|  
|<span data-ttu-id="c56be-123">Input(필수)</span><span class="sxs-lookup"><span data-stu-id="c56be-123">Input (required)</span></span>|<span data-ttu-id="c56be-124">검색할 입력 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-124">The input string to search.</span></span>|  
|<span data-ttu-id="c56be-125">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="c56be-125">RegexOptions</span></span>|<span data-ttu-id="c56be-126">비트 OR 조합 [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-126">Bitwise OR combination of [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="c56be-127">반환 값</span><span class="sxs-lookup"><span data-stu-id="c56be-127">Return value</span></span>|<span data-ttu-id="c56be-128">제공된 패턴에 일치하는 항목을 입력에서 찾으면 `true`이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-128">`true` if the input finds a match in the provided pattern; otherwise `false`.</span></span>|  
  
 <span data-ttu-id="c56be-129">다음 코드 예제에서는 `IsMatch` 사용자 지정 활동을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-129">The following code example demonstrates how to use the `IsMatch` custom activity.</span></span>  
  
```  
new IsMatch  
{  
    Pattern = new InArgument<string>( @"^-?\d+(\.\d{2})?$"),  
    Input = "20.00",  
};  
```  
  
## <a name="matches"></a><span data-ttu-id="c56be-130">요청 내용</span><span class="sxs-lookup"><span data-stu-id="c56be-130">Matches</span></span>  
 <span data-ttu-id="c56be-131">`Matches` 사용자 지정 활동은 입력 문자열에서 정규식의 모든 항목을 검색하고 일치하는 항목을 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-131">The `Matches` custom activity searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span> <span data-ttu-id="c56be-132">이 활동은 <xref:System.Activities.CodeActivity%601>에서 파생되며 <xref:System.Activities.CodeActivity%601.Execute%2A> 메서드 내에서 <xref:System.Text.RegularExpressions.Regex.Matches%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-132">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Matches%2A> method.</span></span>  
  
 <span data-ttu-id="c56be-133">다음 표에서는 `IsMatch` 사용자 지정 활동의 속성과 반환 값을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-133">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="c56be-134">속성 또는 반환 값</span><span class="sxs-lookup"><span data-stu-id="c56be-134">Property or Return Value</span></span>|<span data-ttu-id="c56be-135">설명</span><span class="sxs-lookup"><span data-stu-id="c56be-135">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="c56be-136">Pattern(필수)</span><span class="sxs-lookup"><span data-stu-id="c56be-136">Pattern (required)</span></span>|<span data-ttu-id="c56be-137">검색에 사용할 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-137">The regular expression to search with.</span></span>|  
|<span data-ttu-id="c56be-138">Input(필수)</span><span class="sxs-lookup"><span data-stu-id="c56be-138">Input (required)</span></span>|<span data-ttu-id="c56be-139">검색할 입력 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-139">The input string to search.</span></span>|  
|<span data-ttu-id="c56be-140">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="c56be-140">RegexOptions</span></span>|<span data-ttu-id="c56be-141">비트 OR 조합 [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-141">Bitwise OR combination of [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="c56be-142">반환 값</span><span class="sxs-lookup"><span data-stu-id="c56be-142">Return Value</span></span>|<span data-ttu-id="c56be-143">일치하는 항목의 컬렉션이 포함된 <xref:System.Text.RegularExpressions.MatchCollection>입니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-143">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="c56be-144">다음 코드 예제에서는 `Matches` 사용자 지정 활동을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-144">The following code example demonstrates how to use the `Matches` custom activity.</span></span>  
  
```  
new Matches  
{  
    Pattern = @"\b(?<word>\w+)\s+(\k<word>)\b",  
    Input = "The quick brown fox  fox jumped over over the lazy dog dog.",  
};  
```  
  
## <a name="replace"></a><span data-ttu-id="c56be-145">Replace</span><span class="sxs-lookup"><span data-stu-id="c56be-145">Replace</span></span>  
 <span data-ttu-id="c56be-146">`Replace` 사용자 지정 활동은 입력 문자열을 검색하고 지정된 정규식에 일치하는 모든 문자열을 대체 문자열로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-146">The `Replace` custom activity searches an input string and replaces all strings that match a specified regular expression with a string.</span></span> <span data-ttu-id="c56be-147">이 활동은 <xref:System.Activities.CodeActivity%601>에서 파생되며 <xref:System.Activities.CodeActivity%601.Execute%2A> 메서드 내에서 <xref:System.Text.RegularExpressions.Regex.Replace%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-147">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Replace%2A> method.</span></span>  
  
 <span data-ttu-id="c56be-148">다음 표에서는 `Replace` 사용자 지정 활동의 속성과 반환 값을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-148">The following table describes the properties and return value for the `Replace` custom activity.</span></span>  
  
|<span data-ttu-id="c56be-149">속성 또는 반환 값</span><span class="sxs-lookup"><span data-stu-id="c56be-149">Property or Return Value</span></span>|<span data-ttu-id="c56be-150">설명</span><span class="sxs-lookup"><span data-stu-id="c56be-150">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="c56be-151">Pattern(필수)</span><span class="sxs-lookup"><span data-stu-id="c56be-151">Pattern (required)</span></span>|<span data-ttu-id="c56be-152">검색에 사용할 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-152">The regular expression to search with.</span></span>|  
|<span data-ttu-id="c56be-153">Input(필수)</span><span class="sxs-lookup"><span data-stu-id="c56be-153">Input (required)</span></span>|<span data-ttu-id="c56be-154">검색할 입력 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-154">The input string to search.</span></span>|  
|<span data-ttu-id="c56be-155">Replacement</span><span class="sxs-lookup"><span data-stu-id="c56be-155">Replacement</span></span>|<span data-ttu-id="c56be-156">대체 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-156">The replacement string.</span></span><br /><br /> <span data-ttu-id="c56be-157">`Replacement`를 지정한 경우 `MatchEvaluator` 속성이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-157">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="c56be-158">`Replacement` 또는 `MatchEvaluator` 속성 중 하나는 반드시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-158">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="c56be-159">MatchEvaluator</span><span class="sxs-lookup"><span data-stu-id="c56be-159">MatchEvaluator</span></span>|<span data-ttu-id="c56be-160">각 항목의 일치 여부를 조사하고 원래 일치 문자열 또는 대체 문자열을 반환하는 사용자 지정 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-160">A custom method that examines each match and returns either the original matched string or a replacement string.</span></span><br /><br /> <span data-ttu-id="c56be-161">`Replacement`를 지정한 경우 `MatchEvaluator` 속성이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-161">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="c56be-162">`Replacement` 또는 `MatchEvaluator` 속성 중 하나는 반드시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-162">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="c56be-163">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="c56be-163">RegexOptions</span></span>|<span data-ttu-id="c56be-164">비트 OR 조합 [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-164">Bitwise OR combination of [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="c56be-165">반환 값</span><span class="sxs-lookup"><span data-stu-id="c56be-165">Return Value</span></span>|<span data-ttu-id="c56be-166">일치하는 항목의 컬렉션이 포함된 <xref:System.Text.RegularExpressions.MatchCollection>입니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-166">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="c56be-167">다음 코드 예제에서는 `Replace` 사용자 지정 활동을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-167">The following code example demonstrates how to use the `Replace` custom activity.</span></span>  
  
```  
// Using the replacement string.  
new Replace  
{  
    Pattern = @"\bWorld\b",  
    Input = "Hello World! This is a wonderful World",  
    Replacement = "Universe"  
};  
  
// Using a match evaluator.  
new Replace  
{  
    Pattern = new InArgument<string>(pattern),  
    Input = new InArgument<string>(input),  
    MatchEvaluator = new MatchEvaluator(CapText)                  
};  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="c56be-168">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="c56be-168">To use this sample</span></span>  
  
1.  <span data-ttu-id="c56be-169">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 RegexActivities.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-169">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RegexActivities.sln solution file.</span></span>  
  
2.  <span data-ttu-id="c56be-170">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-170">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="c56be-171">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-171">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c56be-172">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-172">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c56be-173">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c56be-173">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c56be-174">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="c56be-174">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c56be-175">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c56be-175">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Regex`