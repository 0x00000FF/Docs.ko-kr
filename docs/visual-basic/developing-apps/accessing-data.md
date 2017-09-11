---
title: "Visual Basic 응용 프로그램에서 데이터에 액세스"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- data [Visual Basic]
- Visual Basic, data access
ms.assetid: 3086ab38-3be5-4b22-9385-7d0e16b04f6a
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4ff9885f66171ee0454bff058b342d1b5683d3e3
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="accessing-data-in-visual-basic-applications"></a><span data-ttu-id="9cbcb-102">Visual Basic 응용 프로그램에서 데이터에 액세스</span><span class="sxs-lookup"><span data-stu-id="9cbcb-102">Accessing data in Visual Basic applications</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="9cbcb-103">에는 데이터에 액세스하는 응용 프로그램 개발을 지원하기 위한 여러 가지 새로운 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-103"> includes several new features to assist in developing applications that access data.</span></span> <span data-ttu-id="9cbcb-104">[데이터 소스 창](/visualstudio/data-tools/add-new-data-sources)에서 양식으로 항목을 끌어 Windows 응용 프로그램에 대한 데이터 바인딩된 양식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-104">Data-bound forms for Windows applications are created by dragging items from the [Data Sources Window](/visualstudio/data-tools/add-new-data-sources) onto the form.</span></span> <span data-ttu-id="9cbcb-105">**데이터 소스 창**에서 기존 컨트롤로 항목을 끌어 컨트롤을 데이터에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-105">You bind controls to data by dragging items from the **Data Sources Window** onto existing controls.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9cbcb-106">관련 단원</span><span class="sxs-lookup"><span data-stu-id="9cbcb-106">Related sections</span></span>  
 [<span data-ttu-id="9cbcb-107">Visual Studio에서 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="9cbcb-107">Accessing Data in Visual Studio</span></span>](/visualstudio/data-tools/)  
 <span data-ttu-id="9cbcb-108">응용 프로그램에 데이터 액세스 기능을 통합하는 방법을 설명하는 페이지의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-108">Provides links to pages that discuss incorporating data access functionality into your applications.</span></span>

 [<span data-ttu-id="9cbcb-109">.NET용 Visual Studio 데이터 도구</span><span class="sxs-lookup"><span data-stu-id="9cbcb-109">Visual Studio data tools for .NET</span></span>](/visualstudio/data-tools/visual-studio-data-tools-for-dotnet)  
 <span data-ttu-id="9cbcb-110">[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]를 통해 데이터를 사용하는 응용 프로그램을 만드는 방법에 대한 페이지의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-110">Provides links to pages on creating applications that work with data, using [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span></span>  
  
 [<span data-ttu-id="9cbcb-111">LINQ</span><span class="sxs-lookup"><span data-stu-id="9cbcb-111">LINQ</span></span>](../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="9cbcb-112">Visual Basic에서 LINQ를 사용하는 방법을 설명하는 항목의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-112">Provides links to topics that describe how to use LINQ with Visual Basic.</span></span>  
  
 [<span data-ttu-id="9cbcb-113">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="9cbcb-113">LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb386976)  
 <span data-ttu-id="9cbcb-114">[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-114">Provides information about [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="9cbcb-115">프로그래밍 예제를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-115">Includes programming examples.</span></span>  
  
 <span data-ttu-id="9cbcb-116">[LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)(Visual Studio의 LINQ to SQL 도구)</span><span class="sxs-lookup"><span data-stu-id="9cbcb-116">[LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)</span></span>  
 <span data-ttu-id="9cbcb-117">응용 프로그램에서 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) 개체 모델을 만드는 방법에 대한 항목의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-117">Provides links to topics about how to create a [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) object model in applications.</span></span>  
  
 [<span data-ttu-id="9cbcb-118">n 계층 응용 프로그램에서 데이터 집합 작업</span><span class="sxs-lookup"><span data-stu-id="9cbcb-118">Work with datasets in n-tier applications</span></span>](/visualstudio/data-tools/work-with-datasets-in-n-tier-applications)  
 <span data-ttu-id="9cbcb-119">다중 계층 데이터 응용 프로그램을 만드는 방법에 대한 항목의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-119">Provides links to topics about how to create multitiered data applications.</span></span>  
     
 [<span data-ttu-id="9cbcb-120">새 연결 추가</span><span class="sxs-lookup"><span data-stu-id="9cbcb-120">Add new connections</span></span>](/visualstudio/data-tools/add-new-connections)  
 <span data-ttu-id="9cbcb-121">[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]를 사용하여 디자인 타임 도구 및 ADO.NET 연결 개체를 통해 응용 프로그램을 데이터에 연결하는 방법에 대한 페이지의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-121">Provides links to pages on connecting your application to data with design-time tools and ADO.NET connection objects, using [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span></span>  

 [<span data-ttu-id="9cbcb-122">Visual Studio의 데이터 집합 도구</span><span class="sxs-lookup"><span data-stu-id="9cbcb-122">Dataset Tools in Visual Studio</span></span>](/visualstudio/data-tools/dataset-tools-in-visual-studio)  
 <span data-ttu-id="9cbcb-123">데이터를 데이터 집합에 로드하는 방법 및 SQL 문과 저장 프로시저를 실행하는 방법을 설명하는 페이지의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-123">Provides links to pages describing how to load data into datasets and how to execute SQL statements and stored procedures.</span></span>  
  
 [<span data-ttu-id="9cbcb-124">Visual Studio에서 데이터에 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="9cbcb-124">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)  
 <span data-ttu-id="9cbcb-125">데이터 바인딩된 컨트롤을 통해 Windows Forms에 데이터를 표시하는 방법을 설명하는 페이지의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-125">Provides links to pages that explain how to display data on Windows Forms through data-bound controls.</span></span>  
  
 [<span data-ttu-id="9cbcb-126">데이터 집합의 데이터 편집</span><span class="sxs-lookup"><span data-stu-id="9cbcb-126">Edit Data in Datasets</span></span>](/visualstudio/data-tools/edit-data-in-datasets)  
 <span data-ttu-id="9cbcb-127">데이터 집합의 데이터 테이블에서 데이터를 조작하는 방법을 설명하는 페이지의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-127">Provides links to pages describing how to manipulate the data in the data tables of a dataset.</span></span>  
  
 [<span data-ttu-id="9cbcb-128">데이터 집합의 데이터 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="9cbcb-128">Validate data in datasets</span></span>](/visualstudio/data-tools/validate-data-in-datasets)  
 <span data-ttu-id="9cbcb-129">열 및 행 변경 중에 데이터 집합에 유효성 검사를 추가하는 방법을 설명하는 페이지의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-129">Provides links to pages describing how to add validation to a dataset during column and row changes.</span></span>  
  
 [<span data-ttu-id="9cbcb-130">데이터를 다시 데이터베이스에 저장</span><span class="sxs-lookup"><span data-stu-id="9cbcb-130">Save data back to the database</span></span>](/visualstudio/data-tools/save-data-back-to-the-database)  
 <span data-ttu-id="9cbcb-131">응용 프로그램에서 데이터베이스로 업데이트된 데이터를 보내는 방법을 설명하는 페이지의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-131">Provides links to pages explaining how to send updated data from an application to the database.</span></span>  
  
 [<span data-ttu-id="9cbcb-132">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9cbcb-132">ADO.NET</span></span>](https://msdn.microsoft.com/library/e80y5yhx.aspx)  
 <span data-ttu-id="9cbcb-133">.NET Framework 프로그래머에게 데이터 액세스 서비스를 표시하는 ADO.NET 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-133">Describes the ADO.NET classes, which expose data-access services to the .NET Framework programmer.</span></span>

 [<span data-ttu-id="9cbcb-134">Office 솔루션의 데이터</span><span class="sxs-lookup"><span data-stu-id="9cbcb-134">Data in Office Solutions</span></span>](https://msdn.microsoft.com/library/xx069ybh)  
 <span data-ttu-id="9cbcb-135">스키마 지향 프로그래밍, 데이터 캐싱 및 서버 쪽 데이터 액세스에 대한 정보를 비롯하여 Office 솔루션에서 데이터가 작동하는 방법을 설명하는 페이지의 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-135">Contains links to pages that explain how data works in Office solutions, including information about schema-oriented programming, data caching, and server-side data access.</span></span>

