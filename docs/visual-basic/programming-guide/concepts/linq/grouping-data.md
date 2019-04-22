---
title: 데이터 그룹화 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 8f3a0871-6958-4aef-8f6f-493e189fd57d
ms.openlocfilehash: c658ac5c46baec1bfa976074b78ac86d791b6515
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842059"
---
# <a name="grouping-data-visual-basic"></a><span data-ttu-id="d807b-102">데이터 그룹화 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d807b-102">Grouping Data (Visual Basic)</span></span>
<span data-ttu-id="d807b-103">그룹화는 데이터를 그룹에 넣어 각 그룹의 요소가 공통 특성을 공유하게 하는 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="d807b-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="d807b-104">다음 그림은 문자 시퀀스를 그룹화한 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d807b-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="d807b-105">각 그룹에 대한 키는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="d807b-105">The key for each group is the character.</span></span>  
  
 <span data-ttu-id="d807b-106">![LINQ 그룹화 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span><span class="sxs-lookup"><span data-stu-id="d807b-106">![LINQ Grouping Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span></span>  
  
 <span data-ttu-id="d807b-107">데이터 요소를 그룹화하는 표준 쿼리 연산자 메서드가 다음 섹션에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d807b-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d807b-108">메서드</span><span class="sxs-lookup"><span data-stu-id="d807b-108">Methods</span></span>  
  
|<span data-ttu-id="d807b-109">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="d807b-109">Method Name</span></span>|<span data-ttu-id="d807b-110">설명</span><span class="sxs-lookup"><span data-stu-id="d807b-110">Description</span></span>|<span data-ttu-id="d807b-111">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="d807b-111">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="d807b-112">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d807b-112">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="d807b-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="d807b-113">GroupBy</span></span>|<span data-ttu-id="d807b-114">공통 특성을 공유하는 요소를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="d807b-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="d807b-115">각 그룹은 <xref:System.Linq.IGrouping%602> 개체로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d807b-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`Group … By … Into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d807b-116">ToLookup</span><span class="sxs-lookup"><span data-stu-id="d807b-116">ToLookup</span></span>|<span data-ttu-id="d807b-117">키 선택기 함수에 따라 <xref:System.Linq.Lookup%602>(일대다 사전)에 요소를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d807b-117">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="d807b-118">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="d807b-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="d807b-119">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="d807b-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="d807b-120">다음 코드 예제에서는 `Group By` 절을 사용하여 짝수 또는 홀수인지에 따라 목록에서 정수를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="d807b-120">The following code example uses the `Group By` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```vb  
Dim numbers As New System.Collections.Generic.List(Of Integer)(  
     New Integer() {35, 44, 200, 84, 3987, 4, 199, 329, 446, 208})  
  
Dim query = From number In numbers   
            Group By Remainder = (number Mod 2) Into Group  
  
Dim sb As New System.Text.StringBuilder()  
For Each group In query  
    sb.AppendLine(If(group.Remainder = 0, vbCrLf & "Even numbers:", vbCrLf & "Odd numbers:"))  
    For Each num In group.Group  
        sb.AppendLine(num)  
    Next  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' Odd numbers:  
' 35  
' 3987  
' 199  
' 329  
  
' Even numbers:  
' 44  
' 200  
' 84  
' 4  
' 446  
' 208  
```  
  
## <a name="see-also"></a><span data-ttu-id="d807b-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="d807b-121">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="d807b-122">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d807b-122">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="d807b-123">Group By 절</span><span class="sxs-lookup"><span data-stu-id="d807b-123">Group By Clause</span></span>](../../../../visual-basic/language-reference/queries/group-by-clause.md)
- [<span data-ttu-id="d807b-124">방법: 그룹 파일 확장명 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d807b-124">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="d807b-125">방법: 그룹 (LINQ) (Visual Basic)를 사용 하 여 여러 파일로 분합니다</span><span class="sxs-lookup"><span data-stu-id="d807b-125">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
