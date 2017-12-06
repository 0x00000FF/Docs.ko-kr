---
title: "빠른 시작 - 클래스 소개 - C# 가이드"
description: "첫 번째 C# 프로그램을 만들고 개체 지향 개념을 살펴봅니다."
author: billwagner
ms.author: wiwagn
ms.date: 10/11/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: ad6e83d427b55482f9615e0083682bdca6c56704
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="introduction-to-classes"></a><span data-ttu-id="23b13-103">클래스 소개</span><span class="sxs-lookup"><span data-stu-id="23b13-103">Introduction to classes</span></span>

<span data-ttu-id="23b13-104">이 단원에서는 [.NET Core SDK](http://dot.net/core)와 편집기를 설치했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-104">This lesson assumes that you've installed [.NET Core SDK](http://dot.net/core), and an editor of your choice.</span></span> <span data-ttu-id="23b13-105">아직 설치하지 않은 경우 Mac 또는 Windows에서 [Visual Studio Code](https://code.visualstudio.com/) 또는 [Visual Studio](https://www.visualstudio.com/)를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="23b13-105">If you don't have one, try [Visual Studio Code](https://code.visualstudio.com/), or [Visual Studio](https://www.visualstudio.com/) on Mac or Windows.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="23b13-106">응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="23b13-106">Create your application</span></span>

<span data-ttu-id="23b13-107">터미널 창을 사용하여 **클래스**라는 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-107">Using a terminal window, create a directory named **classes**.</span></span> <span data-ttu-id="23b13-108">거기에 응용 프로그램을 빌드할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-108">You'll build your application there.</span></span> <span data-ttu-id="23b13-109">해당 디렉터리로 변경하고 콘솔 창에 `dotnet new console`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-109">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="23b13-110">이 명령은 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-110">This command creates your application.</span></span> <span data-ttu-id="23b13-111">**Program.cs**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-111">Open **Program.cs**.</span></span> <span data-ttu-id="23b13-112">다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-112">It should look like this:</span></span>

```csharp
using System;

namespace classes
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="23b13-113">이 빠른 시작에서는 은행 계좌를 나타내는 새로운 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-113">In this quick start, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="23b13-114">일반적으로 개발자는 여러 텍스트 파일에 각 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-114">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="23b13-115">그러면 프로그램의 크기가 커질 때 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-115">That makes it easier to manage as a program grows in size.</span></span>  <span data-ttu-id="23b13-116">**클래스** 디렉터리에 **BankAccount.cs**라는 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-116">Create a new file named **BankAccount.cs** in the **classes** directory.</span></span> 

<span data-ttu-id="23b13-117">이 파일에는 ***은행 계좌***의 정의가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-117">This file will contain the deefinition of a ***bank account***.</span></span> <span data-ttu-id="23b13-118">개체 지향 프로그래밍은 ***클래스*** 형태로 형식을 생성하여 코드를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-118">Object Oriented programming organizes code by creating types in the form of ***classes***.</span></span> <span data-ttu-id="23b13-119">이러한 클래스에는 특정 엔티티를 나타내는 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-119">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="23b13-120">`BankAccount` 클래스는 은행 계좌를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-120">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="23b13-121">코드는 메서드 및 속성을 통해 특정 작업을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-121">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="23b13-122">이 빠른 시작에서 은행 계좌는 다음 동작을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-122">In this quick start, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="23b13-123">은행 계좌를 고유하게 식별하는 10자리 숫자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-123">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="23b13-124">소유자의 이름을 저장하는 문자열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-124">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="23b13-125">잔액을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-125">The balance can be retrieved.</span></span>
1. <span data-ttu-id="23b13-126">예금을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-126">It accepts deposits.</span></span>
1. <span data-ttu-id="23b13-127">인출을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-127">It accepts withdrawals.</span></span>
1. <span data-ttu-id="23b13-128">초기 잔액은 양수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-128">The initial balance must be positive.</span></span>
1. <span data-ttu-id="23b13-129">인출로 인해 음의 잔액이 발생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-129">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="23b13-130">은행 계좌 형식 정의</span><span class="sxs-lookup"><span data-stu-id="23b13-130">Define the bank account type</span></span>

<span data-ttu-id="23b13-131">동작을 정의하는 클래스의 기본 사항을 만들어 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-131">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="23b13-132">다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-132">It would look like this:</span></span>

```csharp
using System;

namespace classes
{
    public class BankAccount
    {
        public string Number { get; }
        public string Owner { get; set; }
        public decimal Balance { get; }

        public void MakeDeposit(decimal amount, DateTime date, string note)
        {
        }

        public void MakeWithdrawal(decimal amount, DateTime date, string payee, string note)
        {
        }
    }
}
```

<span data-ttu-id="23b13-133">계속하기 전에 빌드한 내용을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-133">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="23b13-134">`namespace` 선언은 코드를 논리적으로 구성하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-134">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="23b13-135">이 빠른 시작은 비교적 작으므로 하나의 네임스페이스에 모든 코드를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-135">This quick start is relatively small, so you'll put all the code in one namespace.</span></span> 

<span data-ttu-id="23b13-136">`public class BankAccount`는 생성하는 클래스 또는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-136">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="23b13-137">클래스 선언 뒤에 오는 `{` 및 `}`의 모든 항목은 클래스의 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-137">Everything inside the `{` and `}` that follows the class declaration defines the behavior of the class.</span></span> <span data-ttu-id="23b13-138">`BankAccount` 클래스의 ***멤버***가 다섯 개 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-138">There are five ***members*** of the `BankAccount` class.</span></span> <span data-ttu-id="23b13-139">첫 번째 세 개는 ***속성***입니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-139">The first three are ***properties***.</span></span> <span data-ttu-id="23b13-140">속성은 데이터 요소이며 유효성 검사 또는 기타 규칙을 적용하는 코드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-140">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="23b13-141">마지막 두 개는 ***메서드***입니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-141">The last two are ***methods***.</span></span> <span data-ttu-id="23b13-142">메서드는 단일 함수를 수행하는 코드 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-142">Methods are blocks of code that peform a single function.</span></span> <span data-ttu-id="23b13-143">각 멤버의 이름을 읽으면 사용자 또는 다른 개발자가 클래스가 수행하는 작업을 이해하기에 충분한 정보를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-143">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="23b13-144">새 계좌 개설</span><span class="sxs-lookup"><span data-stu-id="23b13-144">Open a new account</span></span>

<span data-ttu-id="23b13-145">구현할 첫 번째 기능은 은행 계좌 개설 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-145">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="23b13-146">고객이 계좌를 개설할 때 초기 잔액과 해당 계좌 소유자에 대한 정보를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-146">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span> 

<span data-ttu-id="23b13-147">`BankAccount` 형식의 새 개체를 생성하는 것은 해당 값을 지정하는 ***생성자***를 정의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-147">Creating a new object of the `BankAccount` type means defining a ***constructor*** that assigns those values.</span></span> <span data-ttu-id="23b13-148">***생성자***는 클래스와 이름이 같은 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-148">A ***constructor*** is a member that has the same name as the class.</span></span> <span data-ttu-id="23b13-149">생성자는 해당 클래스 형식의 개체를 초기화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-149">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="23b13-150">`BankAccount` 형식에 다음 생성자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-150">Add the following constructor to the `BankAccount` type:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="23b13-151">생성자는 [`new`](../language-reference/keywords/new.md)를 사용하여 개체를 만들 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-151">Constructors are called when you create an object using [`new`](../language-reference/keywords/new.md).</span></span> <span data-ttu-id="23b13-152">***program.cs***의 `Console.WriteLine("Hello World!");` 줄을 다음 줄로 바꿉니다(`<name>`을 사용자의 이름으로 바꿈).</span><span class="sxs-lookup"><span data-stu-id="23b13-152">Replace the line `Console.WriteLine("Hello World!");` in ***program.cs*** with the following line (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="23b13-153">`dotnet run`을 입력하고 어떤 일이 일어나는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-153">Type `dotnet run` to see what happens.</span></span>  

<span data-ttu-id="23b13-154">계좌 번호가 공백인가요?</span><span class="sxs-lookup"><span data-stu-id="23b13-154">Did you notice that the account number is blank?</span></span> <span data-ttu-id="23b13-155">이를 수정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-155">It's time to fix that.</span></span> <span data-ttu-id="23b13-156">개체가 생성될 때 계좌 번호를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-156">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="23b13-157">그러나 계좌 번호 생성은 호출자의 책임이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-157">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="23b13-158">`BankAccount` 클래스 코드는 새 계좌 번호를 지정하는 방법을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-158">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="23b13-159">이를 수행하는 간단한 방법은 10자리 숫자로 시작하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-159">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="23b13-160">새 계좌가 생성될 때마다 숫자가 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-160">Increment it when each new account is created.</span></span> <span data-ttu-id="23b13-161">마지막으로, 개체가 생성될 때 현재 계좌 번호를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-161">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="23b13-162">`BankAccount` 클래스에 다음 멤버 선언을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-162">Add the following member declaration to the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="23b13-163">이는 데이터 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-163">This is a data member.</span></span> <span data-ttu-id="23b13-164">이것은 `private`입니다. 즉 `BankAccount` 클래스 내의 코드로만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-164">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="23b13-165">이는 전용 구현(계좌 번호가 생성되는 방법)과 공공 책임(계좌 번호를 가지는 것 등)을 구분하는 방법입니다. 생성자에 다음 두 줄을 추가하여 계좌 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-165">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated.) Add the following two lines to the constructor to assign the account number:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="23b13-166">`dotnet run`을 입력하여 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-166">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="23b13-167">예금 및 인출 만들기</span><span class="sxs-lookup"><span data-stu-id="23b13-167">Create deposits and withdrawals</span></span>

<span data-ttu-id="23b13-168">은행 계좌 클래스는 제대로 작동하려면 예금과 인출을 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-168">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="23b13-169">계좌의 모든 트랜잭션에 대한 저널을 만들어 예금과 인출을 구현하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-169">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="23b13-170">단순히 각 트랜잭션의 잔액을 업데이트하는 것보다 많은 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-170">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="23b13-171">기록을 사용하여 모든 트랜잭션을 감사하고 일별 잔액을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-171">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="23b13-172">필요한 경우 모든 트랜잭션의 기록에서 잔액을 계산함으로써, 수정된 단일 트랜잭션의 오류가 다음 계산의 잔액에 올바르게 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-172">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="23b13-173">트랜잭션을 나타내는 새 형식을 생성해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-173">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="23b13-174">이는 책임이 없는 단순 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-174">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="23b13-175">몇 가지 속성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-175">It needs a few properties.</span></span> <span data-ttu-id="23b13-176">***Transaction.cs***라는 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-176">Create a new file named ***Transaction.cs***.</span></span> <span data-ttu-id="23b13-177">파일에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-177">Add the following code to it:</span></span>

[!code-csharp[Transaction](../../../samples/csharp/classes-quickstart/Transaction.cs "Transaction declaration")]

<span data-ttu-id="23b13-178">이제 `Transaction` 개체의 <xref:System.Collections.Generic.List%601>를 `BankAccount` 클래스에 추가하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-178">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="23b13-179">다음 선언을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-179">Add the following declaration:</span></span>

[!code-csharp[TransactionDecl](../../../samples/csharp/classes-quickstart/BankAccount.cs#TransactionDeclaration "Transaction declaration")]

<span data-ttu-id="23b13-180"><xref:System.Collections.Generic.List%601> 클래스를 사용하려면 다른 네임스페이스를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-180">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="23b13-181">**BankAccount.cs**의 시작 부분에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-181">Add the following at the beginning of **BankAccount.cs**:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="23b13-182">이제 `Balance`를 보고하는 방법을 변경해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-182">Now, let's change how the `Balance` is reported.</span></span>  <span data-ttu-id="23b13-183">모든 트랜잭션의 값을 합하여 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-183">It can be found by summing the values of all transactions.</span></span> <span data-ttu-id="23b13-184">`BankAccount` 클래스에서 `Balance`의 선언을 다음과 같이 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-184">Modify the declaration of `Balance` in the `BankAccount` class to the following:</span></span>

[!code-csharp[BalanceComputation](../../../samples/csharp/classes-quickstart/BankAccount.cs#BalanceComputation "Computing the balance")]

<span data-ttu-id="23b13-185">이 예제에서는 ***속성***의 중요한 측면을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-185">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="23b13-186">이제 다른 프로그래머가 값을 요청할 때 잔액을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-186">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="23b13-187">계산은 모든 트랜잭션을 열거하고 합계를 현재 잔액으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-187">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="23b13-188">다음으로 `MakeDeposit` 및 `MakeWithdrawal` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-188">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="23b13-189">이러한 메서드는 최종 두 규칙을 적용합니다. 초기 잔액은 양수여야 하고 인출로 인해 음수의 잔액이 발생되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-189">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span> 

<span data-ttu-id="23b13-190">이는 ***예외***의 개념을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-190">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="23b13-191">메서드가 작업을 성공적으로 완료할 수 없음을 나타내는 일반적인 방법은 예외를 throw하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-191">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="23b13-192">예외 형식 및 관련 메시지는 오류를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-192">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="23b13-193">여기에서 `MakeDeposit` 메서드는 인출 금액이 음수인 경우 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-193">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="23b13-194">인출 금액이 음수이거나 인출 적용 결과로 음수의 잔액이 발생하는 경우 `MakeWithdrawal` 메서드는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-194">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance:</span></span>

[!code-csharp[DepositAndWithdrawal](../../../samples/csharp/classes-quickstart/BankAccount.cs#DepositAndWithdrawal "Make deposits and withdrawals")]

<span data-ttu-id="23b13-195">[`throw`](../language-reference/keywords/throw.md) 문은 예외를 **throw**합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-195">The [`throw`](../language-reference/keywords/throw.md) statement **throws** an exception.</span></span> <span data-ttu-id="23b13-196">현재 메서드 실행이 끝나고 일치하는 `catch` 블록이 발견되면 메서드가 다시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-196">Execution of the current method ends, and will resume when a matching `catch` block is found.</span></span> <span data-ttu-id="23b13-197">`catch` 블록을 추가하여 나중에 이 코드를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-197">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="23b13-198">생성자는 잔액을 직접 업데이트하지 않고 초기 트랜잭션을 추가하도록 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-198">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="23b13-199">`MakeDeposit` 메서드를 이미 작성했으므로 생성자에서 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-199">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="23b13-200">완성된 생성자는 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-200">The finished constructor should look like this:</span></span>

[!code-csharp[Constructor](../../../samples/csharp/classes-quickstart/BankAccount.cs#Constructor "The final version of the constructor")]

<span data-ttu-id="23b13-201"><xref:System.DateTime.Now?displayProperty=nameWithType>은 현재 날짜 및 시간을 반환하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-201"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="23b13-202">`Main` 메서드에 예금 및 인출을 몇 개 추가하여 다음을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-202">Test this by adding a few deposits and withdrawals in your `Main` method:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="23b13-203">다음으로 음수 잔액을 사용하여 계정을 생성하여 오류 조건을 알아보는 테스트를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-203">Next, test that you are catching error conditions by trying to create an account with a negative balance:</span></span>

```csharp
// Test that the initial balances must be positive:
try {
    var invalidAccount = new BankAccount("invalid", -55);
} catch (ArgumentOutOfRangeException e)
{
    Console.WriteLine("Exception caught creating account with negative balance");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="23b13-204">[`try` 및 `catch` 문](../language-reference/keywords/try-catch.md)을 사용하여 예외를 throw할 수 있는 코드 블록을 표시하고 예상한 오류를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-204">You use the [`try` and `catch` statements](../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions, and to catch those errors that you expect.</span></span> <span data-ttu-id="23b13-205">동일한 기술을 사용하여 음수 잔액에 대해 throw되는 코드를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-205">You can use the same technique to test the code that throws for a negative balance:</span></span>

```csharp
// Test for a negative balance
try {
    account.MakeWithdrawal(750, DateTime.Now, "Attempt to overdraw");
} catch (InvalidOperationException e)
{
    Console.WriteLine("Exception caught trying to overdraw");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="23b13-206">파일을 저장하고 `dotnet run`을 입력하여 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="23b13-206">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="23b13-207">과제 - 모든 트랜잭션 기록</span><span class="sxs-lookup"><span data-stu-id="23b13-207">Challenge - log all transactions</span></span>

<span data-ttu-id="23b13-208">이 빠른 시작을 완료하기 위해 트랜잭션 기록에 대해 `string`을 생성하는 `GetAccountHistory` 메서드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-208">To finish this quick start, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="23b13-209">`BankAccount` 형식에 이 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-209">add this method to the `BankAccount` type:</span></span>

[!code-csharp[History](../../../samples/csharp/classes-quickstart/BankAccount.cs#History "Display transaction history")]

<span data-ttu-id="23b13-210"><xref:System.Text.StringBuilder> 클래스를 사용하여 각 트랜잭션에 대해 한 줄을 포함하는 문자열의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-210">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="23b13-211">이전 빠른 시작에서 문자열 형식 지정 코드를 살펴봤습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-211">You've seen the string formatting code earlier in these quick starts.</span></span> <span data-ttu-id="23b13-212">새 문자는 `\t`입니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-212">One new character is `\t`.</span></span> <span data-ttu-id="23b13-213">이 새 문자는 탭을 삽입하여 출력 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-213">That inserts a tab to format the output.</span></span>

<span data-ttu-id="23b13-214">**Program.cs**에서 테스트하려면 이 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-214">Add this line to test it in **Program.cs**:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="23b13-215">`dotnet run`을 입력하여 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-215">Type `dotnet run` to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="23b13-216">다음 단계</span><span class="sxs-lookup"><span data-stu-id="23b13-216">Next Steps</span></span>

<span data-ttu-id="23b13-217">잘 모르겠는 경우 [GitHub 리포지토리](https://github.com/dotnet/docs/tree/master/samples/csharp/classes-quickstart/)에서 이 빠른 시작의 소스를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-217">If you got stuck, you can see the source for this quick start [in our GitHub repo](https://github.com/dotnet/docs/tree/master/samples/csharp/classes-quickstart/)</span></span>

<span data-ttu-id="23b13-218">축하합니다. 모든 빠른 시작을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="23b13-218">Congratulations, you've finished all our Quick Starts.</span></span> <span data-ttu-id="23b13-219">더 자세히 학습하려면 [자습서](../tutorials/index.md)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="23b13-219">If you're eager to learn more, try our [tutorials](../tutorials/index.md)</span></span>
