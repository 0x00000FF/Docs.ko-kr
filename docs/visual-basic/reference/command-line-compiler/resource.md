---
title: /resource(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 858a216873ad9999722388e45d5de28398b27fbe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="resource-visual-basic"></a><span data-ttu-id="9d492-102">/resource(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d492-102">/resource (Visual Basic)</span></span>
<span data-ttu-id="9d492-103">관리되는 리소스를 어셈블리에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9d492-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d492-104">구문</span><span class="sxs-lookup"><span data-stu-id="9d492-104">Syntax</span></span>  
  
```  
/resource:filename[,identifier[,public|private]]  
' -or-  
/res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="9d492-105">인수</span><span class="sxs-lookup"><span data-stu-id="9d492-105">Arguments</span></span>  
  
|<span data-ttu-id="9d492-106">용어</span><span class="sxs-lookup"><span data-stu-id="9d492-106">Term</span></span>|<span data-ttu-id="9d492-107">정의</span><span class="sxs-lookup"><span data-stu-id="9d492-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="9d492-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="9d492-108">Required.</span></span> <span data-ttu-id="9d492-109">출력 파일에 포함할 리소스 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9d492-109">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="9d492-110">기본적으로 `filename` 어셈블리에 공개 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d492-110">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="9d492-111">파일 이름을 따옴표로 묶습니다 ("")에 공백이 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="9d492-111">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="9d492-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9d492-112">Optional.</span></span> <span data-ttu-id="9d492-113">리소스에 대 한 논리적 이름 로드 하는 데 사용 하는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9d492-113">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="9d492-114">기본값은 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9d492-114">The default is the name of the file.</span></span> <span data-ttu-id="9d492-115">리소스 인지 공개 또는 개인 어셈블리 매니페스트에 다음와 같이 지정할 수 있습니다: `/res:``filename.res`,`myname.res`,`public`</span><span class="sxs-lookup"><span data-stu-id="9d492-115">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `/res:``filename.res`,`myname.res`,`public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d492-116">설명</span><span class="sxs-lookup"><span data-stu-id="9d492-116">Remarks</span></span>  
 <span data-ttu-id="9d492-117">사용 하 여 `/linkresource` 출력 파일에 리소스 파일을 배치 하지 않고 어셈블리에는 리소스를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d492-117">Use `/linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="9d492-118">경우 `filename` 는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 만들어진 리소스 파일, 예를 들어 여는 [Resgen.exe (리소스 파일 생성기)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) 또는 개발 환경에서의 멤버와 액세스할 수 있습니다는 <xref:System.Resources> (참조 네임스페이스<xref:System.Resources.ResourceManager> 자세한 정보에 대 한).</span><span class="sxs-lookup"><span data-stu-id="9d492-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="9d492-119">런타임 시 다른 모든 리소스에 액세스 하려면 다음 방법 중 하나를 사용: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, 또는 <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="9d492-119">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="9d492-120">`/resource`의 약식은 `/res`입니다.</span><span class="sxs-lookup"><span data-stu-id="9d492-120">The short form of `/resource` is `/res`.</span></span>  
  
 <span data-ttu-id="9d492-121">설정 하는 방법에 대 한 내용은 `/resource` Visual Studio IDE에서 참조 [응용 프로그램 리소스 관리 (.NET)](/visualstudio/ide/managing-application-resources-dotnet)합니다.</span><span class="sxs-lookup"><span data-stu-id="9d492-121">For information about how to set `/resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d492-122">예제</span><span class="sxs-lookup"><span data-stu-id="9d492-122">Example</span></span>  
 <span data-ttu-id="9d492-123">다음 코드에서는 `In.vb` 및 연결 합니다. 리소스 파일 `Rf.resource`합니다.</span><span class="sxs-lookup"><span data-stu-id="9d492-123">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```  
vbc /res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d492-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d492-124">See Also</span></span>  
 [<span data-ttu-id="9d492-125">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="9d492-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="9d492-126">/win32resource</span><span class="sxs-lookup"><span data-stu-id="9d492-126">/win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)  
 [<span data-ttu-id="9d492-127">/linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d492-127">/linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)  
 [<span data-ttu-id="9d492-128">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d492-128">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="9d492-129">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="9d492-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
