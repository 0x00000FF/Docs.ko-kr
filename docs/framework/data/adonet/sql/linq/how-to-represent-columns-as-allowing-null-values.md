---
title: "방법: NULL 값을 허용하도록 열 표현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: efa6f9d453940151dfe01d27827760521359ab67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a>방법: NULL 값을 허용하도록 열 표현
사용 하 여는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> 속성에는 <xref:System.Data.Linq.Mapping.ColumnAttribute> 연결 된 데이터베이스 열의 null 값을 보유할 수를 지정 하는 특성입니다.  
  
 코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>를 참조하세요.  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a>열을 null 값을 허용하는 열로 지정하려면  
  
1.  <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.  
  
2.  <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> 속성 값을 `true`로 설정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [방법: 엔터티 클래스 코드 편집기를 사용 하 여 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
