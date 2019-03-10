---
title: 필수 인수 및 오버로드 그룹
ms.date: 03/30/2017
ms.assetid: 4ca3ed06-b9af-4b85-8b70-88c2186aefa3
ms.openlocfilehash: b5006a201ce5db68e925bd5764fadde308bbccb4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707874"
---
# <a name="required-arguments-and-overload-groups"></a><span data-ttu-id="d417c-102">필수 인수 및 오버로드 그룹</span><span class="sxs-lookup"><span data-stu-id="d417c-102">Required Arguments and Overload Groups</span></span>
<span data-ttu-id="d417c-103">활동을 실행하기 위해 특정 인수를 바인딩하도록 활동을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-103">Activities can be configured so that certain arguments are required to be bound for the activity to be valid for execution.</span></span> <span data-ttu-id="d417c-104">`RequiredArgument` 특성은 활동의 특정 인수가 필수 인수임을 나타내고 `OverloadGroup` 특성은 필수 인수 범주를 그룹화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-104">The `RequiredArgument` attribute is used to indicate that certain arguments on an activity are required and the `OverloadGroup` attribute is used to group categories of required arguments together.</span></span> <span data-ttu-id="d417c-105">활동 작성자는 특성을 사용하여 단순 활동 유효성 검사 구성 또는 복합 활동 유효성 검사 구성을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-105">By using the attributes, activity authors can provide simple or complex activity validation configurations.</span></span>  
  
## <a name="using-required-arguments"></a><span data-ttu-id="d417c-106">필수 인수 사용</span><span class="sxs-lookup"><span data-stu-id="d417c-106">Using Required Arguments</span></span>  
 <span data-ttu-id="d417c-107">활동에서 `RequiredArgument` 특성을 사용하려면 <xref:System.Activities.RequiredArgumentAttribute>를 사용하여 원하는 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-107">To use the `RequiredArgument` attribute in an activity, indicate the desired arguments using <xref:System.Activities.RequiredArgumentAttribute>.</span></span> <span data-ttu-id="d417c-108">이 예제에서는 두 필수 인수를 가진 `Add` 활동을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-108">In this example, an `Add` activity is defined that has two required arguments.</span></span>  
  
```csharp  
public sealed class Add : CodeActivity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Operand1 { get; set; }  
  
    [RequiredArgument]  
    public InArgument<int> Operand2 { get; set; }  
  
    protected override int Execute(CodeActivityContext context)  
    {  
        return Operand1.Get(context) + Operand2.Get(context);  
    }  
}  
```  
  
 <span data-ttu-id="d417c-109">XAML에서는 또한 <xref:System.Activities.RequiredArgumentAttribute>를 사용하여 필수 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-109">In XAML, required arguments are also indicated by using <xref:System.Activities.RequiredArgumentAttribute>.</span></span> <span data-ttu-id="d417c-110">이 예제에서 `Add` 활동은 세 인수를 사용하여 정의되며 <xref:System.Activities.Statements.Assign%601> 활동을 사용하여 추가 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-110">In this example the `Add` activity is defined by using three arguments and uses an <xref:System.Activities.Statements.Assign%601> activity to perform the add operation.</span></span>  
  
```xaml  
<Activity x:Class="ValidationDemo.Add" ...>  
  <x:Members>  
    <x:Property Name="Operand1" Type="InArgument(x:Int32)">  
      <x:Property.Attributes>  
        <RequiredArgumentAttribute />  
      </x:Property.Attributes>  
    </x:Property>  
    <x:Property Name="Operand2" Type="InArgument(x:Int32)">  
      <x:Property.Attributes>  
        <RequiredArgumentAttribute />  
      </x:Property.Attributes>  
    </x:Property>  
    <x:Property Name="Result" Type="OutArgument(x:Int32)" />  
  </x:Members>  
  <Assign>  
    <Assign.To>  
      <OutArgument x:TypeArguments="x:Int32">[Result]</OutArgument>  
    </Assign.To>  
    <Assign.Value>  
      <InArgument x:TypeArguments="x:Int32">[Operand1 + Operand2]</InArgument>  
    </Assign.Value>  
  </Assign>  
</Activity>  
```  
  
 <span data-ttu-id="d417c-111">활동을 사용할 때 필수 인수가 바인딩되지 않을 경우 다음 유효성 검사 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-111">If the activity is used and either of the required arguments is not bound the following validation error is returned.</span></span>  
  
 <span data-ttu-id="d417c-112">**필수 작업 인수 'Operand1'에 대 한 값을 제공 하지 않았습니다.**</span><span class="sxs-lookup"><span data-stu-id="d417c-112">**Value for a required activity argument 'Operand1' was not supplied.**</span></span>  
> [!NOTE]
> <span data-ttu-id="d417c-113">확인 하 고 유효성 검사 오류 및 경고 처리에 대 한 자세한 내용은 참조 하세요. [활동 유효성 검사 호출](invoking-activity-validation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-113">For more information about checking for and handling validation errors and warnings, see [Invoking Activity Validation](invoking-activity-validation.md).</span></span>  
  
## <a name="using-overload-groups"></a><span data-ttu-id="d417c-114">오버로드 그룹 사용</span><span class="sxs-lookup"><span data-stu-id="d417c-114">Using Overload Groups</span></span>

<span data-ttu-id="d417c-115">오버로드 그룹은 활동에서 유효한 인수 조합을 나타내는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-115">Overload groups provide a method for indicating which combinations of arguments are valid in an activity.</span></span> <span data-ttu-id="d417c-116">인수는 <xref:System.Activities.OverloadGroupAttribute>를 사용하여 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-116">Arguments are grouped together by using <xref:System.Activities.OverloadGroupAttribute>.</span></span> <span data-ttu-id="d417c-117">지정 된 이름이 지정 되 고 각 그룹은 <xref:System.Activities.OverloadGroupAttribute>합니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-117">Each group is given a name that is specified by the <xref:System.Activities.OverloadGroupAttribute>.</span></span> <span data-ttu-id="d417c-118">활동 오버 로드 그룹의 인수 집합 하나만 바인딩되는 경우 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-118">The activity is valid when only one set of arguments in an overload group are bound.</span></span> <span data-ttu-id="d417c-119">다음 예제에서는 `CreateLocation` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-119">In the following example, a `CreateLocation` class is defined.</span></span>  
  
```csharp  
class CreateLocation: Activity  
{  
    [RequiredArgument]  
    public InArgument<string> Name { get; set; }  
  
    public InArgument<string> Description { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G1")]  
    public InArgument<int> Latitude { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G1")]  
    public InArgument<int> Longitude { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G2")]  
    [OverloadGroup("G3")]  
    public InArgument<string> Street { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G2")]  
    public InArgument<string> City { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G2")]  
    public InArgument<string> State { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G3")]  
    public InArgument<int> Zip { get; set; }                  
}  
```  
  
 <span data-ttu-id="d417c-120">이 활동의 목적은 미국 내 위치를 지정하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-120">The objective of this activity is to specify a location in the US.</span></span> <span data-ttu-id="d417c-121">활동 사용자는 세 인수 그룹 중 하나를 사용하여 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-121">To do this, the user of the activity can specify the location using one of three groups of arguments.</span></span> <span data-ttu-id="d417c-122">유효한 인수 조합을 지정하기 위해 세 가지 오버로드 그룹이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-122">To specify the valid combinations of arguments, three overload groups are defined.</span></span> <span data-ttu-id="d417c-123">`G1`에는 `Latitude` 및 `Longitude` 인수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-123">`G1` contains the `Latitude` and `Longitude` arguments.</span></span> <span data-ttu-id="d417c-124">`G2`에는 `Street`, `City` 및 `State`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-124">`G2` contains `Street`, `City`, and `State`.</span></span> <span data-ttu-id="d417c-125">`G3`에는 `Street` 및 `Zip`이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-125">`G3` contains `Street` and `Zip`.</span></span> <span data-ttu-id="d417c-126">`Name`도 필수 인수이지만 오버로드 그룹에 속하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-126">`Name` is also a required argument, but it is not part of an overload group.</span></span> <span data-ttu-id="d417c-127">이 활동이 유효하려면 `Name`을 한 오버로드 그룹의 모든 인수와 함께 바인딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-127">For this activity to be valid, `Name` would have to be bound together with all of the arguments from one and only one overload group.</span></span>  
  
 <span data-ttu-id="d417c-128">다음 예제에서 가져온 합니다 [데이터베이스 액세스 활동](./samples/database-access-activities.md) 샘플에 있는 두 개의 오버 로드 그룹: `ConnectionString` 및 `ConfigFileSectionName`합니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-128">In the following example, taken from the [Database Access Activities](./samples/database-access-activities.md) sample, there are two overload groups: `ConnectionString` and `ConfigFileSectionName`.</span></span> <span data-ttu-id="d417c-129">이 활동이 유효하려면 `ProviderName`과 `ConnectionString` 인수가 바인딩되어 있거나 `ConfigName` 인수가 바인딩되어 있어야 하지만 둘 다가 바인딩되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-129">For this activity to be valid, either the `ProviderName` and `ConnectionString` arguments must be bound, or the `ConfigName` argument, but not both.</span></span>  
  
```  
Public class DbUpdate: AsyncCodeActivity  
{  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DefaultValue(null)]  
    public InArgument<string> ProviderName { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DependsOn("ProviderName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConnectionString { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConfigFileSectionName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConfigName { get; set; }  
  
    [DefaultValue(null)]  
    public CommandType CommandType { get; set; }  
  
    [RequiredArgument]  
    public InArgument<string> Sql { get; set; }  
  
    [DependsOn("Sql")]  
    [DefaultValue(null)]  
    public IDictionary<string, Argument> Parameters { get; }  
  
    [DependsOn("Parameters")]  
    public OutArgument<int> AffectedRecords { get; set; }       
}  
```  
  
 <span data-ttu-id="d417c-130">오버로드 그룹 사용을 정의할 경우</span><span class="sxs-lookup"><span data-stu-id="d417c-130">When defining an overload group:</span></span>  
  
-   <span data-ttu-id="d417c-131">오버로드 그룹은 다른 오버로드 그룹의 하위 집합 또는 이와 동등한 집합이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-131">An overload group cannot be a subset or an equivalent set of another overload group.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d417c-132">그러나 이 규칙에는 한 가지 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-132">There is one exception to this rule.</span></span> <span data-ttu-id="d417c-133">오버로드 그룹이 다른 오버로드 그룹의 하위 집합이고, 하위 집합에 `RequiredArgument`가 `false`인 인수만 있을 경우 오버로드 그룹은 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-133">If an overload group is a subset of another overload group, and the subset contains only arguments where `RequiredArgument` is `false`, then the overload group is valid.</span></span>  
  
-   <span data-ttu-id="d417c-134">오버로드 그룹은 겹칠 수 있지만 그룹의 교집합에 오버로드 그룹 중 하나 또는 둘 다의 모든 필수 인수가 포함되는 경우 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-134">Overload groups can overlap but it is an error if the intersection of the groups contains all the required arguments of one or both of the overload groups.</span></span> <span data-ttu-id="d417c-135">이전 예제에서 `G2` 및 `G3` 오버로드 그룹은 겹쳤지만 교집합에 오버로드 그룹 중 하나 또는 둘 다의 모든 인수가 포함되지 않았으므로 유효했습니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-135">In the previous example the `G2` and `G3` overload groups overlapped, but because the intersection did not contain all the arguments of one or both of the groups this was valid.</span></span>  
  
 <span data-ttu-id="d417c-136">오버로드 그룹에서 인수를 바인딩할 경우</span><span class="sxs-lookup"><span data-stu-id="d417c-136">When binding arguments in an overload group:</span></span>  
  
-   <span data-ttu-id="d417c-137">오버로드 그룹은 그룹의 모든 `RequiredArgument` 인수가 바인딩되는 경우 바인딩된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-137">An overload group is considered bound if all the `RequiredArgument` arguments in the group are bound.</span></span>  
  
-   <span data-ttu-id="d417c-138">그룹에 `RequiredArgument` 인수가 없고 하나 이상의 인수가 바인딩되는 경우 그룹은 바인딩된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-138">If a group has zero `RequiredArgument` arguments and at least one argument bound, then the group is considered bound.</span></span>  
  
-   <span data-ttu-id="d417c-139">하나의 오버로드 그룹에 `RequiredArgument` 인수가 없는 경우가 아니면 오버로드 그룹이 바인딩되지 않은 경우 유효성 검사 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-139">It is a validation error if no overload groups are bound unless one overload group has no `RequiredArgument` arguments in it.</span></span>  
  
-   <span data-ttu-id="d417c-140">두 개 이상의 오버로드 그룹이 바인딩되는 경우, 즉 한 오버로드 그룹의 모든 필수 인수가 바인딩되고 다른 오버로드 그룹의 인수도 바인딩되는 경우 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d417c-140">It is an error to have more than one overload group bound, that is, all required arguments in one overload group are bound and any argument in another overload group is also bound.</span></span>
