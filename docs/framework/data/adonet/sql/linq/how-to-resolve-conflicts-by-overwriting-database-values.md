---
title: "방법: 데이터베이스 값을 덮어써서 충돌 해결"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: fd6db0b8-c29c-48ff-b768-31d28e7a148c
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f3155eca2344e32913aaacbd0e2671603824aaf4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resolve-conflicts-by-overwriting-database-values"></a><span data-ttu-id="b0e38-102">방법: 데이터베이스 값을 덮어써서 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="b0e38-102">How to: Resolve Conflicts by Overwriting Database Values</span></span>
<span data-ttu-id="b0e38-103">변경 내용을 전송하기 전에 예상 데이터베이스 값과 실제 데이터베이스 값의 차이점을 조정하려면 <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>를 사용하여 데이터베이스 값을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="b0e38-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> to overwrite database values.</span></span> <span data-ttu-id="b0e38-104">자세한 내용은 참조 [낙관적 동시성: 개요](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e38-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0e38-105">모든 경우에 데이터베이스에서 업데이트된 데이터를 검색하여 클라이언트의 레코드를 먼저 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="b0e38-105">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="b0e38-106">이렇게 하면 다음 업데이트 시도는 동일한 동시성 검사에서 실패하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e38-106">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0e38-107">예</span><span class="sxs-lookup"><span data-stu-id="b0e38-107">Example</span></span>  
 <span data-ttu-id="b0e38-108">이 시나리오에서는 User1이 변경 내용을 전송하려 하는 경우 User2가 그 동안에 Assistant 열과 Department 열을 변경했기 때문에 <xref:System.Data.Linq.ChangeConflictException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0e38-108">In this scenario, an <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="b0e38-109">다음 표에서는 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b0e38-109">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="b0e38-110">Manager</span><span class="sxs-lookup"><span data-stu-id="b0e38-110">Manager</span></span>|<span data-ttu-id="b0e38-111">Assistant</span><span class="sxs-lookup"><span data-stu-id="b0e38-111">Assistant</span></span>|<span data-ttu-id="b0e38-112">Department</span><span class="sxs-lookup"><span data-stu-id="b0e38-112">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="b0e38-113">User1과 User2가 쿼리했을 때 원래 데이터베이스 상태</span><span class="sxs-lookup"><span data-stu-id="b0e38-113">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="b0e38-114">Alfreds</span><span class="sxs-lookup"><span data-stu-id="b0e38-114">Alfreds</span></span>|<span data-ttu-id="b0e38-115">Maria</span><span class="sxs-lookup"><span data-stu-id="b0e38-115">Maria</span></span>|<span data-ttu-id="b0e38-116">Sales</span><span class="sxs-lookup"><span data-stu-id="b0e38-116">Sales</span></span>|  
|<span data-ttu-id="b0e38-117">User1이 변경 내용 전송 준비</span><span class="sxs-lookup"><span data-stu-id="b0e38-117">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="b0e38-118">Alfred</span><span class="sxs-lookup"><span data-stu-id="b0e38-118">Alfred</span></span>||<span data-ttu-id="b0e38-119">Marketing</span><span class="sxs-lookup"><span data-stu-id="b0e38-119">Marketing</span></span>|  
|<span data-ttu-id="b0e38-120">User2가 이미 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="b0e38-120">User2 has already submitted these changes.</span></span>||<span data-ttu-id="b0e38-121">Mary</span><span class="sxs-lookup"><span data-stu-id="b0e38-121">Mary</span></span>|<span data-ttu-id="b0e38-122">서비스</span><span class="sxs-lookup"><span data-stu-id="b0e38-122">Service</span></span>|  
  
 <span data-ttu-id="b0e38-123">User1이 데이터베이스 값을 현재 클라이언트 멤버 값에 덮어써서 이 충돌을 해결하기로 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e38-123">User1 decides to resolve this conflict by overwriting database values with the current client member values.</span></span>  
  
 <span data-ttu-id="b0e38-124">User1이 <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>를 사용하여 문제를 해결하는 경우 데이터베이스의 결과는 다음 테이블과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e38-124">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>, the result in the database is as in following table:</span></span>  
  
||<span data-ttu-id="b0e38-125">Manager</span><span class="sxs-lookup"><span data-stu-id="b0e38-125">Manager</span></span>|<span data-ttu-id="b0e38-126">Assistant</span><span class="sxs-lookup"><span data-stu-id="b0e38-126">Assistant</span></span>|<span data-ttu-id="b0e38-127">Department</span><span class="sxs-lookup"><span data-stu-id="b0e38-127">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="b0e38-128">충돌 해결 후 변경된 상태</span><span class="sxs-lookup"><span data-stu-id="b0e38-128">New state after conflict resolution.</span></span>|<span data-ttu-id="b0e38-129">Alfred</span><span class="sxs-lookup"><span data-stu-id="b0e38-129">Alfred</span></span><br /><br /> <span data-ttu-id="b0e38-130">(User1이 전송한 값)</span><span class="sxs-lookup"><span data-stu-id="b0e38-130">(from User1)</span></span>|<span data-ttu-id="b0e38-131">Maria</span><span class="sxs-lookup"><span data-stu-id="b0e38-131">Maria</span></span><br /><br /> <span data-ttu-id="b0e38-132">(원래 값)</span><span class="sxs-lookup"><span data-stu-id="b0e38-132">(original)</span></span>|<span data-ttu-id="b0e38-133">Marketing</span><span class="sxs-lookup"><span data-stu-id="b0e38-133">Marketing</span></span><br /><br /> <span data-ttu-id="b0e38-134">(User1이 전송한 값)</span><span class="sxs-lookup"><span data-stu-id="b0e38-134">(from User1)</span></span>|  
  
 <span data-ttu-id="b0e38-135">다음의 예제 코드에서는 데이터베이스 값을 현재 클라이언트 멤버 값으로 덮어쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b0e38-135">The following example code shows how to overwrite database values with the current client member values.</span></span> <span data-ttu-id="b0e38-136">각 멤버 충돌에 대한 검사 또는 사용자 지정 처리는 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e38-136">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b0e38-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0e38-137">See Also</span></span>  
 [<span data-ttu-id="b0e38-138">방법: 변경 내용 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="b0e38-138">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
