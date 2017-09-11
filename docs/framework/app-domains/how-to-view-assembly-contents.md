---
title: "방법: 어셈블리 내용 보기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assembly manifest, viewing information
- Ildasm.exe
- MSIL Disassembler
- assemblies [.NET Framework], viewing contents
- viewing assembly information
- MSIL
- viewing MSIL information
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3583e69e90080eb830bb61a5e0c7b6e944f7d654
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-view-assembly-contents"></a><span data-ttu-id="ada5e-102">방법: 어셈블리 내용 보기</span><span class="sxs-lookup"><span data-stu-id="ada5e-102">How to: View Assembly Contents</span></span>
<span data-ttu-id="ada5e-103">[Ildasm.exe(IL 디스어셈블러)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)를 사용하여 파일의 MSIL(Microsoft Intermediate Language) 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-103">You can use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to view Microsoft intermediate language (MSIL) information in a file.</span></span> <span data-ttu-id="ada5e-104">검사되는 파일이 어셈블리이면 이 정보에 어셈블리의 특성뿐만 아니라 다른 모듈 및 어셈블리에 대한 참조가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-104">If the file being examined is an assembly, this information can include the assembly's attributes, as well as references to other modules and assemblies.</span></span> <span data-ttu-id="ada5e-105">이 정보는 파일이 어셈블리 또는 어셈블리의 일부인지 여부 및 파일이 다른 모듈 또는 어셈블리에 대한 참조를 포함하는지 여부를 확인하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-105">This information can be helpful in determining whether a file is an assembly or part of an assembly, and whether the file has references to other modules or assemblies.</span></span>  
  
### <a name="to-display-the-contents-of-an-assembly-using-ildasmexe"></a><span data-ttu-id="ada5e-106">Ildasm.exe를 사용하여 어셈블리의 내용을 표시하려면</span><span class="sxs-lookup"><span data-stu-id="ada5e-106">To display the contents of an assembly using Ildasm.exe</span></span>  
  
1.  <span data-ttu-id="ada5e-107">명령 프롬프트에서 **ildasm** \<*assembly name*>을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-107">Type **ildasm** \<*assembly name*> at the command prompt.</span></span> <span data-ttu-id="ada5e-108">예를 들어 다음 명령은 `Hello.exe` 어셈블리를 디스어셈블합니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-108">For example, the following command disassembles the `Hello.exe` assembly.</span></span>  
  
    ```  
    ildasm Hello.exe  
    ```  
  
### <a name="to-view-assembly-manifest-information"></a><span data-ttu-id="ada5e-109">어셈블리 매니페스트 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="ada5e-109">To view assembly manifest information</span></span>  
  
1.  <span data-ttu-id="ada5e-110">MSIL 디스어셈블러 창에서 매니페스트 아이콘을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-110">Double-click the MANIFEST icon in the MSIL Disassembler window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ada5e-111">예제</span><span class="sxs-lookup"><span data-stu-id="ada5e-111">Example</span></span>  
 <span data-ttu-id="ada5e-112">다음 예제는 기본 "Hello, World" 프로그램으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-112">The following example starts with a basic "Hello, World" program.</span></span> <span data-ttu-id="ada5e-113">프로그램을 컴파일한 후 Ildasm.exe를 사용하여 Hello.exe 어셈블리를 디스어셈블하고 어셈블리 매니페스트를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-113">After compiling the program, use Ildasm.exe to disassemble the Hello.exe assembly and view the assembly manifest.</span></span>  
  
 <span data-ttu-id="ada5e-114">[!code-cpp[Conceptual.Assembly.Contents#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.contents/cpp/source.cpp#1)] [!code-csharp[Conceptual.Assembly.Contents#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.contents/cs/source.cs#1)] [!code-vb[Conceptual.Assembly.Contents#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.contents/vb/source.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="ada5e-114">[!code-cpp[Conceptual.Assembly.Contents#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.contents/cpp/source.cpp#1)] [!code-csharp[Conceptual.Assembly.Contents#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.contents/cs/source.cs#1)] [!code-vb[Conceptual.Assembly.Contents#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.contents/vb/source.vb#1)]</span></span>  
  
 <span data-ttu-id="ada5e-115">Hello.exe 어셈블리에서 ildasm.exe 명령을 실행하고 IL DASM 창에서 매니페스트 아이콘을 두 번 클릭하면 다음과 같은 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-115">Running the command ildasm.exe on the Hello.exe assembly and double-clicking the MANIFEST icon in the IL DASM window produces the following output:</span></span>  
  
```  
// Metadata version: v4.0.30319  
.assembly extern mscorlib  
{  
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..  
  .ver 4:0:0:0  
}  
.assembly Hello  
{  
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )   
  .custom instance void [mscorlib]System.Runtime.CompilerServices.RuntimeCompatibilityAttribute::.ctor() = ( 01 00 01 00 54 02 16 57 72 61 70 4E 6F 6E 45 78   // ....T..WrapNonEx  
                                                                                                             63 65 70 74 69 6F 6E 54 68 72 6F 77 73 01 )       // ceptionThrows.  
  .hash algorithm 0x00008004  
  .ver 0:0:0:0  
}  
.module Hello.exe  
// MVID: {7C2770DB-1594-438D-BAE5-98764C39CCCA}  
.imagebase 0x00400000  
.file alignment 0x00000200  
.stackreserve 0x00100000  
.subsystem 0x0003       // WINDOWS_CUI  
.corflags 0x00000001    //  ILONLY  
// Image base: 0x00600000  
```  
  
 <span data-ttu-id="ada5e-116">다음 표에서는 예제에 사용된 Hello.exe 어셈블리의 어셈블리 매니페스트에 있는 각 지시문에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-116">The following table describes each directive in the assembly manifest of the Hello.exe assembly used in the example.</span></span>  
  
|<span data-ttu-id="ada5e-117">지시문</span><span class="sxs-lookup"><span data-stu-id="ada5e-117">Directive</span></span>|<span data-ttu-id="ada5e-118">설명</span><span class="sxs-lookup"><span data-stu-id="ada5e-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ada5e-119">**.assembly extern \<** *assembly name* **>**</span><span class="sxs-lookup"><span data-stu-id="ada5e-119">**.assembly extern \<** *assembly name* **>**</span></span>|<span data-ttu-id="ada5e-120">현재 모듈에서 참조하는 항목이 포함된 다른 어셈블리를 지정합니다(이 예제에서는 `mscorlib`).</span><span class="sxs-lookup"><span data-stu-id="ada5e-120">Specifies another assembly that contains items referenced by the current module (in this example, `mscorlib`).</span></span>|  
|<span data-ttu-id="ada5e-121">**.publickeytoken \<** *token* **>**</span><span class="sxs-lookup"><span data-stu-id="ada5e-121">**.publickeytoken \<** *token* **>**</span></span>|<span data-ttu-id="ada5e-122">참조된 어셈블리의 실제 키의 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-122">Specifies the token of the actual key of the referenced assembly.</span></span>|  
|<span data-ttu-id="ada5e-123">**.ver \<** *version number* **>**</span><span class="sxs-lookup"><span data-stu-id="ada5e-123">**.ver \<** *version number* **>**</span></span>|<span data-ttu-id="ada5e-124">참조된 어셈블리의 버전 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-124">Specifies the version number of the referenced assembly.</span></span>|  
|<span data-ttu-id="ada5e-125">**.assembly \<** *assembly name* **>**</span><span class="sxs-lookup"><span data-stu-id="ada5e-125">**.assembly \<** *assembly name* **>**</span></span>|<span data-ttu-id="ada5e-126">어셈블리 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-126">Specifies the assembly name.</span></span>|  
|<span data-ttu-id="ada5e-127">**.hash algorithm \<** *int32 value* **>**</span><span class="sxs-lookup"><span data-stu-id="ada5e-127">**.hash algorithm \<** *int32 value* **>**</span></span>|<span data-ttu-id="ada5e-128">사용되는 해시 알고리즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-128">Specifies the hash algorithm used.</span></span>|  
|<span data-ttu-id="ada5e-129">**.ver \<** *version number* **>**</span><span class="sxs-lookup"><span data-stu-id="ada5e-129">**.ver \<** *version number* **>**</span></span>|<span data-ttu-id="ada5e-130">어셈블리의 버전 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-130">Specifies the version number of the assembly.</span></span>|  
|<span data-ttu-id="ada5e-131">**.module \<** *file name* **>**</span><span class="sxs-lookup"><span data-stu-id="ada5e-131">**.module \<** *file name* **>**</span></span>|<span data-ttu-id="ada5e-132">어셈블리를 구성하는 모듈의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-132">Specifies the name of the modules that make up the assembly.</span></span> <span data-ttu-id="ada5e-133">이 예제에서는 어셈블리가 파일 하나로만 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-133">In this example, the assembly consists of only one file.</span></span>|  
|<span data-ttu-id="ada5e-134">**.subsystem \<** *value* **>**</span><span class="sxs-lookup"><span data-stu-id="ada5e-134">**.subsystem \<** *value* **>**</span></span>|<span data-ttu-id="ada5e-135">프로그램에 필요한 응용 프로그램 환경을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-135">Specifies the application environment required for the program.</span></span> <span data-ttu-id="ada5e-136">이 예제에서 값 3은 이 실행 파일이 콘솔에서 실행됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-136">In this example, the value 3 indicates that this executable is run from a console.</span></span>|  
|<span data-ttu-id="ada5e-137">**.corflags**</span><span class="sxs-lookup"><span data-stu-id="ada5e-137">**.corflags**</span></span>|<span data-ttu-id="ada5e-138">현재 메타데이터에서 예약된 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-138">Currently a reserved field in the metadata.</span></span>|  
  
 <span data-ttu-id="ada5e-139">어셈블리 매니페스트에는 어셈블리의 내용에 따라 여러 다른 지시문이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ada5e-139">An assembly manifest can contain a number of different directives, depending on the contents of the assembly.</span></span> <span data-ttu-id="ada5e-140">어셈블리 매니페스트에 있는 지시문의 광범위한 목록은 ECMA 설명서의 "파티션 II: 메타데이터 정의 및 의미 체계" 및 "파티션 III: CIL 명령 집합"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ada5e-140">For an extensive list of the directives in the assembly manifest, see the ECMA documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="ada5e-141">이 설명서는 온라인으로 제공됩니다. MSDN의 [ECMA C# 및 공용 언어 인프라 표준](http://go.microsoft.com/fwlink/?LinkID=99212) 및 Ecma International 웹 사이트의 [표준 ECMA-335 - CLI(공용 언어 인프라)](http://go.microsoft.com/fwlink/?LinkID=65552)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ada5e-141">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ada5e-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ada5e-142">See Also</span></span>  
 <span data-ttu-id="ada5e-143">[응용 프로그램 도메인 및 어셈블리](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346) </span><span class="sxs-lookup"><span data-stu-id="ada5e-143">[Application Domains and Assemblies](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346) </span></span>  
 <span data-ttu-id="ada5e-144">[응용 프로그램 도메인 및 어셈블리 방법 항목](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="ada5e-144">[Application Domains and Assemblies How-to Topics](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md) </span></span>  
 [<span data-ttu-id="ada5e-145">Ildasm.exe(IL 디스어셈블러)</span><span class="sxs-lookup"><span data-stu-id="ada5e-145">Ildasm.exe (IL Disassembler)</span></span>](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)

