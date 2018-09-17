---
title: '방법: 식 트리를 사용하여 동적 쿼리 빌드(C#)'
ms.date: 07/20/2015
ms.assetid: 52cd44dd-a3ec-441e-b93a-4eca388119c7
ms.openlocfilehash: e3afbea647bb429d25f41f37fde268565bc5bf8a
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2018
ms.locfileid: "45591414"
---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-c"></a><span data-ttu-id="ce4cc-102">방법: 식 트리를 사용하여 동적 쿼리 빌드(C#)</span><span class="sxs-lookup"><span data-stu-id="ce4cc-102">How to: Use Expression Trees to Build Dynamic Queries (C#)</span></span>
<span data-ttu-id="ce4cc-103">LINQ에서는 식 트리를 사용하여 <xref:System.Linq.IQueryable%601>을 구현하는 데이터 소스를 대상으로 하는 구조적 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-103">In LINQ, expression trees are used to represent structured queries that target sources of data that implement <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="ce4cc-104">예를 들어 LINQ 공급자는 관계형 데이터 저장소를 쿼리하기 위한 <xref:System.Linq.IQueryable%601> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-104">For example, the LINQ provider implements the <xref:System.Linq.IQueryable%601> interface for querying relational data stores.</span></span> <span data-ttu-id="ce4cc-105">C# 컴파일러는 이러한 데이터 소스를 대상으로 하는 쿼리를 런타임에 식 트리를 작성하는 코드로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-105">The C# compiler compiles queries that target such data sources into code that builds an expression tree at runtime.</span></span> <span data-ttu-id="ce4cc-106">그런 다음 쿼리 공급자는 식 트리 데이터 구조를 트래버스하고 데이터 소스에 적합한 쿼리 언어로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-106">The query provider can then traverse the expression tree data structure and translate it into a query language appropriate for the data source.</span></span>  
  
 <span data-ttu-id="ce4cc-107">식 트리는 LINQ에서 <xref:System.Linq.Expressions.Expression%601> 형식의 변수에 할당된 람다 식을 나타내는 데에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-107">Expression trees are also used in LINQ to represent lambda expressions that are assigned to variables of type <xref:System.Linq.Expressions.Expression%601>.</span></span>  
  
 <span data-ttu-id="ce4cc-108">이 항목에서는 식 트리를 사용하여 동적 LINQ 쿼리를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-108">This topic describes how to use expression trees to create dynamic LINQ queries.</span></span> <span data-ttu-id="ce4cc-109">동적 쿼리는 컴파일 시 쿼리의 세부 정보를 알 수 없는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-109">Dynamic queries are useful when the specifics of a query are not known at compile time.</span></span> <span data-ttu-id="ce4cc-110">예를 들어 최종 사용자가 하나 이상의 조건자를 지정하여 데이터를 필터링할 수 있는 사용자 인터페이스를 응용 프로그램에서 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-110">For example, an application might provide a user interface that enables the end user to specify one or more predicates to filter the data.</span></span> <span data-ttu-id="ce4cc-111">LINQ를 쿼리에 사용하려면 이러한 종류의 응용 프로그램에서 식 트리를 사용하여 런타임에 LINQ 쿼리를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-111">In order to use LINQ for querying, this kind of application must use expression trees to create the LINQ query at runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce4cc-112">예</span><span class="sxs-lookup"><span data-stu-id="ce4cc-112">Example</span></span>  
 <span data-ttu-id="ce4cc-113">다음 예제에서는 식 트리를 사용하여 `IQueryable` 데이터 소스에 대한 쿼리를 생성한 다음 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-113">The following example shows you how to use expression trees to construct a query against an `IQueryable` data source and then execute it.</span></span> <span data-ttu-id="ce4cc-114">코드에서 다음 쿼리를 나타내는 식 트리를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-114">The code builds an expression tree to represent the following query:</span></span>  
  
 `companies.Where(company => (company.ToLower() == "coho winery" || company.Length > 16)).OrderBy(company => company)`  
  
 <span data-ttu-id="ce4cc-115"><xref:System.Linq.Expressions> 네임스페이스의 팩터리 메서드는 전체 쿼리를 구성하는 식을 나타내는 식 트리를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-115">The factory methods in the <xref:System.Linq.Expressions> namespace are used to create expression trees that represent the expressions that make up the overall query.</span></span> <span data-ttu-id="ce4cc-116">표준 쿼리 연산자 메서드 호출을 나타내는 식은 이러한 메서드의 <xref:System.Linq.Queryable> 구현을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-116">The expressions that represent calls to the standard query operator methods refer to the <xref:System.Linq.Queryable> implementations of these methods.</span></span> <span data-ttu-id="ce4cc-117">최종 식 트리는 `IQueryable` 데이터 소스 공급자의 <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> 구현에 전달되어 `IQueryable` 형식의 실행 가능한 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-117">The final expression tree is passed to the <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> implementation of the provider of the `IQueryable` data source to create an executable query of type `IQueryable`.</span></span> <span data-ttu-id="ce4cc-118">해당 쿼리 변수를 열거하여 결과를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-118">The results are obtained by enumerating that query variable.</span></span>  
  
```csharp  
// Add a using directive for System.Linq.Expressions.  
  
string[] companies = { "Consolidated Messenger", "Alpine Ski House", "Southridge Video", "City Power & Light",  
                   "Coho Winery", "Wide World Importers", "Graphic Design Institute", "Adventure Works",  
                   "Humongous Insurance", "Woodgrove Bank", "Margie's Travel", "Northwind Traders",  
                   "Blue Yonder Airlines", "Trey Research", "The Phone Company",  
                   "Wingtip Toys", "Lucerne Publishing", "Fourth Coffee" };  
  
// The IQueryable data to query.  
IQueryable<String> queryableData = companies.AsQueryable<string>();  
  
// Compose the expression tree that represents the parameter to the predicate.  
ParameterExpression pe = Expression.Parameter(typeof(string), "company");  
  
// ***** Where(company => (company.ToLower() == "coho winery" || company.Length > 16)) *****  
// Create an expression tree that represents the expression 'company.ToLower() == "coho winery"'.  
Expression left = Expression.Call(pe, typeof(string).GetMethod("ToLower", System.Type.EmptyTypes));  
Expression right = Expression.Constant("coho winery");  
Expression e1 = Expression.Equal(left, right);  
  
// Create an expression tree that represents the expression 'company.Length > 16'.  
left = Expression.Property(pe, typeof(string).GetProperty("Length"));  
right = Expression.Constant(16, typeof(int));  
Expression e2 = Expression.GreaterThan(left, right);  
  
// Combine the expression trees to create an expression tree that represents the  
// expression '(company.ToLower() == "coho winery" || company.Length > 16)'.  
Expression predicateBody = Expression.OrElse(e1, e2);  
  
// Create an expression tree that represents the expression  
// 'queryableData.Where(company => (company.ToLower() == "coho winery" || company.Length > 16))'  
MethodCallExpression whereCallExpression = Expression.Call(  
    typeof(Queryable),  
    "Where",  
    new Type[] { queryableData.ElementType },  
    queryableData.Expression,  
    Expression.Lambda<Func<string, bool>>(predicateBody, new ParameterExpression[] { pe }));  
// ***** End Where *****  
  
// ***** OrderBy(company => company) *****  
// Create an expression tree that represents the expression  
// 'whereCallExpression.OrderBy(company => company)'  
MethodCallExpression orderByCallExpression = Expression.Call(  
    typeof(Queryable),  
    "OrderBy",  
    new Type[] { queryableData.ElementType, queryableData.ElementType },  
    whereCallExpression,  
    Expression.Lambda<Func<string, string>>(pe, new ParameterExpression[] { pe }));  
// ***** End OrderBy *****  
  
// Create an executable query from the expression tree.  
IQueryable<string> results = queryableData.Provider.CreateQuery<string>(orderByCallExpression);  
  
// Enumerate the results.  
foreach (string company in results)  
    Console.WriteLine(company);  
  
/*  This code produces the following output:  
  
    Blue Yonder Airlines  
    City Power & Light  
    Coho Winery  
    Consolidated Messenger  
    Graphic Design Institute  
    Humongous Insurance  
    Lucerne Publishing  
    Northwind Traders  
    The Phone Company  
    Wide World Importers  
*/  
```  
  
 <span data-ttu-id="ce4cc-119">이 코드는 `Queryable.Where` 메서드에 전달되는 조건자에 고정 개수의 식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-119">This code uses a fixed number of expressions in the predicate that is passed to the `Queryable.Where` method.</span></span> <span data-ttu-id="ce4cc-120">그러나 사용자 입력에 따라 달라지는 가변 개수의 조건자 식을 결합하는 응용 프로그램을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-120">However, you can write an application that combines a variable number of predicate expressions that depends on the user input.</span></span> <span data-ttu-id="ce4cc-121">사용자 입력에 따라 쿼리에서 호출되는 표준 쿼리 연산자를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-121">You can also vary the standard query operators that are called in the query, depending on the input from the user.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ce4cc-122">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ce4cc-122">Compiling the Code</span></span>  
  
-   <span data-ttu-id="ce4cc-123">**콘솔 응용 프로그램** 프로젝트를 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-123">Create a new **Console Application** project.</span></span>  
  
-   <span data-ttu-id="ce4cc-124">아직 참조되지 않은 경우 System.Core.dll에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-124">Add a reference to System.Core.dll if it is not already referenced.</span></span>  
  
-   <span data-ttu-id="ce4cc-125">System.Linq.Expressions 네임스페이스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-125">Include the System.Linq.Expressions namespace.</span></span>  
  
-   <span data-ttu-id="ce4cc-126">예제의 코드를 복사하여 `Main` 메서드에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-126">Copy the code from the example and paste it into the `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce4cc-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce4cc-127">See Also</span></span>

- [<span data-ttu-id="ce4cc-128">식 트리(C#)</span><span class="sxs-lookup"><span data-stu-id="ce4cc-128">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)  
- [<span data-ttu-id="ce4cc-129">방법: 식 트리 실행(C#)</span><span class="sxs-lookup"><span data-stu-id="ce4cc-129">How to: Execute Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)  
- [<span data-ttu-id="ce4cc-130">방법: 런타임에 동적으로 조건자 필터 지정</span><span class="sxs-lookup"><span data-stu-id="ce4cc-130">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)
