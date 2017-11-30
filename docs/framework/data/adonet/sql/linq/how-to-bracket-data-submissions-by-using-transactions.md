---
title: "방법: 트랜잭션을 사용하여 데이터 대괄호 전송"
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
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 071c0c8bc7e0bb8dca01e9fc51c66fb930ed102b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>방법: 트랜잭션을 사용하여 데이터 대괄호 전송
<xref:System.Transactions.TransactionScope>를 사용하여 데이터베이스에 대한 전송을 표시합니다. 자세한 내용은 참조 [트랜잭션 지원](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 데이터베이스 전송을 <xref:System.Transactions.TransactionScope>로 묶습니다.  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>참고 항목  
 [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [만들고 데이터 변경 내용을 전송](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [트랜잭션 지원](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)
