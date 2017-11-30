---
title: "방법: 두 목록 (Visual Basic) (LINQ) 간의 차집합 구하기"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5b25474-10a8-4df6-aab5-75621bb6b68e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 267e348ac528b210e25c5b8b6e01294a225bc48e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-visual-basic"></a><span data-ttu-id="4e998-102">방법: 두 목록 (Visual Basic) (LINQ) 간의 차집합 구하기</span><span class="sxs-lookup"><span data-stu-id="4e998-102">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="4e998-103">이 예제에서는 LINQ를 사용하여 두 개의 문자열 목록을 비교하고 names1.txt에 있지만 names2.txt에는 없는 줄만 출력하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e998-103">This example shows how to use LINQ to compare two lists of strings and output those lines that are in names1.txt but not in names2.txt.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="4e998-104">데이터 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4e998-104">To create the data files</span></span>  
  
1.  <span data-ttu-id="4e998-105">에 표시 된 대로 names1.txt 및 names2.txt를 솔루션 폴더로 복사 [하는 방법: 결합 및 비교 문자열 컬렉션 (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e998-105">Copy names1.txt and names2.txt to your solution folder as shown in [How to: Combine and Compare String Collections (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e998-106">예제</span><span class="sxs-lookup"><span data-stu-id="4e998-106">Example</span></span>  
  
```vb  
Class CompareLists  
  
    Shared Sub Main()  
  
        ' Create the IEnumerable data sources.  
        Dim names1 As String() = System.IO.File.ReadAllLines("../../../names1.txt")  
        Dim names2 As String() = System.IO.File.ReadAllLines("../../../names2.txt")  
  
        ' Create the query. Note that method syntax must be used here.  
        Dim differenceQuery = names1.Except(names2)  
        Console.WriteLine("The following lines are in names1.txt but not names2.txt")  
  
        ' Execute the query.  
        For Each name As String In differenceQuery  
            Console.WriteLine(name)  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output:  
' The following lines are in names1.txt but not names2.txt  
' Potra, Cristina  
' Noriega, Fabricio  
' Aw, Kam Foo  
' Toyoshima, Tim  
' Guy, Wey Yuan  
' Garcia, Debra  
```  
  
 <span data-ttu-id="4e998-107">와 같은 일부 유형의 쿼리 Visual Basic에서 작업 <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, 및 <xref:System.Linq.Enumerable.Concat%2A>, 메서드 기반의 구문을 으로만 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e998-107">Some types of query operations in Visual Basic, such as <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Concat%2A>, can only be expressed in method-based syntax.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4e998-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="4e998-108">Compiling the Code</span></span>  
 <span data-ttu-id="4e998-109">System.Core.dll에 대한 참조와 System.Linq 네임스페이스에 대한 `Imports` 문을 사용하여 .NET Framework 버전 3.5 이상을 대상으로 하는 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e998-109">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e998-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e998-110">See Also</span></span>  
 [<span data-ttu-id="4e998-111">LINQ 및 문자열 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e998-111">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
