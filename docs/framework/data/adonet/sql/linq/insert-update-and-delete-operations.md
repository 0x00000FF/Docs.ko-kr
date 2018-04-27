---
title: 삽입, 업데이트 및 삭제 작업
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: fcfb858dbc4bed1109c31c24b29731e74afd6ce1
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="insert-update-and-delete-operations"></a>삽입, 업데이트 및 삭제 작업
`Insert`에서는 개체 모델에서 개체를 추가, 변경 및 제거함으로써 `Update`, `Delete` 및 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 작업을 수행합니다. 기본적으로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 사용자 작업을 SQL로 변환하여 데이터베이스로 변경 내용을 전송합니다.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 개체에 대한 변경 내용을 조작하고 유지하는 데 최대한의 유연성을 제공합니다. 엔터티 개체를 쿼리를 통해 검색하거나 새로 생성하여 사용할 수 있으면 응용 프로그램에서 해당 개체를 일반적인 개체로 변경할 수 있습니다. 즉, 해당 값을 변경, 사용자 컬렉션에 추가할 수 있습니다 및 컬렉션에서 제거할 수 있습니다. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 변경 내용을 추적하여 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출할 때 변경 내용을 데이터베이스로 다시 전송할 수 있도록 준비합니다.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 하위 삭제 작업을 지원하거나 인식하지 않습니다. 설정 하거나 해야 제약 조건이 있는 테이블의 행을 삭제 하려는 경우는 `ON DELETE CASCADE` 는 데이터베이스의 외래 키 제약 조건에 규칙 하거나 사용자 고유의 코드를 사용 하 여 부모 개체를 삭제 하지 못하게 하는 자식 개체를 먼저 삭제 합니다. 그러지 않으면 예외가 throw됩니다. 자세한 내용은 참조 [하는 방법: 행 데이터베이스에서 삭제](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md)합니다.  
  
 다음에 인용된 예제에서는 Northwind 샘플 데이터베이스의 `Customer`와 `Order` 클래스를 사용합니다. 간결하게 나타내기 위해 클래스 정의는 표시하지 않았습니다.  
  
 [!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
 [!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]  
  
 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출하면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 변경 내용을 데이터베이스로 다시 전송하는 SQL 명령을 자동으로 생성하여 실행합니다.  
  
> [!NOTE]
>  일반적으로 저장 프로시저와 같은 사용자 지정 논리를 사용하여 이러한 동작을 재정의할 수 있습니다. 자세한 내용은 참조 [는에서 기본 동작 재정의 개발자의 책임](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)합니다.  
>   
>  Visual Studio를 사용 하 여 개발자가 사용할 수는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 이 목적을 위해 저장된 프로시저를 개발할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [삽입, 업데이트 및 삭제 작업 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
