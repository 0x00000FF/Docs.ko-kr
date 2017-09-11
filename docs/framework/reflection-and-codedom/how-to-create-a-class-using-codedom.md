---
title: "방법: CodeDOM을 사용하여 클래스 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Code Document Object Model, graphs
- Code Document Object Model, creating classes
- graphing with CodeDOM
- CodeDOM, creating classes
- CodeDOM, graphs
ms.assetid: 0ceb70fe-36e1-49bb-922b-e9f615c20a14
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3876ed881d98b4ee0bdb66f43de3de939111d45d
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-class-using-codedom"></a><span data-ttu-id="478ce-102">방법: CodeDOM을 사용하여 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="478ce-102">How to: Create a Class Using CodeDOM</span></span>
<span data-ttu-id="478ce-103">다음 절차에서는 필드 2개, 속성 3개, 메서드, 생성자 및 진입점을 포함하는 클래스를 생성하는 CodeDOM 그래프를 만들고 컴파일하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-103">The following procedures illustrate how to create and compile a CodeDOM graph that generates a class containing two fields, three properties, a method, a constructor, and an entry point.</span></span>  
  
1.  <span data-ttu-id="478ce-104">CodeDOM 코드를 사용하여 클래스에 대한 소스 코드를 생성하는 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-104">Create a console application that will use CodeDOM code to generate the source code for a class.</span></span>  
  
     <span data-ttu-id="478ce-105">이 예제에서 생성하는 클래스의 이름은 `Sample`이고, 생성된 코드는 SampleCode 파일의 `CodeDOMCreatedClass` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-105">In this example, the generating class is named `Sample`, and the generated code is a class named `CodeDOMCreatedClass` in a file named SampleCode.</span></span>  
  
2.  <span data-ttu-id="478ce-106">생성하는 클래스에서 CodeDOM 그래프를 초기화하고 CodeDOM 메서드를 사용하여 생성된 클래스의 멤버, 생성자 및 진입점(`Main` 메서드)을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-106">In the generating class, initialize the CodeDOM graph and use CodeDOM methods to define the members, constructor, and entry point (`Main` method) of the generated class.</span></span>  
  
     <span data-ttu-id="478ce-107">이 예제에서 생성된 클래스에는 필드 2개, 속성 3개, 생성자, 메서드 및 `Main` 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-107">In this example, the generated class has two fields, three properties, a constructor, a method, and a `Main` method.</span></span>  
  
3.  <span data-ttu-id="478ce-108">생성하는 클래스에서 언어별 코드 공급자를 만들고 해당 <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> 메서드를 호출하여 그래프에서 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-108">In the generating class, create a language-specific code provider and call its <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method to generate the code from the graph.</span></span>  
  
4.  <span data-ttu-id="478ce-109">응용 프로그램을 컴파일 및 실행하여 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-109">Compile and execute the application to generate the code.</span></span>  
  
     <span data-ttu-id="478ce-110">이 예제에서 생성된 코드는 SampleCode 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-110">In this example, the generated code is in a file named SampleCode.</span></span> <span data-ttu-id="478ce-111">해당 코드를 컴파일 및 실행하여 샘플 출력을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-111">Compile and execute that code to see the sample output.</span></span>  
  
### <a name="to-create-the-application-that-will-execute-the-codedom-code"></a><span data-ttu-id="478ce-112">CodeDOM 코드를 실행할 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="478ce-112">To create the application that will execute the CodeDOM code</span></span>  
  
-   <span data-ttu-id="478ce-113">CodeDOM 코드를 포함하는 콘솔 응용 프로그램 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-113">Create a console application class to contain the CodeDOM code.</span></span> <span data-ttu-id="478ce-114">클래스에서 어셈블리(<xref:System.CodeDom.CodeCompileUnit>) 및 클래스(<xref:System.CodeDom.CodeTypeDeclaration>)를 참조하는 데 사용할 전역 필드를 정의하고 생성된 소스 파일의 이름을 지정한 다음 `Main` 메서드를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-114">Define the global fields that are to be used in the class to reference the assembly (<xref:System.CodeDom.CodeCompileUnit>) and class (<xref:System.CodeDom.CodeTypeDeclaration>), specify the name of the generated source file, and declare the `Main` method.</span></span>  
  
     <span data-ttu-id="478ce-115">[!code-csharp[CodeDOM Class Sample Main#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample Main/CS/program.cs#1)]  [!code-vb[CodeDOM Class Sample Main#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample Main/VB/program.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="478ce-115">[!code-csharp[CodeDOM Class Sample Main#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample Main/CS/program.cs#1)]  [!code-vb[CodeDOM Class Sample Main#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample Main/VB/program.vb#1)]</span></span>  
  
### <a name="to-initialize-the-codedom-graph"></a><span data-ttu-id="478ce-116">CodeDOM 그래프를 초기화하려면</span><span class="sxs-lookup"><span data-stu-id="478ce-116">To initialize the CodeDOM graph</span></span>  
  
-   <span data-ttu-id="478ce-117">콘솔 응용 프로그램 클래스에 대한 생성자에서 어셈블리와 클래스를 초기화하고 적절한 선언을 CodeDOM 그래프에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-117">In the constructor for the console application class, initialize the assembly and class, and add the appropriate declarations to the CodeDOM graph.</span></span>  
  
     <span data-ttu-id="478ce-118">[!code-csharp[CodeDOM Class Sample#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#2)]  [!code-vb[CodeDOM Class Sample#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="478ce-118">[!code-csharp[CodeDOM Class Sample#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#2)]  [!code-vb[CodeDOM Class Sample#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#2)]</span></span>  
  
### <a name="to-add-members-to-the-codedom-graph"></a><span data-ttu-id="478ce-119">CodeDOM 그래프에 멤버를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="478ce-119">To add members to the CodeDOM graph</span></span>  
  
-   <span data-ttu-id="478ce-120">클래스의 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 속성에 <xref:System.CodeDom.CodeMemberField> 개체를 추가하여 CodeDOM 그래프에 필드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-120">Add fields to the CodeDOM graph by adding <xref:System.CodeDom.CodeMemberField> objects to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     <span data-ttu-id="478ce-121">[!code-csharp[CodeDOM Class Sample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#3)]  [!code-vb[CodeDOM Class Sample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#3)]</span><span class="sxs-lookup"><span data-stu-id="478ce-121">[!code-csharp[CodeDOM Class Sample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#3)]  [!code-vb[CodeDOM Class Sample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#3)]</span></span>  
  
-   <span data-ttu-id="478ce-122">클래스의 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 속성에 <xref:System.CodeDom.CodeMemberProperty> 개체를 추가하여 CodeDOM 그래프에 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-122">Add properties to the CodeDOM graph by adding <xref:System.CodeDom.CodeMemberProperty> objects to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     <span data-ttu-id="478ce-123">[!code-csharp[CodeDOM Class Sample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#4)]  [!code-vb[CodeDOM Class Sample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#4)]</span><span class="sxs-lookup"><span data-stu-id="478ce-123">[!code-csharp[CodeDOM Class Sample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#4)]  [!code-vb[CodeDOM Class Sample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#4)]</span></span>  
  
-   <span data-ttu-id="478ce-124">클래스의 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 속성에 <xref:System.CodeDom.CodeMemberMethod> 개체를 추가하여 CodeDOM 그래프에 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-124">Add a method to the CodeDOM graph by adding a <xref:System.CodeDom.CodeMemberMethod> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     <span data-ttu-id="478ce-125">[!code-csharp[CodeDOM Class Sample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#5)]  [!code-vb[CodeDOM Class Sample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#5)]</span><span class="sxs-lookup"><span data-stu-id="478ce-125">[!code-csharp[CodeDOM Class Sample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#5)]  [!code-vb[CodeDOM Class Sample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#5)]</span></span>  
  
-   <span data-ttu-id="478ce-126">클래스의 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 속성에 <xref:System.CodeDom.CodeConstructor> 개체를 추가하여 CodeDOM 그래프에 생성자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-126">Add a constructor to the CodeDOM graph by adding a <xref:System.CodeDom.CodeConstructor> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     <span data-ttu-id="478ce-127">[!code-csharp[CodeDOM Class Sample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#6)]  [!code-vb[CodeDOM Class Sample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#6)]</span><span class="sxs-lookup"><span data-stu-id="478ce-127">[!code-csharp[CodeDOM Class Sample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#6)]  [!code-vb[CodeDOM Class Sample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#6)]</span></span>  
  
-   <span data-ttu-id="478ce-128">클래스의 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 속성에 <xref:System.CodeDom.CodeEntryPointMethod> 개체를 추가하여 CodeDOM 그래프에 진입점을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-128">Add an entry point to the CodeDOM graph by adding a <xref:System.CodeDom.CodeEntryPointMethod> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     <span data-ttu-id="478ce-129">[!code-csharp[CodeDOM Class Sample#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#7)]  [!code-vb[CodeDOM Class Sample#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#7)]</span><span class="sxs-lookup"><span data-stu-id="478ce-129">[!code-csharp[CodeDOM Class Sample#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#7)]  [!code-vb[CodeDOM Class Sample#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#7)]</span></span>  
  
### <a name="to-generate-the-code-from-the-codedom-graph"></a><span data-ttu-id="478ce-130">CodeDOM 그래프에서 코드를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="478ce-130">To generate the code from the CodeDOM graph</span></span>  
  
-   <span data-ttu-id="478ce-131"><xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> 메서드를 호출하여 CodeDOM 그래프에서 소스 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-131">Generate source code from the CodeDOM graph by calling the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method.</span></span>  
  
     <span data-ttu-id="478ce-132">[!code-csharp[CodeDOM Class Sample#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#8)]  [!code-vb[CodeDOM Class Sample#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#8)]</span><span class="sxs-lookup"><span data-stu-id="478ce-132">[!code-csharp[CodeDOM Class Sample#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#8)]  [!code-vb[CodeDOM Class Sample#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#8)]</span></span>  
  
### <a name="to-create-the-graph-and-generate-the-code"></a><span data-ttu-id="478ce-133">그래프를 만들고 코드를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="478ce-133">To create the graph and generate the code</span></span>  
  
1.  <span data-ttu-id="478ce-134">앞의 단계에서 만든 메서드를 첫 번째 단계에서 정의한 `Main` 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-134">Add the methods created in the preceding steps to the `Main` method defined in the first step.</span></span>  
  
     <span data-ttu-id="478ce-135">[!code-csharp[CodeDOM Class Sample#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#9)]  [!code-vb[CodeDOM Class Sample#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#9)]</span><span class="sxs-lookup"><span data-stu-id="478ce-135">[!code-csharp[CodeDOM Class Sample#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#9)]  [!code-vb[CodeDOM Class Sample#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#9)]</span></span>  
  
2.  <span data-ttu-id="478ce-136">생성하는 클래스를 컴파일 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-136">Compile and execute the generating class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="478ce-137">예제</span><span class="sxs-lookup"><span data-stu-id="478ce-137">Example</span></span>  
 <span data-ttu-id="478ce-138">다음 코드 예제에서는 앞의 단계에서 생성한 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-138">The following code example shows the code from the preceding steps.</span></span>  
  
 <span data-ttu-id="478ce-139">[!code-csharp[CodeDOM Class Sample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#1)] [!code-vb[CodeDOM Class Sample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="478ce-139">[!code-csharp[CodeDOM Class Sample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#1)] [!code-vb[CodeDOM Class Sample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#1)]</span></span>  
  
 <span data-ttu-id="478ce-140">앞의 예제를 컴파일 및 실행하면 다음 소스 코드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-140">When the preceding example is compiled and executed, it produces the following source code.</span></span>  
  
 <span data-ttu-id="478ce-141">[!code-csharp[CodeDOM Class Sample#99](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/SampleCode.cs#99)] [!code-vb[CodeDOM Class Sample#99](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/SampleCode.vb#99)]</span><span class="sxs-lookup"><span data-stu-id="478ce-141">[!code-csharp[CodeDOM Class Sample#99](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/SampleCode.cs#99)] [!code-vb[CodeDOM Class Sample#99](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/SampleCode.vb#99)]</span></span>  
  
 <span data-ttu-id="478ce-142">생성된 소스 코드를 컴파일 및 실행하면 다음 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-142">The generated source code produces the following output when compiled and executed.</span></span>  
  
```  
The object:  
 width = 5.3,  
 height = 6.9,  
 area = 36.57  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="478ce-143">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="478ce-143">Compiling the Code</span></span>  
  
-   <span data-ttu-id="478ce-144">이 코드 예제를 성공적으로 실행하려면 `FullTrust` 권한이 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="478ce-144">This code example requires the `FullTrust` permission set to execute successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="478ce-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="478ce-145">See Also</span></span>  
 <span data-ttu-id="478ce-146">[CodeDOM 사용](../../../docs/framework/reflection-and-codedom/using-the-codedom.md) </span><span class="sxs-lookup"><span data-stu-id="478ce-146">[Using the CodeDOM](../../../docs/framework/reflection-and-codedom/using-the-codedom.md) </span></span>  
 [<span data-ttu-id="478ce-147">CodeDOM 그래프에서 소스 코드 생성 및 컴파일</span><span class="sxs-lookup"><span data-stu-id="478ce-147">Generating and Compiling Source Code from a CodeDOM Graph</span></span>](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)

