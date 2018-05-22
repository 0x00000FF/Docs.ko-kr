---
title: -delaysign(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
ms.openlocfilehash: f8525a4e96d172709673b94316b06d815535805f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-delaysign-c-compiler-options"></a><span data-ttu-id="4ddda-102">-delaysign(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="4ddda-102">-delaysign (C# Compiler Options)</span></span>
<span data-ttu-id="4ddda-103">이 옵션을 사용하면 나중에 디지털 시그니처를 추가할 수 있도록 컴파일러가 출력 파일에 공간을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddda-103">This option causes the compiler to reserve space in the output file so that a digital signature can be added later.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ddda-104">구문</span><span class="sxs-lookup"><span data-stu-id="4ddda-104">Syntax</span></span>  
  
```console  
-delaysign[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="4ddda-105">인수</span><span class="sxs-lookup"><span data-stu-id="4ddda-105">Arguments</span></span>  
 <span data-ttu-id="4ddda-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="4ddda-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="4ddda-107">완전히 서명된 어셈블리가 필요하면 **-delaysign-** 를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddda-107">Use **-delaysign-** if you want a fully signed assembly.</span></span> <span data-ttu-id="4ddda-108">어셈블리에 공개 키만 배치하려면 **-delaysign+** 를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddda-108">Use **-delaysign+** if you only want to place the public key in the assembly.</span></span> <span data-ttu-id="4ddda-109">기본값은 **-delaysign-** 입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddda-109">The default is **-delaysign-**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ddda-110">설명</span><span class="sxs-lookup"><span data-stu-id="4ddda-110">Remarks</span></span>  
 <span data-ttu-id="4ddda-111">**-delaysign** 옵션은 [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) 또는 [-keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md)와 함께 사용하지 않으면 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddda-111">The **-delaysign** option has no effect unless used with [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) or [-keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span></span>  
  
 <span data-ttu-id="4ddda-112">완전히 서명된 어셈블리를 요청할 경우 컴파일러는 매니페스트(어셈블리 메타데이터)가 포함된 파일을 해시하고 개인 키로 해당 해시에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddda-112">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="4ddda-113">결과로 생성되는 디지털 서명은 매니페스트가 포함된 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddda-113">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="4ddda-114">어셈블리 서명이 연기된 경우 컴파일러는 서명을 계산하거나 저장하지 않고 나중에 서명을 추가할 수 있도록 파일에 공간을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddda-114">When an assembly is delay signed, the compiler does not compute and store the signature, but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="4ddda-115">예를 들어 **-delaysign+** 를 사용하면 테스터를 통해 전역 캐시에 어셈블리를 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddda-115">For example, using **-delaysign+** allows a tester to put the assembly in the global cache.</span></span> <span data-ttu-id="4ddda-116">테스트를 마친 후 [어셈블리 링커](../../../framework/tools/al-exe-assembly-linker.md) 유틸리티를 통해 어셈블리에 개인 키를 배치하여 어셈블리에 완전히 서명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddda-116">After testing, you can fully sign the assembly by placing the private key in the assembly using the [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md) utility.</span></span>  
  
 <span data-ttu-id="4ddda-117">자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) 및 [어셈블리 서명 지연](../../../framework/app-domains/delay-sign-assembly.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ddda-117">For more information, see [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="4ddda-118">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="4ddda-118">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="4ddda-119">프로젝트의 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4ddda-119">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="4ddda-120">**서명만 연기** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddda-120">Modify the **Delay sign only** property.</span></span>  
  
 <span data-ttu-id="4ddda-121">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ddda-121">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ddda-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ddda-122">See Also</span></span>  
 [<span data-ttu-id="4ddda-123">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="4ddda-123">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="4ddda-124">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="4ddda-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
