---
title: "방법: 데이터베이스 이름 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b80f0fd2-7f75-45fe-9e12-496f80f183df
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d0dffe22205b2d59dbd77bcd8f86efe4fa56be3b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-database-names"></a>방법: 데이터베이스 이름 지정
연결에서 이름이 제공되지 않은 경우 <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> 특성의 <xref:System.Data.Linq.Mapping.DatabaseAttribute> 속성을 사용하여 데이터베이스의 이름을 지정합니다.  
  
 코드 샘플은 <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>을 참조하세요.  
  
### <a name="to-specify-the-name-of-the-database"></a>데이터베이스의 이름을 지정하려면  
  
1.  데이터베이스의 클래스 선언에 <xref:System.Data.Linq.Mapping.DatabaseAttribute> 특성을 추가합니다.  
  
2.  <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> 특성에 <xref:System.Data.Linq.Mapping.DatabaseAttribute> 속성을 추가합니다.  
  
3.  <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> 속성 값을 지정할 이름으로 설정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
