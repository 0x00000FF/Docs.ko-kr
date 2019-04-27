---
title: 프로그램 구조 및 코드 규칙(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions
- Visual Basic code, coding conventions
- coding conventions [Visual Basic], Visual Basic
- programs [Visual Basic], structure
- program structure [Visual Basic]
- naming conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- Visual Basic code
- programming [Visual Basic], Visual Basic coding conventions
ms.assetid: dd9be76f-6944-4e78-ad72-0b6084a3fc13
ms.openlocfilehash: b79e339ebe81a7228a02837e5c0c23c80a8132e9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916944"
---
# <a name="program-structure-and-code-conventions-visual-basic"></a><span data-ttu-id="bd7bf-102">프로그램 구조 및 코드 규칙(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd7bf-102">Program Structure and Code Conventions (Visual Basic)</span></span>
<span data-ttu-id="bd7bf-103">이 섹션에서는 일반적인 Visual Basic 프로그램 구조를 소개 하 고, "Hello, World" 간단한 Visual Basic 프로그램을 제공, Visual Basic 코드 규칙을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-103">This section introduces the typical Visual Basic program structure, provides a simple Visual Basic program, "Hello, World", and discusses Visual Basic code conventions.</span></span> <span data-ttu-id="bd7bf-104">코드 규칙은 프로그램의 논리에 있지만 해당 물리적 구조 및 모양에 중점을 둔 제안 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-104">Code conventions are suggestions that focus not on a program's logic but on its physical structure and appearance.</span></span> <span data-ttu-id="bd7bf-105">그 뒤에 더 쉽게 코드를 읽고, 이해 하며 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-105">Following them makes your code easier to read, understand, and maintain.</span></span> <span data-ttu-id="bd7bf-106">특히 코드 규칙 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-106">Code conventions can include, among others:</span></span>  
  
-   <span data-ttu-id="bd7bf-107">레이블 지정 및 코드 주석 처리에 대 한 표준화 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-107">Standardized formats for labeling and commenting code.</span></span>  
  
-   <span data-ttu-id="bd7bf-108">간격, 형식 및 코드 들여쓰기에 대 한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-108">Guidelines for spacing, formatting, and indenting code.</span></span>  
  
-   <span data-ttu-id="bd7bf-109">개체, 변수 및 프로시저에 대 한 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="bd7bf-109">Naming conventions for objects, variables, and procedures.</span></span>  
  
 <span data-ttu-id="bd7bf-110">다음 항목에는 일련의 올바른 사용의 예제와 함께 Visual Basic 프로그램에 대 한 프로그래밍 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-110">The following topics present a set of programming guidelines for Visual Basic programs, along with examples of good usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bd7bf-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="bd7bf-111">In This Section</span></span>  
 [<span data-ttu-id="bd7bf-112">Visual Basic 프로그램의 구조</span><span class="sxs-lookup"><span data-stu-id="bd7bf-112">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 <span data-ttu-id="bd7bf-113">Visual Basic 프로그램을 구성 하는 요소에 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-113">Provides an overview of the elements that make up a Visual Basic program.</span></span>  
  
 [<span data-ttu-id="bd7bf-114">Visual Basic의 main 프로시저</span><span class="sxs-lookup"><span data-stu-id="bd7bf-114">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 <span data-ttu-id="bd7bf-115">역할 시작을 가리키고 응용 프로그램에 대 한 전체 제어 하는 절차를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-115">Discusses the procedure that serves as the starting point and overall control for your application.</span></span>  
  
 [<span data-ttu-id="bd7bf-116">참조 및 Imports 문</span><span class="sxs-lookup"><span data-stu-id="bd7bf-116">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 <span data-ttu-id="bd7bf-117">다른 어셈블리 개체를 참조 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-117">Discusses how to reference objects in other assemblies.</span></span>  
  
 [<span data-ttu-id="bd7bf-118">Visual Basic의 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="bd7bf-118">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 <span data-ttu-id="bd7bf-119">네임 스페이스 어셈블리 내에서 개체를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-119">Describes how namespaces organize objects within assemblies.</span></span>  
  
 [<span data-ttu-id="bd7bf-120">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="bd7bf-120">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 <span data-ttu-id="bd7bf-121">프로시저, 상수, 변수, 인수 및 개체 이름을 지정 하기 위한 일반 지침이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-121">Includes general guidelines for naming procedures, constants, variables, arguments, and objects.</span></span>  
  
 [<span data-ttu-id="bd7bf-122">Visual Basic 코딩 규칙</span><span class="sxs-lookup"><span data-stu-id="bd7bf-122">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 <span data-ttu-id="bd7bf-123">이 문서에서는 샘플을 개발에 사용 되는 지침을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-123">Reviews the guidelines used in developing the samples in this documentation.</span></span>  
  
 [<span data-ttu-id="bd7bf-124">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="bd7bf-124">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="bd7bf-125">다른 사용자를 무시 하도록 컴파일러에 지시 하는 동안 코드의 특정 요소를 선택적으로 컴파일하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-125">Describes how to compile particular blocks of code selectively while directing the compiler to ignore others.</span></span>  
  
 [<span data-ttu-id="bd7bf-126">방법: 코드에서 문 분리 및 결합</span><span class="sxs-lookup"><span data-stu-id="bd7bf-126">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 <span data-ttu-id="bd7bf-127">긴 문을 여러 줄으로 나누고 짧은 문을 한 줄에 결합 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-127">Shows how to divide long statements into multiple lines and combine short statements on one line.</span></span>  
  
 [<span data-ttu-id="bd7bf-128">방법: 코드 섹션 축소 및 숨기기</span><span class="sxs-lookup"><span data-stu-id="bd7bf-128">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 <span data-ttu-id="bd7bf-129">코드 편집기에서 Visual Basic 코드 섹션 축소 및 숨기기 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-129">Shows how to collapse and hide sections of code in the Visual Basic code editor.</span></span>  
  
 [<span data-ttu-id="bd7bf-130">방법: 레이블 문</span><span class="sxs-lookup"><span data-stu-id="bd7bf-130">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 <span data-ttu-id="bd7bf-131">사용에 대 한 문을 사용 하 여 같은 식별 하는 코드 줄을 표시 하는 방법을 보여 줍니다 `On Error Goto`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-131">Shows how to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 [<span data-ttu-id="bd7bf-132">코드의 특수 문자</span><span class="sxs-lookup"><span data-stu-id="bd7bf-132">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 <span data-ttu-id="bd7bf-133">방법 및 위치를 보여 줍니다. 비-숫자 및 알파벳 이외의 문자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-133">Shows how and where to use non-numeric and non-alphabetic characters.</span></span>  
  
 [<span data-ttu-id="bd7bf-134">코드 주석</span><span class="sxs-lookup"><span data-stu-id="bd7bf-134">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 <span data-ttu-id="bd7bf-135">코드에 설명 주석을 추가 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-135">Discusses how to add descriptive comments to your code.</span></span>  
  
 [<span data-ttu-id="bd7bf-136">코드에서 요소 이름으로 사용되는 키워드</span><span class="sxs-lookup"><span data-stu-id="bd7bf-136">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 <span data-ttu-id="bd7bf-137">대괄호를 사용 하는 방법을 설명 합니다 (`[]`) Visual Basic 키워드는 변수 이름을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-137">Describes how to use brackets (`[]`) to delimit variable names that are also Visual Basic keywords.</span></span>  
  
 [<span data-ttu-id="bd7bf-138">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="bd7bf-138">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 <span data-ttu-id="bd7bf-139">Visual Basic 프로그램의 요소를 참조 하는 다양 한 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-139">Describes various ways to refer to elements of a Visual Basic program.</span></span>  
  
 [<span data-ttu-id="bd7bf-140">Visual Basic 제한 사항</span><span class="sxs-lookup"><span data-stu-id="bd7bf-140">Visual Basic Limitations</span></span>](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 <span data-ttu-id="bd7bf-141">Visual Basic 내에서 코딩 알려진된 제한 사항 제거에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-141">Discusses the removal of known coding limits within Visual Basic.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bd7bf-142">관련 단원</span><span class="sxs-lookup"><span data-stu-id="bd7bf-142">Related Sections</span></span>  
 [<span data-ttu-id="bd7bf-143">글꼴 표시 및 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="bd7bf-143">Typographic and Code Conventions</span></span>](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 <span data-ttu-id="bd7bf-144">Visual Basic에 대 한 표준 코딩 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-144">Provides standard coding conventions for Visual Basic.</span></span>  
  
 [<span data-ttu-id="bd7bf-145">코드 작성</span><span class="sxs-lookup"><span data-stu-id="bd7bf-145">Writing Code</span></span>](/visualstudio/ide/writing-code-in-the-code-and-text-editor)  
 <span data-ttu-id="bd7bf-146">쉽게 작성 하 고 코드를 관리 하는 기능에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7bf-146">Describes features that make it easier for you to write and manage your code.</span></span>
