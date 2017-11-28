---
title: "방법: CodeDOM을 사용하여 XML 문서 파일 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CodeDOM, generating XML documentation
- XML documentation, creating using CodeDOM
- Code Document Object Model, generating XML documentation
ms.assetid: e3b80484-36b9-41dd-9d21-a2f9a36381dc
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7ce95b1c4f33ed500eabf3f9c7a7ac01a3a08e03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-xml-documentation-file-using-codedom"></a><span data-ttu-id="02592-102">방법: CodeDOM을 사용하여 XML 문서 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="02592-102">How to: Create an XML Documentation File Using CodeDOM</span></span>
<span data-ttu-id="02592-103">CodeDOM을 사용하여 XML 문서를 생성하는 코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02592-103">CodeDOM can be used to create code that generates XML documentation.</span></span> <span data-ttu-id="02592-104">이 프로세스에서는 XML 문서 주석이 포함된 CodeDOM 그래프를 생성하고, 코드를 생성하고, XML 문서 출력을 만드는 컴파일러 옵션을 사용하여 생성된 코드를 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02592-104">The process involves creating the CodeDOM graph that contains the XML documentation comments, generating the code, and compiling the generated code with the compiler option that creates the XML documentation output.</span></span>  
  
### <a name="to-create-a-codedom-graph-that-contains-xml-documentation-comments"></a><span data-ttu-id="02592-105">XML 문서 주석을 포함하는 CodeDOM 그래프를 만들려면</span><span class="sxs-lookup"><span data-stu-id="02592-105">To create a CodeDOM graph that contains XML documentation comments</span></span>  
  
1.  <span data-ttu-id="02592-106">응용 프로그램 예제에 대한 CodeDOM 그래프를 포함하는 <xref:System.CodeDom.CodeCompileUnit>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02592-106">Create a <xref:System.CodeDom.CodeCompileUnit> containing the CodeDOM graph for the sample application.</span></span>  
  
2.  <span data-ttu-id="02592-107">`docComment` 매개 변수를 `true`로 설정해서 <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> 생성자를 사용하여 XML 문서 주석 요소 및 텍스트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02592-107">Use the <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> constructor with the `docComment` parameter set to `true` to create the XML documentation comment elements and text.</span></span>  
  
     [!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]
     [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]  
  
### <a name="to-generate-the-code-from-the-codecompileunit"></a><span data-ttu-id="02592-108">CodeCompileUnit에서 코드를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="02592-108">To generate the code from the CodeCompileUnit</span></span>  
  
1.  <span data-ttu-id="02592-109"><xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> 메서드를 사용하여 코드를 생성하고 컴파일할 소스 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02592-109">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method to generate the code and create a source file to be compiled.</span></span>  
  
     [!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]
     [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]  
  
### <a name="to-compile-the-code-and-generate-the-documentation-file"></a><span data-ttu-id="02592-110">코드를 컴파일하고 문서 파일을 생성하려면</span><span class="sxs-lookup"><span data-stu-id="02592-110">To compile the code and generate the documentation file</span></span>  
  
1.  <span data-ttu-id="02592-111"><xref:System.CodeDom.Compiler.CompilerParameters> 개체의 <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> 속성에 **/doc** 컴파일러 옵션을 추가하고, 코드를 컴파일할 때 <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> 메서드에 이 개체를 전달하여 XML 문서 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02592-111">Add the **/doc** compiler option to the <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> property of a <xref:System.CodeDom.Compiler.CompilerParameters> object and pass the object to the <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> method to create the XML documentation file when the code is compiled.</span></span>  
  
     [!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]
     [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="02592-112">예제</span><span class="sxs-lookup"><span data-stu-id="02592-112">Example</span></span>  
 <span data-ttu-id="02592-113">다음 코드 예제에서는 문서 주석이 포함된 CodeDOM 그래프를 만들고, 그래프에서 코드 파일을 생성한 다음 파일을 컴파일하고 연결된 XML 문서 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02592-113">The following code example creates a CodeDOM graph with documentation comments, generates a code file from the graph, and compiles the file and creates an associated XML documentation file.</span></span>  
  
 [!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)]
 [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]  
  
 <span data-ttu-id="02592-114">코드 예제에서는 HelloWorldDoc.xml 파일에 다음 XML 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02592-114">The code example creates the following XML documentation in the HelloWorldDoc.xml file.</span></span>  
  
```xml  
<?xml version="1.0" ?>   
<doc>  
  <assembly>  
    <name>HelloWorld</name>   
  </assembly>  
  <members>  
    <member name="T:Samples.Class1">  
      <summary>  
        Create a Hello World application.   
        <seealso cref="M:Samples.Class1.Main" />   
      </summary>  
    </member>  
    <member name="M:Samples.Class1.Main">  
      <summary>  
        Main method for HelloWorld application.   
        <para>Add a new paragraph to the description.</para>   
      </summary>  
    </member>  
  </members>  
</doc>  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="02592-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="02592-115">Compiling the Code</span></span>  
  
-   <span data-ttu-id="02592-116">이 코드 예제를 성공적으로 실행하려면 `FullTrust` 권한이 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02592-116">This code example requires the `FullTrust` permission set to execute successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02592-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02592-117">See Also</span></span>  
 [<span data-ttu-id="02592-118">코드를 XML로 문서화</span><span class="sxs-lookup"><span data-stu-id="02592-118">Documenting Your Code with XML</span></span>](~/docs/visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="02592-119">XML 문서 주석</span><span class="sxs-lookup"><span data-stu-id="02592-119">XML Documentation Comments</span></span>](~/docs/csharp/programming-guide/xmldoc/xml-documentation-comments.md)  
 [<span data-ttu-id="02592-120">XML 문서</span><span class="sxs-lookup"><span data-stu-id="02592-120">XML Documentation</span></span>](/cpp/ide/xml-documentation-visual-cpp)
