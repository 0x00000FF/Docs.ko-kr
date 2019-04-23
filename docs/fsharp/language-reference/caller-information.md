---
title: 호출자 정보
description: 메서드에서 호출자 정보를 가져오려면 호출자 정보 인수 특성을 사용 하는 방법에 설명 합니다.
ms.date: 04/25/2017
ms.openlocfilehash: 13092df453b684d3ed4a93c842ea49c066157cb6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316156"
---
# <a name="caller-information"></a><span data-ttu-id="d433f-103">호출자 정보</span><span class="sxs-lookup"><span data-stu-id="d433f-103">Caller information</span></span>

<span data-ttu-id="d433f-104">호출자 정보 특성을 사용하여 메서드 호출자에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-104">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="d433f-105">소스 코드 파일 경로, 소스 코드 줄 번호 및 호출자의 멤버 이름을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-105">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="d433f-106">이 정보는 추적, 디버깅 및 진단 도구를 만드는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-106">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="d433f-107">이 정보를 얻으려면 각각 기본값이 있는 선택적 매개 변수에 적용되는 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-107">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="d433f-108">다음 표에 정의 된 호출자 정보 특성을 [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) 네임 스페이스:</span><span class="sxs-lookup"><span data-stu-id="d433f-108">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="d433f-109">특성</span><span class="sxs-lookup"><span data-stu-id="d433f-109">Attribute</span></span>|<span data-ttu-id="d433f-110">설명</span><span class="sxs-lookup"><span data-stu-id="d433f-110">Description</span></span>|<span data-ttu-id="d433f-111">형식</span><span class="sxs-lookup"><span data-stu-id="d433f-111">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="d433f-112">CallerFilePath</span><span class="sxs-lookup"><span data-stu-id="d433f-112">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="d433f-113">호출자를 포함한 소스 파일의 전체 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="d433f-114">컴파일 시간의 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-114">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="d433f-115">CallerLineNumber</span><span class="sxs-lookup"><span data-stu-id="d433f-115">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="d433f-116">메서드가 호출되는 소스 파일의 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-116">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="d433f-117">CallerMemberName</span><span class="sxs-lookup"><span data-stu-id="d433f-117">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="d433f-118">호출자의 메서드 또는 속성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-118">Method or property name of the caller.</span></span> <span data-ttu-id="d433f-119">이 항목의 뒷부분에 나오는 멤버 이름 섹션을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-119">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="d433f-120">예제</span><span class="sxs-lookup"><span data-stu-id="d433f-120">Example</span></span>

<span data-ttu-id="d433f-121">다음 예에서는 호출자를 추적 하려면 이러한 특성을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-121">The following example shows how you might use these attributes to trace a caller.</span></span>

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices
open System.Runtime.InteropServices

type Tracer() =
    member __.DoTrace(message: string,
                      [<CallerMemberName; Optional; DefaultParameterValue("")>] memberName: string,
                      [<CallerFilePath; Optional; DefaultParameterValue("")>] path: string,
                      [<CallerLineNumber; Optional; DefaultParameterValue(0)>] line: int) =
        Trace.WriteLine(sprintf "Message: %s" message)
        Trace.WriteLine(sprintf "Member name: %s" memberName)
        Trace.WriteLine(sprintf "Source file path: %s" path)
        Trace.WriteLine(sprintf "Source line number: %d" line)
```

## <a name="remarks"></a><span data-ttu-id="d433f-122">설명</span><span class="sxs-lookup"><span data-stu-id="d433f-122">Remarks</span></span>

<span data-ttu-id="d433f-123">호출자 정보 특성은 선택적 매개 변수에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-123">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="d433f-124">호출자 정보 특성을 사용 하면 컴파일러가 각 선택적 매개 변수에 호출자 정보 특성으로 데코 레이트 된 적절 한 값을 쓸.</span><span class="sxs-lookup"><span data-stu-id="d433f-124">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="d433f-125">호출자 정보 값은 컴파일 시간에 리터럴로 중간 언어(IL) 내로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-125">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="d433f-126">결과 달리 합니다 [StackTrace](/dotnet/api/system.diagnostics.stacktrace) 난독 처리 속성 예외를 결과 대 한 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-126">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="d433f-127">선택적 인수를 명시적으로 제공하여 호출자 정보를 제어하거나 호출자 정보를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-127">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="d433f-128">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="d433f-128">Member names</span></span>

<span data-ttu-id="d433f-129">사용할 수는 [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) 멤버 이름을 지정 하지 않으려면 특성을 `String` 호출 된 메서드에 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-129">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="d433f-130">이 기법을 사용 하 여 이름 바꾸기 리팩터링 변경 되지 않는 문제를 방지 하는 `String` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-130">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="d433f-131">이 이점은 다음 작업에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-131">This benefit is especially useful for the following tasks:</span></span>

* <span data-ttu-id="d433f-132">추적 및 진단 루틴 사용.</span><span class="sxs-lookup"><span data-stu-id="d433f-132">Using tracing and diagnostic routines.</span></span>
* <span data-ttu-id="d433f-133">구현 된 [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) 데이터 바인딩할 때 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-133">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="d433f-134">이 인터페이스에서는 컨트롤에서 업데이트된 정보를 표시할 수 있도록 바운드 컨트롤의 속성이 변경되었음을 알리는 개체의 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-134">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="d433f-135">없이 합니다 [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) 특성 속성 이름을 리터럴로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-135">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="d433f-136">다음 차트는 이름을 CallerMemberName 특성을 사용 하는 경우 반환 되는 멤버를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-136">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="d433f-137">호출 발생 범위</span><span class="sxs-lookup"><span data-stu-id="d433f-137">Calls occurs within</span></span>|<span data-ttu-id="d433f-138">멤버 이름 결과</span><span class="sxs-lookup"><span data-stu-id="d433f-138">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="d433f-139">메서드, 속성 또는 이벤트</span><span class="sxs-lookup"><span data-stu-id="d433f-139">Method, property, or event</span></span>|<span data-ttu-id="d433f-140">호출에서 시작한 메서드, 속성 또는 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-140">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="d433f-141">생성자</span><span class="sxs-lookup"><span data-stu-id="d433f-141">Constructor</span></span>|<span data-ttu-id="d433f-142">".ctor" 문자열</span><span class="sxs-lookup"><span data-stu-id="d433f-142">The string ".ctor"</span></span>|
|<span data-ttu-id="d433f-143">정적 생성자</span><span class="sxs-lookup"><span data-stu-id="d433f-143">Static constructor</span></span>|<span data-ttu-id="d433f-144">".cctor" 문자열</span><span class="sxs-lookup"><span data-stu-id="d433f-144">The string ".cctor"</span></span>|
|<span data-ttu-id="d433f-145">소멸자</span><span class="sxs-lookup"><span data-stu-id="d433f-145">Destructor</span></span>|<span data-ttu-id="d433f-146">"Finalize" 문자열</span><span class="sxs-lookup"><span data-stu-id="d433f-146">The string "Finalize"</span></span>|
|<span data-ttu-id="d433f-147">사용자 정의 연산자 또는 변환</span><span class="sxs-lookup"><span data-stu-id="d433f-147">User-defined operators or conversions</span></span>|<span data-ttu-id="d433f-148">멤버에 대해 생성되는 이름입니다(예: "op_Addition").</span><span class="sxs-lookup"><span data-stu-id="d433f-148">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="d433f-149">특성 생성자</span><span class="sxs-lookup"><span data-stu-id="d433f-149">Attribute constructor</span></span>|<span data-ttu-id="d433f-150">특성이 적용되는 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-150">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="d433f-151">특성이 멤버 내에 있는 어떤 요소인 경우(예: 매개 변수, 반환 값 또는 제네릭 형식 매개 변수) 이 결과는 그 요소와 관련된 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-151">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="d433f-152">포함하는 멤버가 없음(예: 어셈블리 수준 또는 형식에 적용되는 특성)</span><span class="sxs-lookup"><span data-stu-id="d433f-152">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="d433f-153">선택적 매개 변수의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="d433f-153">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="d433f-154">참고자료</span><span class="sxs-lookup"><span data-stu-id="d433f-154">See also</span></span>

- [<span data-ttu-id="d433f-155">특성</span><span class="sxs-lookup"><span data-stu-id="d433f-155">Attributes</span></span>](attributes.md)
- [<span data-ttu-id="d433f-156">명명 된 인수</span><span class="sxs-lookup"><span data-stu-id="d433f-156">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)
- [<span data-ttu-id="d433f-157">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="d433f-157">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)
