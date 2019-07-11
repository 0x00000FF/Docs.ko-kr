---
title: 저장 프로시저
ms.date: 03/30/2017
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
ms.openlocfilehash: b06dc19aa8b767da6a1c6b00bd5b465465db6060
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742842"
---
# <a name="stored-procedures"></a><span data-ttu-id="7c640-102">저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="7c640-102">Stored Procedures</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="7c640-103">개체 모델에서 메서드를 사용 하 여 데이터베이스에서 저장된 프로시저를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7c640-103">uses methods in your object model to represent stored procedures in the database.</span></span> <span data-ttu-id="7c640-104">필요한 위치에 <xref:System.Data.Linq.Mapping.FunctionAttribute> 특성과 <xref:System.Data.Linq.Mapping.ParameterAttribute> 특성을 적용하여 메서드를 저장 프로시저로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c640-104">You designate methods as stored procedures by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="7c640-105">자세한 내용은 [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7c640-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="7c640-106">일반적으로 개발자가 Visual Studio를 사용 하 여 저장된 프로시저에 매핑할 개체 관계형 디자이너를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c640-106">Developers using Visual Studio would typically use the Object Relational Designer to map stored procedures.</span></span> <span data-ttu-id="7c640-107">이 단원의 항목에서는 코드를 사용자가 직접 작성하는 경우 응용 프로그램에서 이러한 메서드를 만들어 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c640-107">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7c640-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="7c640-108">In This Section</span></span>  
 [<span data-ttu-id="7c640-109">방법: 행 집합 반환</span><span class="sxs-lookup"><span data-stu-id="7c640-109">How to: Return Rowsets</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)  
 <span data-ttu-id="7c640-110">데이터의 행을 반환하고 입력 매개 변수를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7c640-110">Describes how to return rows of data and shows how to use an input parameter.</span></span>  
  
 [<span data-ttu-id="7c640-111">방법: 매개 변수를 사용 하는 저장된 프로시저를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c640-111">How to: Use Stored Procedures that Take Parameters</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-that-take-parameters.md)  
 <span data-ttu-id="7c640-112">입력 및 출력 매개 변수를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7c640-112">Describes how to use input and output parameters.</span></span>  
  
 [<span data-ttu-id="7c640-113">방법: 여러 결과 도형에 매핑된 저장된 프로시저 사용</span><span class="sxs-lookup"><span data-stu-id="7c640-113">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 <span data-ttu-id="7c640-114">동일한 저장 프로시저에 다양한 모양의 반환을 제공하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7c640-114">Describes how to provide for returns of multiple shapes in the same stored procedure.</span></span>  
  
 [<span data-ttu-id="7c640-115">방법: 순차적 결과 도형에 매핑된 저장된 프로시저 사용</span><span class="sxs-lookup"><span data-stu-id="7c640-115">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 <span data-ttu-id="7c640-116">반환 시퀀스에 다양한 모양을 제공하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7c640-116">Describes how to provide for multiple shapes where the return sequence is known.</span></span>  
  
 [<span data-ttu-id="7c640-117">저장 프로시저를 사용하여 작업 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="7c640-117">Customizing Operations By Using Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)  
 <span data-ttu-id="7c640-118">저장 프로시저를 사용하여 삽입, 업데이트 및 삭제 작업을 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7c640-118">Describes how to use stored procedures to implement insert, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="7c640-119">단독으로 저장 프로시저를 사용하여 작업 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="7c640-119">Customizing Operations by Using Stored Procedures Exclusively</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures-exclusively.md)  
 <span data-ttu-id="7c640-120">저장 프로시저만 사용하여 삽입, 업데이트 및 삭제 작업을 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7c640-120">Describes how to use nothing but stored procedures to implement insert, update, and delete operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7c640-121">관련 단원</span><span class="sxs-lookup"><span data-stu-id="7c640-121">Related Sections</span></span>  
 [<span data-ttu-id="7c640-122">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="7c640-122">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="7c640-123">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 개체 모델을 만들고 사용하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c640-123">Provides information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="7c640-124">연습: 저장 프로시저 (Visual Basic)만 사용</span><span class="sxs-lookup"><span data-stu-id="7c640-124">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)  
 <span data-ttu-id="7c640-125">Visual Basic에서 저장 프로시저를 사용하는 방법을 보여 주는 절차를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c640-125">Includes procedures that illustrate how to use stored procedures in Visual Basic.</span></span>  
  
 [<span data-ttu-id="7c640-126">연습: 저장 프로시저만 사용 (C#)</span><span class="sxs-lookup"><span data-stu-id="7c640-126">Walkthrough: Using Only Stored Procedures (C#)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)  
 <span data-ttu-id="7c640-127">C#에서 저장 프로시저를 사용하는 방법을 보여 주는 절차를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c640-127">Includes procedures that illustrate how to use stored procedures in C#.</span></span>
