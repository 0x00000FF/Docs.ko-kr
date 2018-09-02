---
title: 정책을 사용한 주문 처리
ms.date: 03/30/2017
ms.assetid: 66833724-dc36-4fad-86b0-59ffeaa3ba6a
ms.openlocfilehash: b927d8e7090f96b22c0510f9651070ab999c91be
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43398372"
---
# <a name="order-processing-with-policy"></a><span data-ttu-id="0bd05-102">정책을 사용한 주문 처리</span><span class="sxs-lookup"><span data-stu-id="0bd05-102">Order Processing with Policy</span></span>
<span data-ttu-id="0bd05-103">Order Processing Policy 샘플에서는 Windows WF(Workflow Foundation )의 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]에 도입된 몇 가지 주요 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-103">The Order Processing Policy sample demonstrates some of the key features introduced in the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] of the Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="0bd05-104">다음은 WF 규칙 엔진에 새로 추가된 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-104">The following functionality is new for the WF rules engine:</span></span>  
  
-   <span data-ttu-id="0bd05-105">연산자 오버로드 지원</span><span class="sxs-lookup"><span data-stu-id="0bd05-105">Support for operator overloading.</span></span>  
  
-   <span data-ttu-id="0bd05-106">사용자가 WF 규칙에서 새 개체 및 배열을 만들 수 있는 `new` 연산자 지원</span><span class="sxs-lookup"><span data-stu-id="0bd05-106">Support for the `new` operator, allowing users to create new objects and arrays from WF rules.</span></span>  
  
-   <span data-ttu-id="0bd05-107">C# 코딩 스타일과 호환되는 WF 규칙에서 확장 메서드를 호출할 때 사용자 환경을 만드는 확장 메서드 지원</span><span class="sxs-lookup"><span data-stu-id="0bd05-107">Support for extension methods to make the user experience in calling extension methods from WF rules compatible with C# coding styles.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bd05-108">이 샘플을 실행하려면 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]가 설치되어 빌드 및 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-108">This sample requires that [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] is installed to build and run.</span></span> <span data-ttu-id="0bd05-109">프로젝트 및 솔루션 파일을 열려면 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-109">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] is required to open the project and solution files.</span></span>  
  
 <span data-ttu-id="0bd05-110">이 샘플에서는 번호가 매겨진 사용 가능한 항목 목록으로 구성된 고객 주문과 우편 번호를 입력하는 `OrderProcessingPolicy` 프로젝트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-110">The sample demonstrates an `OrderProcessingPolicy` project in which a customer order, which consists of a numbered list of available items and a zip code, is entered.</span></span> <span data-ttu-id="0bd05-111">두 항목이 모두 올바르면 주문이 성공적으로 처리되고, 그렇지 않으면 정책에서 오버로드된 `+` 연산자와 미리 정의된 확장 메서드를 사용하여 사용자에게 오류를 알리는 오류 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-111">The order is processed successfully if both entries are correct; otherwise, the policy creates error objects, utilizing an overloaded `+` operator and a predefined extension method to inform the user of the errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bd05-112">확장 메서드에 대 한 자세한 내용은 참조 하세요. [C# 버전 3.0 사양](https://go.microsoft.com/fwlink/?LinkId=95402)합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-112">For more information about extension methods, see [C# Version 3.0 Specification](https://go.microsoft.com/fwlink/?LinkId=95402).</span></span>  
  
 <span data-ttu-id="0bd05-113">이 샘플은 다음과 같은 프로젝트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-113">The sample is comprised of the following projects:</span></span>  
  
-   `OrderErrorLibrary`  
  
     <span data-ttu-id="0bd05-114">`OrderErrorLibrary`는 `OrderError` 및 `OrderErrorCollection` 클래스를 정의하는 클래스 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-114">The `OrderErrorLibrary` is a class library that defines `OrderError` and `OrderErrorCollection` classes.</span></span> <span data-ttu-id="0bd05-115">`OrderError` 인스턴스는 잘못된 입력을 제공할 때 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-115">An `OrderError` instance is created when an invalid input is entered.</span></span> <span data-ttu-id="0bd05-116">또한 이 라이브러리는 `OrderErrorCollection`의 모든 `ErrorText` 개체에 대해 `OrderError` 속성을 출력하는 `OrderErrorCollection` 클래스에서 확장 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-116">The library also provides an extension method on the `OrderErrorCollection` class that outputs the `ErrorText` property on all `OrderError` objects in the `OrderErrorCollection`.</span></span>  
  
-   `OrderProcessingPolicy`  
  
     <span data-ttu-id="0bd05-117">`OrderProcessingPolicy` 프로젝트는 단일 `PolicyFromFile` 활동을 정의하는 WF 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-117">The `OrderProcessingPolicy` project is a WF console application that defines a single `PolicyFromFile` activity.</span></span> <span data-ttu-id="0bd05-118">활동에는 다음과 같은 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-118">The activity has the following rules:</span></span>  
  
    -   `invalidItemNum`  
  
         <span data-ttu-id="0bd05-119">이 규칙은 항목 번호가 1에서 6 사이에 있는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-119">This rule validates that the item number is between 1 and 6, inclusive.</span></span> <span data-ttu-id="0bd05-120">항목 번호가 유효한 범위 내에 있으면 규칙에서 아무 작업도 수행하지 않고 콘솔에 출력만 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-120">If the item number is within the valid range, the rule does nothing (other than printing to the console).</span></span> <span data-ttu-id="0bd05-121">항목 번호가 1에서 6 사이에 없으면 `invalidItemNum` 규칙에서 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-121">If the item number is not between 1 and 6, the `invalidItemNum` rule does the following:</span></span>  
  
        1.  <span data-ttu-id="0bd05-122">새 `OrderError` 개체를 만들어 입력된 항목 번호를 전달하고 개체에서 `ErrorText` 및 `CustomerName` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-122">Creates a new `OrderError` object, passing it the item number entered, and sets the `ErrorText` and `CustomerName` properties on the object.</span></span>  
  
        2.  <span data-ttu-id="0bd05-123">`invalidItemNumErrorCollection` 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-123">Creates an `invalidItemNumErrorCollection` object.</span></span>  
  
        3.  <span data-ttu-id="0bd05-124">새로 만든 `OrderError` 인스턴스를 `invalidItemNumErrorCollection`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-124">Adds the newly-created `OrderError` instance to the `invalidItemNumErrorCollection`.</span></span>  
  
         <span data-ttu-id="0bd05-125">이 규칙은 규칙 내에서 개체를 인스턴스화하는 데 사용할 수 있는 `new` 연산자에 대한 지원을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-125">This demonstrates support for the `new` operator, with which you can instantiate objects inside rules.</span></span>  
  
    -   `invalidZip`  
  
         <span data-ttu-id="0bd05-126">이 규칙은 우편 번호가 5자리이며 600에서 99998 사이의 범위 내에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-126">This rule validates that the zip code has 5 digits, and is within the range 600 to 99998.</span></span> <span data-ttu-id="0bd05-127">우편 번호가 유효한 범위 내에 있으면 규칙에서 아무 작업도 수행하지 않고 콘솔에 출력만 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-127">If the zip code is within the valid range, the rule does nothing (other than printing to the console).</span></span> <span data-ttu-id="0bd05-128">우편 번호의 길이가 5보다 작거나 00600에서 99998 사이에 없으면 `invalidZip` 규칙에서 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-128">If the length of the zip code is less than 5, or the zip code is not between 00600 and 99998, the `invalidZip` rule does the following:</span></span>  
  
        1.  <span data-ttu-id="0bd05-129">`OrderError` 개체를 만들어 입력된 우편 번호를 전달하고 개체에서 `ErrorText` 및 `CustomerName` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-129">Creates an `OrderError` object, passing it the zip code entered, and sets the `ErrorText` and `CustomerName` properties on the object.</span></span>  
  
        2.  <span data-ttu-id="0bd05-130">`invalidZipCodeErrorCollection` 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-130">Creates an `invalidZipCodeErrorCollection` object.</span></span>  
  
        3.  <span data-ttu-id="0bd05-131">새로 만든 `OrderError` 인스턴스를 새로 만든 `invalidZipCodeErrorCollection`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-131">Adds the newly-created `OrderError` instance to the newly-created `invalidZipCodeErrorCollection`.</span></span>  
  
         <span data-ttu-id="0bd05-132">이 규칙도 규칙 내에서 개체를 인스턴스화하는 데 사용할 수 있는 `new` 연산자에 대한 지원을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-132">This rule again demonstrates support for the `new` operator, which allows you to instantiate objects inside rules.</span></span>  
  
    -   `displayErrors`  
  
         <span data-ttu-id="0bd05-133">이 규칙은 앞의 두 규칙에 의해 두 `OrderErrorCollection` 개체인 `invalidItemNumErrorCollection`과 `invalidIZipCodeErrorCollection`에 추가된 오류가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-133">This rule checks to see if there were any errors added by the previous two rules in the two `OrderErrorCollection` objects `invalidItemNumErrorCollection` and `invalidIZipCodeErrorCollection`.</span></span> <span data-ttu-id="0bd05-134">오류가 있는 경우(`invalidItemNumErrorCollection` 또는 `invalidZipCodeErrorCollection`이 `null`이 아닌 경우) 규칙에서 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-134">If there were errors (either `invalidItemNumErrorCollection` or `invalidZipCodeErrorCollection` is not `null`), the rule does the following:</span></span>  
  
        1.  <span data-ttu-id="0bd05-135">오버 로드 된 호출 `+` 연산자의 내용을 복사할 `invalidItemNumErrorCollection` 및 `invalidZipCodeErrorCollection` 에 `invalidOrdersCollection``OrderErrorCollection` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="0bd05-135">Calls the overloaded `+` operator to copy the contents of `invalidItemNumErrorCollection` and `invalidZipCodeErrorCollection` to an `invalidOrdersCollection``OrderErrorCollection` instance.</span></span>  
  
        2.  <span data-ttu-id="0bd05-136">`PrintOrderErrors`에서 `invalidOrdersCollection` 확장 메서드를 호출하고 `ErrorText`의 모든 `orderError` 개체에서 `invalidOrdersCollection` 속성을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-136">Calls the `PrintOrderErrors` extension method on `invalidOrdersCollection` and outputs the `ErrorText` property on all `orderError` objects in `invalidOrdersCollection`.</span></span>  
  
 <span data-ttu-id="0bd05-137">`+`의 오버로드된 `OrderErrorCollection` 연산자는 `OrderErrorCollection` 프로젝트의 `OrderErrorLibrary` 클래스에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-137">The overloaded operator `+` on the `OrderErrorCollection` is defined in the `OrderErrorCollection` class, in the `OrderErrorLibrary` project.</span></span> <span data-ttu-id="0bd05-138">이 연산자는 두 개의 `OrderErrorCollection` 개체를 사용하여 하나의 `OrderErrorCollection` 개체로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-138">It takes two `OrderErrorCollection` objects and combines them into one `OrderErrorCollection` object.</span></span>  
  
 <span data-ttu-id="0bd05-139">`PrintOrderErrors` 확장 메서드도 `OrderErrorLibrary` 프로젝트에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-139">The `PrintOrderErrors` extension method is also defined in the `OrderErrorLibrary` project.</span></span> <span data-ttu-id="0bd05-140">확장 메서드는 개발자가 클래스를 파생하거나 원래 형식을 다시 컴파일하지 않고도 기존 CLR 형식의 공용 계약에 새 메서드를 추가할 수 있는 새로운 C# 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-140">Extension methods are a new C# feature that enables developers to add new methods to the public contract of an existing CLR type, without having to derive a class from it or recompile the original type.</span></span>  
  
 <span data-ttu-id="0bd05-141">샘플을 실행하면 이름, 구입할 항목의 항목 번호 및 우편 번호를 입력하라는 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-141">When you run the sample you are prompted to enter a name, the item number of the item to be purchased, and a zip code.</span></span> <span data-ttu-id="0bd05-142">그런 다음 정책 활동에 정의된 규칙에서 이 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-142">This information is then verified by the rules defined in the policy activity.</span></span> <span data-ttu-id="0bd05-143">다음은 프로그램의 출력 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-143">The following is sample output from the program.</span></span>  
  
```  
Please enter your name: John  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 1  
  
Please enter your 5-Digit zip code: 98102  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Thank you for your order, it has been processed.  
  
Workflow Completed  
Another Order? (Y/N): y  
  
Please enter your name: Joel  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 8  
  
Please enter your 5-Digit zip code: 0000  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Your order contains the following error(s)  
  
Error: No item number found. Please choose an available item.  
Error: Invalid zip code. Please choose a zip code between 00600 and 99998.  
  
Workflow Completed  
Another Order? (Y/N): n  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0bd05-144">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="0bd05-144">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="0bd05-145">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 OrderProcessingPolicy.sln 프로젝트 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-145">Open the OrderProcessingPolicy.sln project file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="0bd05-146">솔루션에는 `OrderErrorLibrary` 및 `OrderProcessingPolicy`라는 두 개의 다른 프로젝트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-146">There are two different projects in the solution: `OrderErrorLibrary` and `OrderProcessingPolicy`.</span></span> <span data-ttu-id="0bd05-147">`OrderProcessingPolicy` 프로젝트에서는 `OrderErrorLibrary`에 정의된 클래스 및 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-147">The `OrderProcessingPolicy` project uses classes and methods defined in the `OrderErrorLibrary`.</span></span>  
  
3.  <span data-ttu-id="0bd05-148">프로젝트를 모두 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-148">Build all projects.</span></span>  
  
4.  <span data-ttu-id="0bd05-149">**실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-149">Click **Run**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0bd05-150">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-150">The samples may already be installed on your computer.</span></span> <span data-ttu-id="0bd05-151">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0bd05-151">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0bd05-152">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="0bd05-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0bd05-153">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd05-153">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\OrderProcessingPolicy`