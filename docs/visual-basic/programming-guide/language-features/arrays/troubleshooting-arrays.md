---
title: 배열 문제 해결(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 2b051d22fe3d331626f2e181c008043e576b7526
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833375"
---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="a359c-102">배열 문제 해결(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a359c-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="a359c-103">이 페이지는 배열에서 작업할 때 발생할 수 있는 몇 가지 일반적인 문제를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="a359c-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="a359c-104">컴파일 오류를 선언 하 고 배열을 초기화 하는 중</span><span class="sxs-lookup"><span data-stu-id="a359c-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="a359c-105">컴파일 오류는 선언, 만들기 및 배열 초기화에 대 한 오해에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a359c-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="a359c-106">오류의 가장 일반적인 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a359c-106">The most common causes of errors are the following:</span></span>  
  
-   <span data-ttu-id="a359c-107">제공 된 [새 운영자](../../../../visual-basic/language-reference/operators/new-operator.md) 차원 길이 지정 하는 배열 변수 선언 뒤에 절.</span><span class="sxs-lookup"><span data-stu-id="a359c-107">Supplying a [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="a359c-108">다음 코드 줄에는이 형식의 잘못 된 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a359c-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   <span data-ttu-id="a359c-109">최상위 배열이 가변된 배열 넘게 차원 길이 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a359c-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="a359c-110">다음 코드 줄에는이 형식의 잘못 된 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a359c-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   <span data-ttu-id="a359c-111">생략 된 `New` 키워드 요소 값을 지정 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="a359c-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="a359c-112">다음 코드 줄에는이 형식의 잘못 된 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a359c-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   <span data-ttu-id="a359c-113">제공 된 `New` 괄호 없이 절 (`{}`).</span><span class="sxs-lookup"><span data-stu-id="a359c-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="a359c-114">다음 코드 줄에는이 형식의 잘못 된 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a359c-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="a359c-115">범위를 벗어난 배열 액세스</span><span class="sxs-lookup"><span data-stu-id="a359c-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="a359c-116">배열을 초기화 하는 프로세스 각 차원에 상한값 및 하한값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a359c-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="a359c-117">배열의 요소에 대 한 모든 액세스는 유효한 인덱스 또는 모든 차원에 대 한 아래 첨자를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a359c-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="a359c-118">인덱스의 상한값, 하한값 아래 이상 경우는 <xref:System.IndexOutOfRangeException> 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a359c-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="a359c-119">컴파일러는 오류가 런타임에 발생 하므로 이러한 오류를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a359c-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="a359c-120">범위 결정</span><span class="sxs-lookup"><span data-stu-id="a359c-120">Determining Bounds</span></span>  
 <span data-ttu-id="a359c-121">다른 구성 요소 코드를 배열에 전달 하는 경우 예를 들어 프로시저 인수로 모르는 배열의 크기 또는 해당 차원의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="a359c-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="a359c-122">모든 요소에 액세스 하려고 하기 전에 모든 차원 배열에 대 한 상한 값은 항상 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a359c-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="a359c-123">배열 Visual Basic 이외의 다른 수단으로 만들어진 경우 `New` 절 하한값 0 이외의 것 이므로 가장 안전도 해당 하한값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a359c-123">If the array has been created by some means other than a Visual Basic `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="a359c-124">차원 지정</span><span class="sxs-lookup"><span data-stu-id="a359c-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="a359c-125">다차원 배열의 범위를 결정할 때는 주의 해야 치수를 지정 하는 방법.</span><span class="sxs-lookup"><span data-stu-id="a359c-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="a359c-126">합니다 `dimension` 의 매개 변수를 <xref:System.Array.GetLowerBound%2A> 및 <xref:System.Array.GetUpperBound%2A> 메서드는 0부터 시작 하는 동안 합니다 `Rank` Visual Basic의 매개 변수 <xref:Microsoft.VisualBasic.Information.LBound%2A> 및 <xref:Microsoft.VisualBasic.Information.UBound%2A> 함수는 1부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a359c-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a359c-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="a359c-127">See also</span></span>

- [<span data-ttu-id="a359c-128">배열</span><span class="sxs-lookup"><span data-stu-id="a359c-128">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="a359c-129">방법: Visual Basic에서 배열 변수 초기화</span><span class="sxs-lookup"><span data-stu-id="a359c-129">How to: Initialize an Array Variable in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
