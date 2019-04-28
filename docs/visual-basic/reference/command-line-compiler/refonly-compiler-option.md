---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 4093e98738cf6e41cd450229d82e3672fe9687ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788871"
---
# <a name="-refonly-visual-basic"></a><span data-ttu-id="ec98a-102">-refonly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec98a-102">-refonly (Visual Basic)</span></span>

<span data-ttu-id="ec98a-103">합니다 **-refonly** 옵션 컴파일 기본 출력은 구현 어셈블리 대신 참조 어셈블리를 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec98a-103">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="ec98a-104">`-refonly` 매개 변수는 참조 어셈블리가 실행될 수 없을 때 PDB 출력을 자동으로 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec98a-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="ec98a-105">구문</span><span class="sxs-lookup"><span data-stu-id="ec98a-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="ec98a-106">설명</span><span class="sxs-lookup"><span data-stu-id="ec98a-106">Remarks</span></span>

<span data-ttu-id="ec98a-107">Visual Basic 지원은 `-refout` 버전 15.3부터 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec98a-107">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="ec98a-108">참조 어셈블리는 구현 코드가 없는 메타 데이터를 포함 하는 메타 데이터 전용 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="ec98a-108">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="ec98a-109">익명 형식을 제외한 모든 항목에 대 한 형식 및 멤버 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec98a-109">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="ec98a-110">본문이 없는 경우와 대조적으로 `throw null` 본문을 사용하는 이유는 PEVerify가 실행 및 전달될 수 있도록 하여 메타데이터의 완전성을 검증하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ec98a-110">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="ec98a-111">참조 어셈블리는 어셈블리 수준 포함 [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ec98a-111">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="ec98a-112">이 특성을 소스에서 지정할 수 있습니다. 이렇게 하면 컴파일러가 특성을 합성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec98a-112">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="ec98a-113">이 특성으로 인해 런타임 실행을 위한 참조 어셈블리 로드를 거부 되지만 리플렉션 전용 컨텍스트에서 로드 될 여전히 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec98a-113">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="ec98a-114">어셈블리에 반영 되는 도구를 참조 어셈블리를 리플렉션 전용으로 로드를 확인 해야 합니다. 그렇지 않으면 런타임에서 throw 된 <xref:System.BadImageFormatException>합니다.</span><span class="sxs-lookup"><span data-stu-id="ec98a-114">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="ec98a-115">`-refonly` 및 [`-refout`](refout-compiler-option.md) 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec98a-115">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec98a-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="ec98a-116">See also</span></span>

- [<span data-ttu-id="ec98a-117">/refout</span><span class="sxs-lookup"><span data-stu-id="ec98a-117">-refout</span></span>](refout-compiler-option.md)
- [<span data-ttu-id="ec98a-118">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="ec98a-118">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="ec98a-119">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="ec98a-119">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
