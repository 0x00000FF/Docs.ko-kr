---
title: '방법: 스칼라 반환 사용자 정의 함수 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: ffb24468c81cb4ec9f41645f8888c2c4ba021609
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127177"
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a>방법: 스칼라 반환 사용자 정의 함수 사용
<xref:System.Data.Linq.Mapping.FunctionAttribute> 특성을 사용하여 클래스에 정의된 클라이언트 메서드를 사용자 정의 함수에 매핑할 수 있습니다. 메서드 본문에서는 메서드 호출 목적을 캡처하는 식을 생성하여 해당 식을 변환 및 실행을 위해 <xref:System.Data.Linq.DataContext>로 전달합니다.  
  
> [!NOTE]
>  함수를 쿼리 외부에서 호출한 경우에만 직접 실행됩니다. 자세한 내용은 [방법: 사용자 정의 함수 인라인 호출](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)합니다.  
  
## <a name="example"></a>예제  
 다음 SQL 코드에서는 스칼라 반환 사용자 정의 함수인 `ReverseCustName()`을 나타냅니다.  
  
```  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 사용자는 이 코드에 대해 다음과 같은 클라이언트 메서드를 매핑할 수 있습니다.  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a>참고자료

- [사용자 정의 함수](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
