---
title: CLR 저장 프로시저
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: a1a37ac1257594913c6d06cb08df2882e8773da8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554636"
---
# <a name="clr-stored-procedures"></a>CLR 저장 프로시저
저장 프로시저는 스칼라 식에 사용할 수 없는 루틴입니다. 또한 클라이언트에 테이블 형식 결과와 메시지를 반환하고 DDL(데이터 정의 언어) 및 DML(데이터 조작 언어) 문을 호출하며 출력 매개 변수를 반환합니다.  
  
> [!NOTE]
>  Microsoft Visual Basic에서는 Microsoft Visual C#과 다른 방식으로 출력 매개 변수를 지원합니다. 참조로 매개 변수를 전달 하 고 적용을 지정 해야 합니다 \<나타내야 >는 다음과 같이 출력 매개 변수를 나타내는 특성:  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
자세한 내용은 참조는 버전의 [SQL Server 설명서](/sql) 사용 중인 SQL Server의 버전에 대 한 합니다.
  
 **SQL Server 설명서**

1. [CLR 저장 프로시저](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a>참고자료
- [관리 코드에서 SQL Server 2005 개체 만들기](https://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
