---
title: LINQ to SQL 원본 코드 분석
ms.date: 03/30/2017
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
ms.openlocfilehash: 25c54fa67171b456b2eeb5c30f52d1e654fca995
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353756"
---
# <a name="analyzing-linq-to-sql-source-code"></a><span data-ttu-id="11605-102">LINQ to SQL 원본 코드 분석</span><span class="sxs-lookup"><span data-stu-id="11605-102">Analyzing LINQ to SQL Source Code</span></span>
<span data-ttu-id="11605-103">다음 단계에 따라 Northwind 샘플 데이터베이스에서 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 소스 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11605-103">By using the following steps, you can produce [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] source code from the Northwind sample database.</span></span> <span data-ttu-id="11605-104">개체 모델 요소와 데이터베이스 요소를 비교하여 다른 항목이 매핑되는 방법을 보다 명확하게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11605-104">You can compare elements of the object model with elements of the database to better see how different items are mapped.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11605-105">Visual Studio를 사용 하 여 개발자가 사용할 수는 [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] 이 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="11605-105">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to produce this code.</span></span>  
  
1.  <span data-ttu-id="11605-106">Northwind 샘플 데이터베이스가 개발 컴퓨터에 없는 경우 무료로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11605-106">If you do not already have the Northwind sample database on your development computer, you can download it free of charge.</span></span> <span data-ttu-id="11605-107">자세한 내용은 참조 [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11605-107">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
2.  <span data-ttu-id="11605-108">Visual Basic 또는 C# 소스 파일을 생성하려면 SqlMetal 명령줄 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="11605-108">Use the SqlMetal command-line tool to generate a Visual Basic or C# source file.</span></span> <span data-ttu-id="11605-109">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11605-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span> <span data-ttu-id="11605-110">명령 프롬프트에 다음 명령을 입력하여 저장 프로시저 및 함수를 포함하는 Visual Basic 및 C# 소스 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11605-110">By typing the following commands at a command prompt, you can generate Visual Basic and C# source files that include stored procedures and functions:</span></span>  
  
    -   `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    -   `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a><span data-ttu-id="11605-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11605-111">See Also</span></span>  
 [<span data-ttu-id="11605-112">참조</span><span class="sxs-lookup"><span data-stu-id="11605-112">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [<span data-ttu-id="11605-113">배경 정보</span><span class="sxs-lookup"><span data-stu-id="11605-113">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
