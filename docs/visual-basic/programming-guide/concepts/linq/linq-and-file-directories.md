---
title: "LINQ 및 파일 디렉터리 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 159fd5c3-3926-4071-ae78-d8e423287eb7
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b9e814c9e9f8519522f288657d6940b07a0b3094
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="linq-and-file-directories-visual-basic"></a><span data-ttu-id="a8002-102">LINQ 및 파일 디렉터리 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8002-102">LINQ and File Directories (Visual Basic)</span></span>
<span data-ttu-id="a8002-103">많은 파일 시스템 작업 기본적으로 쿼리는 LINQ 사용 하는 것이 적합 하며 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8002-103">Many file system operations are essentially queries and are therefore well-suited to the LINQ approach.</span></span>  
  
 <span data-ttu-id="a8002-104">이 섹션에서는 쿼리 비파괴 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8002-104">Note that the queries in this section are non-destructive.</span></span> <span data-ttu-id="a8002-105">원본 파일이 나 폴더의 내용을 변경 하는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8002-105">They are not used to change the contents of the original files or folders.</span></span> <span data-ttu-id="a8002-106">이 쿼리도 인해 의도 하지 않은 결과가 발생 하지 않아야 하는 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a8002-106">This follows the rule that queries should not cause any side-effects.</span></span> <span data-ttu-id="a8002-107">일반적으로 원본 데이터를 수정 하는 모든 코드 (만들기 / update / delete 연산자를 수행 하는 쿼리 포함)만 데이터를 쿼리 하는 코드와에서 별도로 유지 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8002-107">In general, any code (including queries that perform create / update / delete operators) that modifies source data should be kept separate from the code that just queries the data.</span></span>  
  
 <span data-ttu-id="a8002-108">이 단원에는 다음 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8002-108">This section contains the following topics:</span></span>  
  
 [<span data-ttu-id="a8002-109">방법: 지정 된 특성 또는 이름 (Visual Basic)를 사용 하 여 파일에 대 한 쿼리</span><span class="sxs-lookup"><span data-stu-id="a8002-109">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 <span data-ttu-id="a8002-110">하나 이상의 속성을 검사 하 여 파일을 검색 하는 방법을 보여 줍니다. 그 <xref:System.IO.FileInfo>개체.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="a8002-110">Shows how to search for files by examining one or more properties of its <xref:System.IO.FileInfo> object.</span></span>  
  
 [<span data-ttu-id="a8002-111">방법: 파일 확장명 (LINQ) (Visual Basic)으로 그룹화</span><span class="sxs-lookup"><span data-stu-id="a8002-111">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 <span data-ttu-id="a8002-112">그룹을 반환 하는 방법을 보여 줍니다 <xref:System.IO.FileInfo>파일 이름 확장명을 기반으로 하는 개체입니다.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="a8002-112">Shows how to return groups of <xref:System.IO.FileInfo> object based on their file name extension.</span></span>  
  
 [<span data-ttu-id="a8002-113">방법: 폴더 (Visual Basic) (LINQ) 집합을 바이트의 총 수에 대 한 쿼리</span><span class="sxs-lookup"><span data-stu-id="a8002-113">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)  
 <span data-ttu-id="a8002-114">지정 된 디렉터리 트리에 있는 모든 파일의 총 바이트 수를 반환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8002-114">Shows how to return the total number of bytes in all the files in a specified directory tree.</span></span>  
  
 <span data-ttu-id="a8002-115">[방법: 두 폴더 (Visual Basic) (LINQ)의 내용을 비교](../../../../visual-basic/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s</span><span class="sxs-lookup"><span data-stu-id="a8002-115">[How to: Compare the Contents of Two Folders (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s</span></span>  
 <span data-ttu-id="a8002-116">두 개의 지정 된 폴더에 있는 모든 파일 및 또한 모든 파일에 특정 폴더에만 다른 있는 반환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8002-116">Shows how to return all the files that are present in two specified folders, and also all the files that are present in one folder but not the other.</span></span>  
  
 [<span data-ttu-id="a8002-117">방법: 파일 또는 디렉터리 트리 (LINQ) (Visual Basic)에서 파일에 대 한 가장 큰 쿼리</span><span class="sxs-lookup"><span data-stu-id="a8002-117">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)  
 <span data-ttu-id="a8002-118">디렉터리 트리에서 가장 크거나 작은 파일 또는 파일의 지정 된 수를 반환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8002-118">Shows how to return the largest or smallest file, or a specified number of files, in a directory tree.</span></span>  
  
 [<span data-ttu-id="a8002-119">방법: 디렉터리 트리 (LINQ) (Visual Basic)에서 중복 파일 쿼리</span><span class="sxs-lookup"><span data-stu-id="a8002-119">How to: Query for Duplicate Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)  
 <span data-ttu-id="a8002-120">지정 된 디렉터리 트리에서 둘 이상의 위치에서 발생 하는 모든 파일 이름에 대 한 그룹화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8002-120">Shows how to group for all file names that occur in more than one location in a specified directory tree.</span></span> <span data-ttu-id="a8002-121">또한 사용자 지정 비교자에 따라 좀 더 복잡 한 비교를 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8002-121">Also shows how to perform more complex comparisons based on a custom comparer.</span></span>  
  
 [<span data-ttu-id="a8002-122">방법: 폴더 (Visual Basic) (LINQ)의 파일 내용 쿼리</span><span class="sxs-lookup"><span data-stu-id="a8002-122">How to: Query the Contents of Files in a Folder (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-the-contents-of-files-in-a-folder-linq.md)  
 <span data-ttu-id="a8002-123">폴더 트리를 반복 하 고, 각 파일을 열고, 파일의 내용을 쿼리 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8002-123">Shows how to iterate through folders in a tree, open each file, and query the file's contents.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="a8002-124">설명</span><span class="sxs-lookup"><span data-stu-id="a8002-124">Comments</span></span>  
 <span data-ttu-id="a8002-125">정확 하 게 파일 시스템의 내용을 나타내는 및 예외를 정상적으로 처리 하는 데이터 소스 만들기와 관련 된 몇 가지 복잡성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8002-125">There is some complexity involved in creating a data source that accurately represents the contents of the file system and handles exceptions gracefully.</span></span> <span data-ttu-id="a8002-126">이 섹션의 예에서는 스냅숏 컬렉션을 만들 <xref:System.IO.FileInfo>지정한 루트 폴더에 있는 모든 파일 및 모든 하위 폴더를 나타내는 개체입니다.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="a8002-126">The examples in this section create a snapshot collection of <xref:System.IO.FileInfo> objects that represents all the files under a specified root folder and all its subfolders.</span></span> <span data-ttu-id="a8002-127">각각의 실제 상태 <xref:System.IO.FileInfo>시작 하 고 쿼리 실행을 종료 하는 때 사이의 시간에 변경 될 수 있습니다.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="a8002-127">The actual state of each <xref:System.IO.FileInfo> may change in the time between when you begin and end executing a query.</span></span> <span data-ttu-id="a8002-128">예를 들어 목록을 만들 수 있습니다 <xref:System.IO.FileInfo>데이터 원본으로 사용할 개체입니다.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="a8002-128">For example, you can create a list of <xref:System.IO.FileInfo> objects to use as a data source.</span></span> <span data-ttu-id="a8002-129">액세스 하려는 경우는 `Length` 쿼리에 있는 속성은 <xref:System.IO.FileInfo>개체의 값을 업데이트 하려면 파일 시스템에 액세스 하려고 합니다 `Length`.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="a8002-129">If you try to access the `Length` property in a query, the <xref:System.IO.FileInfo> object will try to access the file system to update the value of `Length`.</span></span> <span data-ttu-id="a8002-130">파일이 더 이상 존재 하는 경우는 <xref:System.IO.FileNotFoundException>쿼리에 쿼리하지 않는 경우 파일 시스템 직접.</xref:System.IO.FileNotFoundException></span><span class="sxs-lookup"><span data-stu-id="a8002-130">If the file no longer exists, you will get a <xref:System.IO.FileNotFoundException> in your query, even though you are not querying the file system directly.</span></span> <span data-ttu-id="a8002-131">이 섹션에서는 일부 쿼리는 특정 한 경우에 이러한 특정 예외를 사용 하는 별도 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8002-131">Some queries in this section use a separate method that consumes these particular exceptions in certain cases.</span></span> <span data-ttu-id="a8002-132">또 다른 옵션은 <xref:System.IO.FileSystemWatcher>.</xref:System.IO.FileSystemWatcher> 를 사용 하 여 동적으로 업데이트할 데이터 원본을 변경 하지 않으려면</span><span class="sxs-lookup"><span data-stu-id="a8002-132">Another option is to keep your data source updated dynamically by using the <xref:System.IO.FileSystemWatcher>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8002-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8002-133">See Also</span></span>  
 [<span data-ttu-id="a8002-134">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8002-134">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
