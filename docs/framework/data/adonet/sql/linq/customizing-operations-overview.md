---
title: "작업 사용자 지정: 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 9776daa28b0a7ffcd3b721f004f5b9a44dd09f48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-operations-overview"></a><span data-ttu-id="73e9a-102">작업 사용자 지정: 개요</span><span class="sxs-lookup"><span data-stu-id="73e9a-102">Customizing Operations: Overview</span></span>
<span data-ttu-id="73e9a-103">기본적으로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 매핑을 기반으로 하는 삽입, 업데이트 및 삭제 작업을 위한 동적 SQL을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="73e9a-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL for insert, update, and delete operations based on mapping.</span></span> <span data-ttu-id="73e9a-104">그러나 실제로는 사용자 고유의 비즈니스 논리를 추가하여 보안, 유효성 검사 등을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="73e9a-104">However, in practice you typically want to add your own business logic to provide for security, validation, and so forth.</span></span>  
  
 <span data-ttu-id="73e9a-105">이러한 작업을 사용자 지정하는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기술에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="73e9a-105">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] techniques for customizing these operations include the following.</span></span>  
  
## <a name="loading-options"></a><span data-ttu-id="73e9a-106">로드 옵션</span><span class="sxs-lookup"><span data-stu-id="73e9a-106">Loading Options</span></span>  
 <span data-ttu-id="73e9a-107">쿼리에서 데이터베이스에 연결할 때 검색되는 주 대상에 관련된 데이터의 양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73e9a-107">In your queries, you can control how much data related to your main target is retrieved when you connect to the database.</span></span> <span data-ttu-id="73e9a-108">이 기능은 <xref:System.Data.Linq.DataLoadOptions>를 사용하여 대규모로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="73e9a-108">This functionality is implemented largely by using <xref:System.Data.Linq.DataLoadOptions>.</span></span> <span data-ttu-id="73e9a-109">자세한 내용은 참조 [지연 된 실행과 즉시 로드 비교](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73e9a-109">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
## <a name="partial-methods"></a><span data-ttu-id="73e9a-110">부분 메서드</span><span class="sxs-lookup"><span data-stu-id="73e9a-110">Partial Methods</span></span>  
 <span data-ttu-id="73e9a-111">해당 기본 매핑에서 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 사용자 비즈니스 논리를 구현하는 데 도움이 되는 부분 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="73e9a-111">In its default mapping, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides partial methods to help you implement your business logic.</span></span> <span data-ttu-id="73e9a-112">자세한 내용은 참조 [추가 비즈니스 논리에서 사용 하 여 부분 메서드](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73e9a-112">For more information, see [Adding Business Logic By Using Partial Methods](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md).</span></span>  
  
## <a name="stored-procedures-and-user-defined-functions"></a><span data-ttu-id="73e9a-113">저장 프로시저 및 사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="73e9a-113">Stored Procedures and User-Defined Functions</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="73e9a-114">에서는 저장 프로시저 및 사용자 정의 함수의 사용을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="73e9a-114"> supports the use of stored procedures and user-defined functions.</span></span> <span data-ttu-id="73e9a-115">저장 프로시저는 작업을 사용자 지정하는 데 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="73e9a-115">Stored procedures are frequently used to customize operations.</span></span> <span data-ttu-id="73e9a-116">자세한 내용은 [저장 프로시저](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73e9a-116">For more information, see [Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73e9a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73e9a-117">See Also</span></span>  
 [<span data-ttu-id="73e9a-118">삽입, 업데이트 및 삭제 작업 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="73e9a-118">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
