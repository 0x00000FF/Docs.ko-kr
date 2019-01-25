---
title: Array Dimensions in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: 5ba92e113faf9d68bad97968937cc736132b2065
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708534"
---
# <a name="array-dimensions-in-visual-basic"></a><span data-ttu-id="15365-102">Array Dimensions in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15365-102">Array Dimensions in Visual Basic</span></span>
<span data-ttu-id="15365-103">A *차원* 은 방향 배열 요소의 사양을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15365-103">A *dimension* is a direction in which you can vary the specification of an array's elements.</span></span> <span data-ttu-id="15365-104">해당 월의 각 날짜에 대 한 총 판매량을 보유 하는 배열 이상의 차원을 (해당 월의 일)을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="15365-104">An array that holds the sales total for each day of the month has one dimension (the day of the month).</span></span> <span data-ttu-id="15365-105">총 판매액이 들어 부서에서 월의 각 날짜에는 배열에 두 개의 차원 (부서 번호 및 월의 일).</span><span class="sxs-lookup"><span data-stu-id="15365-105">An array that holds the sales total by department for each day of the month has two dimensions (the department number and the day of the month).</span></span> <span data-ttu-id="15365-106">배열의 차원 수 라고 해당 *순위*합니다.</span><span class="sxs-lookup"><span data-stu-id="15365-106">The number of dimensions an array has is called its *rank*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15365-107">사용할 수는 <xref:System.Array.Rank%2A> 얼마나 많은 차원 배열에 확인 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="15365-107">You can use the <xref:System.Array.Rank%2A> property to determine the how many dimensions an array has.</span></span>  
  
## <a name="working-with-dimensions"></a><span data-ttu-id="15365-108">차원 작업</span><span class="sxs-lookup"><span data-stu-id="15365-108">Working with Dimensions</span></span>  
 <span data-ttu-id="15365-109">제공 하 여 배열의 요소를 지정할 수 있습니다는 *인덱스* 하거나 *첨자* 배열의 각 차원에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="15365-109">You specify an element of an array by supplying an *index* or *subscript* for each of its dimensions.</span></span> <span data-ttu-id="15365-110">요소는 해당 차원에 대 한 가장 높은 인덱스를 인덱스 0에서에서 각 차원에 따라 연속.</span><span class="sxs-lookup"><span data-stu-id="15365-110">The elements are contiguous along each dimension from index 0 through the highest index for that dimension.</span></span>  
  
 <span data-ttu-id="15365-111">다음 그림에는 개념적 구조의 서로 다른 순위를 사용 하 여 배열 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15365-111">The following illustrations show the conceptual structure of arrays with different ranks.</span></span> <span data-ttu-id="15365-112">그림의 각 요소에 액세스 하는 인덱스 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15365-112">Each element in the illustrations shows the index values that access it.</span></span> <span data-ttu-id="15365-113">예를 들어, 2 차원 배열의 두 번째 행의 첫 번째 요소 인덱스를 지정 하 여 액세스할 수 있습니다 `(1, 0)`합니다.</span><span class="sxs-lookup"><span data-stu-id="15365-113">For example, you can access the first element of the second row of the two-dimensional array by specifying indexes `(1, 0)`.</span></span>  
  
 <span data-ttu-id="15365-114">![하나의 그래픽 다이어그램&#45;차원 배열인](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")</span><span class="sxs-lookup"><span data-stu-id="15365-114">![Graphic diagram of one&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")</span></span>  
<span data-ttu-id="15365-115">1 차원 배열</span><span class="sxs-lookup"><span data-stu-id="15365-115">One-dimensional array</span></span>  
  
 <span data-ttu-id="15365-116">![두 개의 그래픽 다이어그램&#45;차원 배열인](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")</span><span class="sxs-lookup"><span data-stu-id="15365-116">![Graphic diagram of two&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")</span></span>  
<span data-ttu-id="15365-117">2 차원 배열</span><span class="sxs-lookup"><span data-stu-id="15365-117">Two-dimensional array</span></span>  
  
 <span data-ttu-id="15365-118">![세 개의 그래픽 다이어그램&#45;차원 배열인](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")</span><span class="sxs-lookup"><span data-stu-id="15365-118">![Graphic diagram of three&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")</span></span>  
<span data-ttu-id="15365-119">3 차원 배열</span><span class="sxs-lookup"><span data-stu-id="15365-119">Three-dimensional array</span></span>  
  
### <a name="one-dimension"></a><span data-ttu-id="15365-120">하나 이상의 차원</span><span class="sxs-lookup"><span data-stu-id="15365-120">One Dimension</span></span>  
 <span data-ttu-id="15365-121">여러 개의 배열을 하나의 차원만 각 나이 사람의 수와 같은 경우</span><span class="sxs-lookup"><span data-stu-id="15365-121">Many arrays have only one dimension, such as the number of people of each age.</span></span> <span data-ttu-id="15365-122">요소를 지정 하기만 하면은 해당 요소는 카운트를 보유 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="15365-122">The only requirement to specify an element is the age for which that element holds the count.</span></span> <span data-ttu-id="15365-123">따라서 이러한 배열은 하나의 인덱스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="15365-123">Therefore, such an array uses only one index.</span></span> <span data-ttu-id="15365-124">보유 하는 변수를 선언 하는 다음 예제는 *1 차원 배열* 의 나가 120 사이의 0에 대 한 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="15365-124">The following example declares a variable to hold a *one-dimensional array* of age counts for ages 0 through 120.</span></span>  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a><span data-ttu-id="15365-125">2 차원</span><span class="sxs-lookup"><span data-stu-id="15365-125">Two Dimensions</span></span>  
 <span data-ttu-id="15365-126">일부 배열의 각 건물에 캠퍼스의 각 층에 사무실 수와 같은 2 차원 경우</span><span class="sxs-lookup"><span data-stu-id="15365-126">Some arrays have two dimensions, such as the number of offices on each floor of each building on a campus.</span></span> <span data-ttu-id="15365-127">요소 사양에 건물 번호와 층, 건물 및 층 조합에 대해 카운트를 보유 하는 각 요소를</span><span class="sxs-lookup"><span data-stu-id="15365-127">The specification of an element requires both the building number and the floor, and each element holds the count for that combination of building and floor.</span></span> <span data-ttu-id="15365-128">따라서 이러한 배열은 두 개의 인덱스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="15365-128">Therefore, such an array uses two indexes.</span></span> <span data-ttu-id="15365-129">보유 하는 변수를 선언 하는 다음 예제는 *2 차원 배열을* 0 ~ 40 건물과 층 0 ~ 5에 대 한 office 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="15365-129">The following example declares a variable to hold a *two-dimensional array* of office counts, for buildings 0 through 40 and floors 0 through 5.</span></span>  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 <span data-ttu-id="15365-130">2 차원 배열을 라고 한 *사각형 배열을*합니다.</span><span class="sxs-lookup"><span data-stu-id="15365-130">A two-dimensional array is also called a *rectangular array*.</span></span>  
  
### <a name="three-dimensions"></a><span data-ttu-id="15365-131">3 차원</span><span class="sxs-lookup"><span data-stu-id="15365-131">Three Dimensions</span></span>  
 <span data-ttu-id="15365-132">몇 가지 배열은 있는 3 차원 공간에서 값과 같은 3 차원입니다.</span><span class="sxs-lookup"><span data-stu-id="15365-132">A few arrays have three dimensions, such as values in three-dimensional space.</span></span> <span data-ttu-id="15365-133">이러한 배열은 여기서 x, y 및 z 좌표 물리적 공간을 표시 하는 3 개의 인덱스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="15365-133">Such an array uses three indexes, which in this case represent the x, y, and z coordinates of physical space.</span></span> <span data-ttu-id="15365-134">다음 예제에서는 보유 하는 변수를 선언를 *3 차원 배열* 한 온도가 차원 공간의 다양 한 시점입니다.</span><span class="sxs-lookup"><span data-stu-id="15365-134">The following example declares a variable to hold a *three-dimensional array* of air temperatures at various points in a three-dimensional volume.</span></span>  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a><span data-ttu-id="15365-135">세 개 이상의 차원</span><span class="sxs-lookup"><span data-stu-id="15365-135">More than Three Dimensions</span></span>  
 <span data-ttu-id="15365-136">배열 만큼 32 차원을 포함할 수 있습니다를 이지만 거의 4 개 없습니다.</span><span class="sxs-lookup"><span data-stu-id="15365-136">Although an array can have as many as 32 dimensions, it is rare to have more than three.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15365-137">차원 배열에 추가 하면 상당히 신중 하 게 하므로 사용 하 여 다차원 배열의 배열에 필요한 총 저장소 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="15365-137">When you add dimensions to an array, the total storage needed by the array increases considerably, so use multidimensional arrays with care.</span></span>  
  
## <a name="using-different-dimensions"></a><span data-ttu-id="15365-138">다른 차원을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="15365-138">Using Different Dimensions</span></span>  
 <span data-ttu-id="15365-139">현재 월의 모든 날에 대 한 판매 금액을 추적 하려고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="15365-139">Suppose you want to track sales amounts for every day of the present month.</span></span> <span data-ttu-id="15365-140">다음 예제와 같이 월의 각 날짜에 대 한 항목이 표시 31 요소를 사용 하 여 1 차원 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15365-140">You might declare a one-dimensional array with 31 elements, one for each day of the month, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 <span data-ttu-id="15365-141">이제 월간 아니라 연도의 매월 뿐만 아니라 매일에 대 한 동일한 정보를 추적 하려고 한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="15365-141">Now suppose you want to track the same information not only for every day of a month but also for every month of the year.</span></span> <span data-ttu-id="15365-142">다음 예제와 같이 (월)에 대 한 12 행과 (일) 동안 31 개 열이 있는 2 차원 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15365-142">You might declare a two-dimensional array with 12 rows (for the months) and 31 columns (for the days), as the following example shows.</span></span>  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 <span data-ttu-id="15365-143">이제 할 가정해 배열에 1 년 이상에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="15365-143">Now suppose you decide to have your array hold information for more than one year.</span></span> <span data-ttu-id="15365-144">5 년에 대 한 판매 금액을 추적 하려는 경우 다음 예제와 같이 5 계층, 12 행 및 31 개 열을 사용 하 여 3 차원 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15365-144">If you want to track sales amounts for 5 years, you could declare a three-dimensional array with 5 layers, 12 rows, and 31 columns, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 <span data-ttu-id="15365-145">이때 각 인덱스의 각 차원 최대값으로 0에서 달라 지므로 `salesAmounts` 해당 차원에 필요한 길이 보다 1 작은 값으로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15365-145">Note that, because each index varies from 0 to its maximum, each dimension of `salesAmounts` is declared as one less than the required length for that dimension.</span></span> <span data-ttu-id="15365-146">각 새 차원 배열의 크기 증가 또한 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="15365-146">Note also that the size of the array increases with each new dimension.</span></span> <span data-ttu-id="15365-147">앞의 예제에서 세 가지 크기는 각각 31, 372, 및 1,860 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="15365-147">The three sizes in the preceding examples are 31, 372, and 1,860 elements respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15365-148">사용 하지 않고 배열을 만들 수 있습니다 합니다 `Dim` 문 또는 `New` 절.</span><span class="sxs-lookup"><span data-stu-id="15365-148">You can create an array without using the `Dim` statement or the `New` clause.</span></span> <span data-ttu-id="15365-149">예를 들어, 호출할 수 있습니다는 <xref:System.Array.CreateInstance%2A> 메서드 또는 다른 구성 요소 배열을 전달할 수 코드 이러한 방식으로 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="15365-149">For example, you can call the <xref:System.Array.CreateInstance%2A> method, or another component can pass your code an array created in this manner.</span></span> <span data-ttu-id="15365-150">이러한 배열은 0이 아닌 하한값을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15365-150">Such an array can have a lower bound other than 0.</span></span> <span data-ttu-id="15365-151">사용 하 여 차원에서 최소치 항상 테스트할 수 있습니다 합니다 <xref:System.Array.GetLowerBound%2A> 메서드 또는 `LBound` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="15365-151">You can always test for the lower bound of a dimension by using the <xref:System.Array.GetLowerBound%2A> method or the `LBound` function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15365-152">참고자료</span><span class="sxs-lookup"><span data-stu-id="15365-152">See also</span></span>
- [<span data-ttu-id="15365-153">배열</span><span class="sxs-lookup"><span data-stu-id="15365-153">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="15365-154">배열 문제 해결</span><span class="sxs-lookup"><span data-stu-id="15365-154">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
